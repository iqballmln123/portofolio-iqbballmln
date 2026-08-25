# Prompt untuk Antigravity (Gemini)

Copy-paste seluruh isi di bawah ini ke Antigravity.

---

## KONTEKS PROYEK

Aku punya portofolio pribadi yang dibangun dengan stack:
- **Astro** (framework utama)
- **Tailwind CSS** (styling)
- **MDX** (content project di section Works)
- **GSAP** (animasi, sudah terpasang — gunakan `ScrollTrigger` plugin)

Live preview struktur saat ini: https://portofolio-iqbballmln.vercel.app/

Section yang ada saat ini (urutan dari atas): **Hero → About & Journey (Career Milestones) → Works/Projects (case study) → Archive → Experiments → Expertise & Credentials → Contact**.

## ATURAN PALING PENTING — JANGAN DILANGGAR

- **JANGAN ubah, refactor, atau sentuh Hero section sama sekali.** Markup, styling, animasi, dan konten Hero harus tetap 100% seperti semula. Redesign ini hanya berlaku **mulai dari section setelah Hero (About) sampai Contact**.
- Jangan hapus konten/copy yang sudah ada (judul project, deskripsi Masalah/Proses/Hasil, tech stack tags, dll) — fokus ke redesign visual & interaksi, bukan menulis ulang konten.
- Tetap gunakan struktur data project (MDX) yang sudah ada, jangan ubah schema kecuali benar-benar diperlukan untuk fitur baru.

## KONSEP DESAIN YANG DIINGINKAN

**Vibe umum**: parallax scroll yang clean, minimalist, editorial-modern — bukan template generic/jadul (hindari drop-shadow card klasik, grid simetris kaku, fade-in polos tanpa easing).

**Palet warna**: tetap monokrom (hitam, putih, abu-abu), dengan **background dasar putih/off-white** (bukan gelap/hitam) di semua section dari About sampai Contact. Detail:
- Background utama: off-white (`#FAFAF7`, sedikit warm) — bukan pure `#FFFFFF` biar terasa "paper" bukan "screen"
- Teks & heading: off-black (`#0A0A0A`)
- Tambahkan 4–5 step abu (contoh: `#E4E3DC` border, `#8A8980` secondary text, `#6B6A63` body muted) untuk border, secondary text, divider
- Tambahkan subtle grain/noise texture di background supaya tidak terasa flat kosong
- Tambahkan cursor-follow radial gradient/spotlight sangat halus (abu-abu tipis, opacity rendah) — opsional, progressive enhancement, jangan bikin section jadi gelap
- Section boleh punya card dengan background putih murni (`#FFFFFF`) di atas base off-white untuk memberi sedikit depth/layer, tapi keseluruhan tone tetap terang

**Font**: ganti/tambahkan Google Fonts atau variable fonts berikut lewat Tailwind config:
- Heading/display: **Fraunces** (variable serif, editorial tapi modern)
- Body/UI text: **Inter** atau **Geist**
- Label kecil/eyebrow (angka section, tag): **JetBrains Mono** atau **Space Mono**

## IMPLEMENTASI PARALLAX PER SECTION

Gunakan **GSAP ScrollTrigger** untuk semua efek scroll di bawah ini. Pastikan performant (gunakan `will-change`, hindari layout thrashing, gunakan `transform`/`opacity` saja untuk animasi).

### 1. About & Journey (Career Milestones)
- Ubah dari layout statis jadi **pinned horizontal scroll**: section di-pin (`pin: true`) di viewport, scroll vertikal user diterjemahkan jadi pergerakan horizontal antar milestone card (2023–2026 → Present & Future)
- Angka besar "01/02/03" bergerak dengan parallax speed berbeda (lebih lambat) dibanding card di depannya untuk efek depth
- Quote "Lulusan D3..." muncul dengan text reveal per baris (animasi clip-path/mask), bukan langsung muncul semua sekaligus
- 3 "Core Engineering Pillars" cards muncul dengan stagger reveal saat masuk viewport

### 2. Works/Projects
- Ganti tampilan galeri gambar project jadi pattern **sticky image, scrolling text**: gambar project di-pin di satu sisi (kanan di desktop), sementara deskripsi (Masalah/Proses/Hasil) scroll normal di sisi lain
- Transisi antar project (Telkomsel App → SiTanam → Smart MCB → GlowUp) menggunakan **stacked card effect** — card project berikutnya menutup card sebelumnya saat di-scroll (seperti efek Stripe/Linear), bukan potongan section biasa
- Tech stack tags per project ditampilkan sebagai **marquee/infinite scroll horizontal** tipis
- Di mobile: sticky image berubah jadi gambar biasa di atas teks (parallax tetap ada tapi disederhanakan, lihat catatan responsive di bawah)

### 3. Skills/Expertise
- Ubah grid jadi **bento grid asimetris** (bukan kotak-kotak sama besar) — 1 card besar untuk pillar utama (Mobile App Development & IoT), sisanya lebih kecil
- Hover state pakai perubahan border/background halus, **jangan pakai box-shadow**

### 4. Contact
- Judul "Ready to create impact?" ditampilkan sebagai **kinetic typography** — teks bergerak/skew halus mengikuti kecepatan scroll (scroll velocity-based transform)
- Tombol email & LinkedIn menggunakan **magnetic button effect** (tombol tertarik ke arah cursor saat didekati)

## KEBUTUHAN TEKNIS TAMBAHAN

- **Accessibility**: hormati `prefers-reduced-motion` — matikan/kurangi parallax & animasi berat untuk user yang mengaktifkan setting ini
- **Responsive**: semua efek parallax harus tetap smooth dan tidak merusak layout di mobile (viewport sempit) — sederhanakan efek horizontal-scroll/pinning jika perlu di breakpoint mobile
- **Performance**: pastikan tidak ada jank; gunakan `ScrollTrigger.batch()` atau `scrub` sesuai kebutuhan, lazy-load gambar besar
- Pertahankan SEO meta tags dan struktur heading (h1/h2/h3) yang sudah ada

## DELIVERABLE

Implementasikan perubahan ini langsung ke file Astro/Tailwind/GSAP yang relevan di project. Jelaskan singkat file apa saja yang diubah dan bagian mana yang ditambahkan (khususnya konfigurasi font di `tailwind.config` dan setup GSAP ScrollTrigger baru).
