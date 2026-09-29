# 🎴 KARTU DILEMA DIGITAL: ALGORITHM QUEST

> **"Setiap langkah punya konsekuensi."**

Media pembelajaran interaktif **Informatika — Notasi dan Penulisan Algoritma (X.AP.1)** untuk peserta didik **Kelas X / Fase E**. Dikembangkan sebagai **media tindakan** dalam Penelitian Tindakan Kelas (PTK):

> *"Penerapan Media Kartu Dilema Digital untuk Meningkatkan Kemampuan Berpikir Algoritmik Peserta Didik pada Materi Notasi dan Penulisan Algoritma Kelas X."*

Seluruh materi, tujuan pembelajaran, aktivitas, asesmen, dan tingkat kesulitan bersumber dari **Modul Ajar X.AP.1** (Problem-Based Learning berbasis Kartu Dilema Digital). Tidak ada materi di luar X.AP.1 — tidak ada bahasa pemrograman tertentu, tidak ada percabangan/perulangan/fungsi/struktur data sebagai topik khusus.

---

## ✨ Alur Media (8 Halaman)

| Halaman | Isi |
|---|---|
| **1. Landing** | Identitas media: Informatika • Kelas X/Fase E • X.AP.1, input nama, tombol MULAI MISI |
| **2. Briefing Misi** | Pengertian algoritma, pentingnya urutan instruksi, cara bermain — dalam visual cards + 6 notasi dasar (MULAI/SELESAI, INPUT, OUTPUT/DISPLAY, ←, IF/ELSE, REPEAT) |
| **3. Tutorial** | Kartu latihan "Membuat Teh Manis": susun urutan langkah (drag & drop), UJI URUTAN, lihat konsekuensinya |
| **4. Kartu Dilema** | **10 kartu (5 level × 2)** dengan tingkat kesulitan bertahap. Setiap kartu: Skenario → Pilih algoritma (2–3 alternatif yang sama-sama masuk akal) → **Komitmen alasan** → Konsekuensi (simulasi langkah demi langkah, bukan sekadar benar/salah) → Feedback (yang tepat / bermasalah / mengapa) → **Revisi** → **Refleksi mini** |
| **5. Algorithm Lab** | Drag-and-drop: menyusun langkah & merakit notasi pseudocode, lalu **UJI ALGORITMA** dengan simulasi step-by-step + pesan error yang menunjuk letak kesalahan |
| **6. Final Challenge** | Masalah baru ("Mesin Air Mineral Cerdas"): rakit sendiri algoritma dari blok + blok pengecoh, lulus 2 kasus uji |
| **7. Hasil Belajar** | Skor (KKTP ≥ 70), kartu selesai, jawaban awal benar, jawaban yang direvisi, progress 5 kemampuan (Mengidentifikasi, Membaca, Menganalisis, Mengevaluasi, Menyusun), LIHAT PEMBAHASAN, **unduh CSV untuk data observasi PTK** |
| **8. Refleksi** | 3 pertanyaan refleksi akhir (tersimpan & ikut terunduh di CSV) |

### Peta Level Kartu (mengikuti taksonomi modul)

| Level | Nama | Kemampuan | Bloom |
|---|---|---|---|
| 1 | Peta Urutan | Mengidentifikasi urutan langkah | C2–C3 |
| 2 | Baca Kode | Membaca notasi algoritma sederhana | C3 |
| 3 | Pemburu Cacat | Menemukan kesalahan & ambiguitas | C4 |
| 4 | Dua Jalur | Membandingkan dua algoritma | C5 |
| 5 | Tukang Rakit | Memperbaiki & menyusun algoritma | P3 |

**Skor:** benar pada percobaan pertama = 10 poin/kartu, benar setelah revisi = 6 poin/kartu, Final Challenge = 10 poin. Total maksimum 110 → dinormalisasi ke 0–100. KKTP mengikuti modul: **minimal 70**.

---

## 🚀 Menjalankan Secara Lokal

```bash
# 1. Clone / ekstrak source
cd kartu-dilema-digital

# 2. Install dependensi (pilih salah satu)
npm install
# atau: bun install
# atau: pnpm install

# 3. Jalankan development server
npm run dev

# 4. Buka http://localhost:3000
```

Build produksi: `npm run build` lalu `npm run start`.

## ▲ Deploy ke Vercel

> **PENTING — cek dulu ini sebelum deploy:** isi repository GitHub kamu **harus persis seperti isi folder ini**, bukan foldernya sendiri. Ketika kamu ekstrak zip, kamu dapat satu folder (mis. `kartu-dilema-digital/`). Yang di-push ke GitHub adalah **ISI** folder itu, sehingga `package.json` berada di **root repository**.

Struktur yang benar:

```
repo-github-kamu/
├── package.json        ← harus di ROOT (bukan di dalam subfolder!)
├── bun.lock
├── next.config.ts
├── tsconfig.json
├── postcss.config.mjs
├── tailwind.config.ts
├── components.json
├── eslint.config.mjs
├── README.md
├── .gitignore
└── src/
    ├── app/
    ├── components/
    ├── hooks/
    └── lib/
```

### Cara 1 — Upload lewat web GitHub (paling cepat)

