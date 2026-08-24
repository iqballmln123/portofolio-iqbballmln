# Design — sistem visual

## Prinsip

Editorial, bukan SaaS landing page. Referensi rasa: majalah cetak /
digital magazine (Kinfolk, Monocle) yang dipindah ke web — bukan
dashboard, bukan template "AI slop" (gradient ungu-biru, card rounded
seragam, hero simetris dengan blob 3D).

Hindari sama sekali: gradient, drop shadow tebal, glassmorphism,
blur/glow, tombol rounded-full, font Inter sebagai satu-satunya font.

## Tipografi

Tiga peran font, tiap peran font berbeda:

- **Headline (serif tebal)** — untuk nama, judul section, pull quote.
  Contoh pilihan: `Fraunces`, `Newsreader`, atau `Playfair Display`.
- **Body (sans netral)** — untuk paragraf. Contoh: `Inter` atau
  `Söhne` — ukuran nyaman baca, line-height longgar (1.6–1.7).
- **Mono (monospace)** — untuk metadata: nomor bab, tanggal, label,
  caption gambar. Contoh: `JetBrains Mono` atau `IBM Plex Mono`.
  Ini elemen penting yang membedakan dari template generik — nyambung
  ke identitas teknikal/IoT.

Skala ukuran (contoh, sesuaikan proporsi):
- Headline utama: 40–56px, line-height 1.1
- Judul section: 24–32px
- Body: 16–18px
- Metadata/mono: 12–13px, letter-spacing sedikit lebar

## Warna

Base: **off-white/cream**, bukan putih polos (misal `#F7F4EC`).
Satu warna aksen kuat, pilih salah satu arah:

- **Arah signal/telco**: hijau sinyal `#1D9E75` atau biru jaringan `#185FA5`
- **Arah industrial**: rust/amber `#BA7517` atau steel grey `#5F5E5A`

Teks utama: hitam-hangat (bukan `#000` pekat), misal `#2C2C2A`.
Teks sekunder: abu-hangat, misal `#5F5E5A`.

Aturan: aksen dipakai konsisten hanya untuk nomor bab, link, dan satu
elemen highlight per section — bukan disebar ke banyak elemen sekaligus.

## Layout & grid

- Grid **asimetris**, bukan card sejajar rata. Contoh pola: kolom foto
  proyek 1.3fr berdampingan dengan kolom teks 1fr, posisi bisa
  ditukar antar section (foto kiri di satu proyek, kanan di proyek lain)
- Elemen boleh sedikit "keluar" dari margin standar untuk foto besar
- Setiap section utama diberi nomor bab format `01 —`, `02 —`, dst,
  di-style pakai font mono, warna aksen
- Whitespace generous — jangan padatkan section berdekatan
- Border tipis (0.5–1px) sebagai pemisah, bukan shadow

## Detail yang bikin terasa "dibuat manusia"

- Pull quote di tengah satu section, pakai font headline italic
- Byline kecil di footer: "Ditulis & dibangun oleh Iqbal, Agustus 2026"
- Caption kecil di bawah tiap gambar (font mono, italic opsional)
- Hover state pada link/nomor bab: underline tipis atau shift warna,
  bukan efek scale/glow

## Motion

- Reveal on scroll pakai GSAP ScrollTrigger: fade + translateY kecil
  (16–24px), durasi 0.5–0.7s, easing `power2.out`
- Jangan pakai animasi bounce/elastic — kesan majalah itu tenang, presisi
- Parallax halus opsional untuk gambar besar di hero/proyek (jangan berlebihan)
