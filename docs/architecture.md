# Arsitektur Metasantri AI

## Overview

Metasantri AI dibangun dengan prinsip **server-side first** — semua API key, model inference, dan logika bisnis berjalan di server, tidak pernah expose ke browser.

## Diagram Alur Chat

```
[User] → [Next.js /api/stream]
              │
              ├─ Token check (Supabase)
              ├─ Rate limit check
              │
              ├─ RAG Pipeline:
              │   └─ Query → CF Worker → CF Vectorize
              │              (semantic search 156k+ chunks)
              │              → Top-K dalil relevan
              │
              ├─ System Prompt Builder:
              │   ├─ Mode context (Flash/Kang Santri/Ustadz/Kiyai/Ulama)
              │   ├─ Dalil injected (dari RAG)
              │   └─ I'rab instruction (jika input Arab)
              │
              └─ Aivene Gateway → Model (hy3 / nex-n2-mini / deepseek-r1)
                                  Streaming response → User
```

## Komponen Utama

### 1. AI Gateway (Aivene)
- Multi-model routing: satu endpoint, banyak model
- Mode Flash → hy3 (cepat, ringan)
- Mode Ustadz → nex-n2-mini (seimbang)
- Mode Kiyai/Ulama → DeepSeek-R1 (reasoning mendalam)

### 2. RAG Pipeline
- **Sumber**: Kitab pesantren dari Shamela + HuggingFace
- **Chunking**: Per-paragraph dengan metadata (nama kitab, halaman, bab)
- **Embedding**: `openai/text-embedding-3-small` via CF Worker
- **Vector Store**: Cloudflare Vectorize (156k+ vectors)
- **Threshold**: Per-mode (Flash 0.78, Ulama 0.68) untuk presisi vs recall

### 3. Token System
- Free: 10.000 token / reset tiap 5 jam
- Pro: 500.000 token / reset tiap 7 hari
- Plus: 1.500.000 token / reset tiap bulan
- Token dikurangi per karakter response (dihitung di server)

### 4. Auth
- Supabase Auth: Email/password + Google OAuth
- RLS (Row Level Security) aktif di semua tabel sensitif
- Admin check via `profiles.role = 'admin'`

## Database Schema (simplified)

```sql
profiles          -- user data + subscription plan + token balance
sessions          -- chat history per user
api_keys          -- Aivene/Gemini keys (rotasi otomatis)
app_settings      -- konfigurasi global (token gratis, harga, dll)
kitab_chunks      -- metadata kitab (CF Vectorize menyimpan vector-nya)
orders            -- riwayat transaksi Midtrans
subscriptions     -- status langganan aktif
```

## Deployment

- **Vercel**: Next.js app (Edge Functions untuk streaming)
- **Supabase**: Database + Auth + Storage (avatar)
- **Cloudflare**: Worker (embed proxy) + Vectorize (vector DB)
- **Midtrans**: Payment gateway Indonesia
