# Prompt untuk Antigravity

Paste ini sebagai instruksi awal, lalu lampirkan/refer ke `design.md`,
`content.md`, dan `structure.md` di folder yang sama.

---

Bangun website portofolio personal dengan konsep **editorial/majalah**
(bukan template SaaS generik, bukan gradient/glassmorphism ala AI).
Ikuti spesifikasi di tiga file berikut secara ketat:

- `structure.md` — stack teknis, struktur folder, dan susunan halaman
- `design.md` — sistem desain: warna, tipografi, layout, spacing, motion
- `content.md` — konten asli tiap section (jangan diparafrase jadi generik,
  pakai persis kalimat yang sudah disiapkan, boleh dirapikan grammar-nya saja)

Prinsip yang WAJIB dipegang sepanjang proses build:

1. Tidak ada gradient, drop shadow berlebihan, blur, atau efek glow
2. Tidak ada card seragam dengan shadow rata — grid harus asimetris
3. Tipografi adalah elemen desain utama, bukan sekadar teks
4. Setiap section proyek punya nomor bab (01, 02, 03) seperti majalah
5. Semua konten pakai data asli dari `content.md`, jangan isi lorem ipsum
   atau placeholder generik
6. Responsive mobile-first, tapi grid asimetris tetap dipertahankan
   (jangan collapse jadi tumpukan card polos di mobile)

Kerjakan bertahap: mulai dari setup project + design tokens (warna/font
sebagai CSS variable), lalu struktur layout per section, baru terakhir
animasi scroll.
