# Fitur Metasantri AI

## 🤖 5 Mode AI

Metasantri AI memiliki 5 persona AI yang berbeda — masing-masing dengan gaya jawaban dan tingkat kedalaman yang berbeda.

### ⚡ Flash
- **Untuk**: Pertanyaan umum, cepat, santai
- **Ciri**: Jawaban ringkas, bahasa Indonesia informal
- **Akses**: Free

### 🎒 Kang Santri
- **Untuk**: Teman belajar, gaya bahasa santri
- **Ciri**: Bahasa campuran (Indonesia + sedikit Arab), tetap pakai dalil
- **Akses**: Free

### 👳 Ustadz
- **Untuk**: Fatwa & hukum fiqih dengan referensi formal
- **Ciri**: Selalu sertakan nama kitab & halaman, bahasa formal
- **Akses**: Pro+

### 🧕 Kiyai
- **Untuk**: Analisis mendalam, ijtihad masalah kontemporer
- **Ciri**: Reasoning panjang, komparasi pendapat ulama
- **Akses**: Pro+

### 📚 Ulama
- **Untuk**: Riset akademis, komparasi mazhab
- **Ciri**: Paling detail, sertakan semua referensi yang relevan
- **Akses**: Plus

---

## 📚 RAG (Retrieval-Augmented Generation)

Ketika user bertanya, sistem secara otomatis mencari referensi paling relevan dari basis data kitab pesantren sebelum menjawab, sehingga jawaban tidak "mengarang" dalil.

**Visi jangka panjang**: mengindex **6.700+ kitab klasik pesantren** — mencakup fiqih, hadits, akidah, nahwu, tasawuf, dan tafsir — sebagai basis rujukan terlengkap untuk AI Islam berbahasa Indonesia. Proses ini sedang berjalan secara bertahap.

### Kategori Kitab yang Ditargetkan

| Kategori | Contoh |
|----------|--------|
| Fiqih | Fathul Qarib, Safinah, Taqrib, Kifayatul Akhyar |
| Hadits | Arba'in Nawawi, Bulughul Maram, Riyadhus Shalihin |
| Fiqih Mazhab | Al-Umm (Imam Syafi'i), Minhajut Thalibin |
| Akidah | Aqidatul Awam, Sanusiyyah |
| Tasawuf | Al-Hikam, Minhajul Abidin |
| Nahwu | Jurumiyyah, Alfiyyah Ibnu Malik |

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

Fitur khusus untuk diskusi hukum fiqih kontemporer.

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

Dashboard admin dengan data real-time:

- **Users**: kelola user & akses
- **RAG Monitor**: statistik kitab ter-index
- **Website Settings**: atur konten & pengaturan dari UI, tanpa perlu redeploy

---

## 🌙 Landing Page Real-Time

Background langit berubah otomatis sesuai waktu nyata:

- **Subuh**: gradien fajar oranye-biru
- **Pagi–Siang**: langit cerah dengan efek paralaks
- **Sore**: golden hour
- **Maghrib–Isya**: langit gelap dengan bintang animasi
- **Malam**: full night sky dengan bulan sabit

Waktu maghrib/isya dihitung secara real-time berdasarkan koordinat Indonesia.
