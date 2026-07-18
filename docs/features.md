# Fitur Metasantri AI

## 🤖 5 Mode AI

Metasantri AI memiliki 5 persona AI yang berbeda, bukan sekadar ganti nama — masing-masing punya system prompt, model, dan threshold RAG yang berbeda.

### ⚡ Flash
- **Model**: hy3
- **Untuk**: Pertanyaan umum, cepat, santai
- **Ciri**: Jawaban ringkas, bahasa Indonesia informal
- **Akses**: Free

### 🎒 Kang Santri
- **Model**: nex-n2-mini
- **Untuk**: Teman belajar, gaya bahasa santri
- **Ciri**: Bahasa campuran (Indonesia + sedikit Arab), tetap pakai dalil
- **Akses**: Free

### 👳 Ustadz
- **Model**: nex-n2-mini
- **Untuk**: Fatwa & hukum fiqih dengan referensi formal
- **Ciri**: Selalu sertakan nama kitab + halaman, bahasa formal
- **RAG threshold**: 0.75
- **Akses**: Pro+

### 🧕 Kiyai
- **Model**: DeepSeek-R1
- **Untuk**: Analisis mendalam, ijtihad masalah kontemporer
- **Ciri**: Reasoning panjang, komparasi pendapat ulama
- **RAG threshold**: 0.72
- **Akses**: Pro+

### 📚 Ulama
- **Model**: DeepSeek-R1
- **Untuk**: Riset akademis, komparasi mazhab
- **Ciri**: Paling detail, sertakan semua referensi yang relevan
- **RAG threshold**: 0.68
- **Akses**: Plus

---

## 📚 RAG (Retrieval-Augmented Generation)

Ketika user bertanya, sistem secara otomatis:

1. **Query embedding** — pertanyaan diubah ke vector
2. **Semantic search** — cari di 156k+ chunks kitab yang paling relevan
3. **DalilCard injection** — dalil relevan dimasukkan ke context AI
4. **Verifikasi sumber** — AI tidak boleh sebut sumber yang tidak ada di context

### Kitab yang Ter-index (19 dari target 110)

| Kategori | Kitab |
|----------|-------|
| Fiqih | Fathul Qarib, Safinah, Taqrib, Kifayatul Akhyar |
| Hadits | Arba'in Nawawi, Bulughul Maram, Riyadhus Shalihin |
| Fiqih Mazhab | Al-Umm (Imam Syafi'i), Minhajut Thalibin |
| Akidah | Aqidatul Awam, Sanusiyyah |
| Tasawuf | Al-Hikam, Minhajul Abidin |
| Nahwu | Jurumiyyah, Alfiyyah Ibnu Malik |
| + 5 kitab lainnya | |

---

## ✍️ I'rab Nahwu Otomatis

Fitur andalan untuk santri yang belajar bahasa Arab:

**Input user:**
```
إِنَّ اللَّهَ غَفُورٌ رَحِيمٌ
```

**Output Metasantri AI:**
```
إِنَّ : حرف توكيد ونصب، مبني على الفتح
اللَّهَ : اسم إن، منصوب، علامة نصبه الفتحة
غَفُورٌ : خبر إن، مرفوع، علامة رفعه الضمة
رَحِيمٌ : نعت لـ"غفور"، مرفوع
```

---

## 🔎 Bahtsul Masail

Fitur khusus untuk diskusi hukum fiqih kontemporer (Plus only).

Format output mengikuti standar Bahtsul Masail pesantren:
- **Masalah**: rumusan pertanyaan hukum
- **Jawaban**: hukum yang disimpulkan
- **Ta'lil**: alasan/dalil
- **Maraji'**: referensi kitab yang dipakai

---

## 📄 Generate Dokumen

Chat bisa menghasilkan file yang bisa didownload:

| Format | Contoh penggunaan |
|--------|-------------------|
| `.docx` | "Buatkan resume materi fiqih bab wudhu" |
| `.pdf` | "Cetak jadwal sholat bulan ini" |
| `.xlsx` | "Buat tabel hafalan santri kelas 3" |

Sistem otomatis mendeteksi intent generate dokumen dari kalimat user — tidak perlu perintah khusus.

---

## 👤 Admin Dashboard

Dashboard admin dengan data real-time (bukan mock):

- **Users**: list semua user, cari, lihat detail, ubah plan manual
- **API Config**: kelola API key Aivene/Gemini, aktifkan/nonaktifkan per key
- **RAG Monitor**: statistik kitab ter-index, jumlah chunks, score rata-rata
- **A/B Test**: bandingkan performa RAG vs non-RAG
- **Website Settings**: ubah token gratis, harga paket, nama situs — langsung dari UI tanpa redeploy

---

## 🌙 Landing Page Real-Time

Background langit berubah otomatis sesuai waktu nyata:

- **Subuh (04:00–06:00)**: gradien fajar oranye-biru
- **Pagi–Siang**: langit cerah dengan efek paralaks
- **Sore (17:00–18:30)**: golden hour
- **Maghrib–Isya**: langit gelap dengan bintang animasi
- **Malam**: full night sky dengan bulan sabit

Waktu maghrib/isya dihitung secara real-time berdasarkan koordinat Indonesia.