1. Ekstrak zip, lalu **masuk ke dalam folder hasil ekstrak**.
2. Di GitHub: **New repository** → beri nama → **Create**.
3. Klik **uploading an existing file** → drag **SEMUA file & folder dari DALAM folder hasil ekstrak** (blok semua: `src`, `public`, `package.json`, dst.) → **Commit changes**.
4. Pastikan `package.json` tampil di daftar file root repo. Kalau tidak, berarti yang ke-upload adalah foldernya — hapus, ulangi langkah 3.

### Cara 2 — Lewat Git (disarankan)

```bash
# masuk ke DALAM folder hasil ekstrak
cd kartu-dilema-digital

git init
git add .
git commit -m "Kartu Dilema Digital: Algorithm Quest"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

### Deploy

1. Buka [vercel.com/new](https://vercel.com/new) → pilih repository tersebut.
2. Vercel otomatis mendeteksi **Next.js** — **tidak perlu mengubah pengaturan apa pun** (tidak perlu environment variables, tidak perlu database).
3. Klik **Deploy** (build ± 1–2 menit). Selesai — media siap dibagikan ke peserta didik.

> **Catatan:** butuh Node.js ≥ 20 (sudah diset otomatis via `engines` di `package.json`). Aplikasi ini 100% frontend — seluruh progres siswa tersimpan di `localStorage` per perangkat, jadi tidak ada konfigurasi database. Tombol 🔄 di pojok kanan atas menghapus progres — gunakan antar siswa yang berbagi satu perangkat.

### Troubleshooting deploy

| Pesan error di Vercel | Penyebab | Solusi |
|---|---|---|
| `Couldn't find any pages or app directory` / `No Next.js version detected` | `package.json` tidak di root repo (file ke-upload di dalam subfolder) | Pindahkan seluruh isi folder ke root repo, push ulang |
| `Cannot find module ...` / `Module not found` | Ada file/folder `src` yang tidak ter-upload (upload web GitHub kadang melewatkan banyak file sekaligus) | Pastikan 4 folder `src/app`, `src/components`, `src/hooks`, `src/lib` lengkap; kalau via web gagal terus, pakai Cara 2 (git) |
| `Unsupported engine` / Node version error | Node < 20 | Vercel otomatis pakai Node 22; kalau deploy lewat CLI lokal, upgrade Node |
| Build gagal tapi lokal jalan | Cache Vercel | Deploy → tab **Deployments** → ⋯ → **Redeploy** dengan **Use existing Build Cache: OFF** |
| `Multiple lockfiles detected` (warning) | Ada `package-lock.json` buatan sendiri di repo | Tidak fatal — hapus `package-lock.json` kalau mau bersih, biarkan `bun.lock` saja |

---

## 🗂️ Struktur Kode

```
src/
├── app/
│   ├── page.tsx              # Router tampilan 8 halaman (single-page flow)
│   ├── layout.tsx            # Metadata + tema
│   └── globals.css           # Tema dark navy / off-white / orange / electric blue
├── lib/
│   ├── gameData.ts           # SEMUA KONTEN PEMBELAJARAN (kartu, notasi, lab, final) — sumber dari Modul Ajar X.AP.1
│   ├── store.ts              # Zustand store + persist localStorage + logika unlock level
│   └── scoring.ts            # Perhitungan skor, KKTP, progress kemampuan, ekspor CSV
└── components/game/
    ├── ui.tsx                # Header, footer, renderer pseudocode, konsol simulasi
    ├── Landing.tsx           # Halaman 1
    ├── Briefing.tsx          # Halaman 2
    ├── Tutorial.tsx          # Halaman 3
    ├── CardsScreen.tsx       # Halaman 4 (peta level)
    ├── CardPlay.tsx          # Halaman 4 (engine kartu: pilih→alasan→konsekuensi→feedback→revisi→refleksi)
    ├── Lab.tsx               # Halaman 5
    ├── Final.tsx             # Halaman 6
    ├── Results.tsx           # Halaman 7
    └── Reflection.tsx        # Halaman 8
```

### Mengedit konten kartu
Semua teks kartu dilema terpusat di `src/lib/gameData.ts` pada array `CARDS`. Setiap kartu memuat: `scenario`, `mission`, `options` (pseudocode + log konsekuensi + feedback), `reasons` (opsi komitmen alasan), `conceptTags`, dan `pembahasan`. Tambah/kurangi kartu cukup dengan mengedit array ini — skor, unlock, dan halaman hasil menyesuaikan otomatis.

---

## 🛠️ Teknologi

- **Next.js 16** (App Router) + **TypeScript**
- **Tailwind CSS 4** + komponen **shadcn/ui**
- **Framer Motion** (animasi halus, drag-and-drop via `Reorder`)
- **Zustand** + persist (progres tersimpan otomatis)
- **Lucide React** (ikon)

## 📊 Catatan untuk PTK

- Kolom data pada CSV: identitas, skor, status KKTP, jawaban awal vs hasil revisi tiap kartu, kualitas argumen, percobaan final challenge, dan refleksi — siap dilampirkan sebagai instrumen/dokumen observasi.
- Indikator kemampuan pada halaman hasil mengacu pada Tujuan Pembelajaran modul (LOTS C2–C3 dan HOTS C4–C5 serta psikomotor P3).
- Siswa dapat mengulang media setelah reset; pola jawaban pada siklus berikutnya dapat dibandingkan sebagai data siklus PTK.
"# PTKSS" 
