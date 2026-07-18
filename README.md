<div align="center">

<img src="https://img.shields.io/badge/☪️-Metasantri_AI-1a1a2e?style=for-the-badge&logoColor=white" />

# Metasantri AI

### *Platform Belajar Islam Berbasis AI untuk Santri, Ustadz, dan Muslim Indonesia*

[![Next.js](https://img.shields.io/badge/Next.js-15-black?logo=next.js&logoColor=white)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-strict-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Supabase](https://img.shields.io/badge/Supabase-Postgres%20%2B%20Auth-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com)
[![Cloudflare](https://img.shields.io/badge/Cloudflare-Vectorize%20RAG-F38020?logo=cloudflare&logoColor=white)](https://cloudflare.com)
[![Status](https://img.shields.io/badge/status-🟢%20Live-brightgreen)]()
[![Made in Indonesia](https://img.shields.io/badge/🇮🇩-Made%20in%20Indonesia-red)]()

**Tanya ilmu Islam dan dapat jawaban dengan rujukan jelas — bukan sekadar chatbot generik.**

[🌐 Coba Sekarang](https://metasantri.vercel.app) · [📖 Dokumentasi](./docs/) · [🐛 Laporkan Bug](https://github.com/Metasantridev/metasantri-ai/issues)

</div>

---

## ✨ Apa Itu Metasantri AI?

**Metasantri AI** adalah asisten belajar Islam berbasis AI yang menjawab pertanyaan agama dengan **rujukan yang bisa dipertanggungjawabkan** — nama surah + ayat, perawi + kitab hadits, atau nama kitab ulama klasik. Bukan jawaban ngawur tanpa sumber.

Dibangun untuk:
- 🎓 **Santri pesantren** — tanya masalah fiqih, nahwu, atau tafsir kapan saja
- 🕌 **Ustadz & pengajar** — bantu riset Bahtsul Masail dan referensi kitab
- 👥 **Muslim umum Indonesia** — "tanya ustadz" versi instan 24 jam

---

## 🤖 5 Mode AI

| Mode | Model | Deskripsi | Akses |
|------|-------|-----------|-------|
| ⚡ **Flash** | hy3 | Jawaban cepat untuk pertanyaan umum | Free |
| 🎒 **Kang Santri** | nex-n2-mini | Gaya santri, bahasa santai + dalil | Free |
| 👳 **Ustadz** | nex-n2-mini | Jawaban formal dengan referensi kitab | Pro+ |
| 🧕 **Kiyai** | DeepSeek-R1 | Analisis mendalam, ijtihad kontemporer | Pro+ |
| 📚 **Ulama** | DeepSeek-R1 | Mode riset + komparasi mazhab | Plus |

---

## 🧠 Fitur Utama

### 📚 RAG Kitab Pesantren
Lebih dari **156.000 chunks** dari **19+ kitab klasik pesantren** diindex menggunakan Cloudflare Vectorize. Setiap jawaban AI bisa disertai kutipan langsung dari kitab asli.

Kitab yang sudah ter-index:
> Fathul Qarib · Safinah · Taqrib · Arba'in Nawawi · Bulughul Maram · Riyadhus Shalihin · Al-Umm · Minhajut Thalibin · dan 11+ kitab lainnya

### ✍️ I'rab & Nahwu Otomatis
Kirim teks Arab → AI langsung analisis i'rab nahwu lengkap dengan istilah Arab asli (فَاعِلٌ، مَرْفُوعٌ، مُبْتَدَأٌ dst), bukan transliterasi Latin.

### 🔎 Bahtsul Masail (Plus)
Diskusi hukum fiqih kontemporer dengan format Bahtsul Masail pesantren — lengkap dengan metode istidlal dan referensi pendapat ulama.

### 📖 Perpustakaan Kitab (Pro+)
Akses referensi dari ribuan kitab klasik Islam, bisa dicari dan dikutip langsung dari chat.

### 📄 Generate Dokumen
Chat bisa menghasilkan file `.docx`, `.pdf`, `.xlsx` langsung — misalnya: "buatkan jadwal pelajaran santri minggu ini dalam Excel."

### 🌙 Landing Page Dinamis
Background langit real-time yang berubah otomatis sesuai waktu (subuh, siang, maghrib, isya) menggunakan kalkulasi waktu sholat Indonesia.

---

## 🛠️ Tech Stack

```
Frontend      Next.js 15 (App Router) + TypeScript + Tailwind CSS
Auth & DB     Supabase (Postgres + Auth + Row Level Security)
AI Gateway    Aivene API (multi-model routing)
Vector DB     Cloudflare Vectorize (RAG + semantic search)
Embedding     OpenAI text-embedding-3-small via CF Worker
Payment       Midtrans (payment gateway Indonesia)
Deploy        Vercel (Edge Functions + CDN)
PWA           @ducanh2912/next-pwa (installable di Android/iOS)
File Gen      docx · jspdf · jszip · xlsx
```

---

## 🏗️ Arsitektur Sistem

```
User Browser
     │
     ▼
Next.js 15 (Vercel)
├── App Router (SSR + API Routes)
├── /api/stream    ──► Aivene Gateway ──► DeepSeek-R1 / nex-n2 / hy3
├── /api/rag       ──► Cloudflare Worker
│                           │
│                    CF Vectorize (156k+ chunks)
│                    + Supabase (kitab metadata)
│
├── /api/payment   ──► Midtrans Snap
└── Supabase Auth  ──► Google OAuth + Email/OTP
```

---

## 💰 Model Bisnis

| Plan | Harga | Token | Mode AI | Fitur |
|------|-------|-------|---------|-------|
| **Free** | Gratis | 10K / 5 jam | Flash, Kang Santri | Chat dasar |
| **Pro** | Rp 29.000/bln | 500K / 7 hari | + Ustadz, Kiyai | Hafalan, Perpustakaan |
| **Plus** | Rp 59.000/bln | 1.5M / bulan | + Ulama | + Bahtsul Masail, prioritas |

Token auto-reset. Tidak ada langganan tahunan — bayar bulanan, bisa berhenti kapan saja.

---

## 📊 Status Project

| Komponen | Status |
|----------|--------|
| Chat AI (5 mode) | ✅ Live |
| RAG Kitab (CF Vectorize) | ✅ 156k+ chunks, 19 kitab |
| Token System | ✅ Free/Pro/Plus |
| Admin Dashboard | ✅ Analytics, RAG, API config |
| Bahtsul Masail | ✅ Plus only |
| Hafalan + Perpustakaan | ✅ Pro+ |
| Landing Page | ✅ 16 section, real-time sky |
| PWA (installable) | ✅ Android + iOS |
| Payment (Midtrans) | 🚧 Fase 9 — in progress |
| Expand kitab (110 target) | 🚧 Fase 10 — embedding ongoing |

---

## 👤 Developer

**Faisal** · [@Metasantridev](https://github.com/Metasantridev)

Project ini dikerjakan solo sebagai platform edukasi Islam berbasis AI untuk komunitas pesantren dan muslim Indonesia. Dibangun dari nol dengan semangat *"ilmu bermanfaat yang mengalir terus."*

---

## 📄 Lisensi

Source code project ini **proprietary / closed source**. Repo ini adalah showcase publik.

Untuk kolaborasi, integrasi pesantren, atau pertanyaan bisnis: buka [Issue](https://github.com/Metasantridev/metasantri-ai/issues) atau hubungi via GitHub.

---

<div align="center">

*Dibangun dengan ❤️ untuk santri Indonesia*

**بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيم**

</div>
