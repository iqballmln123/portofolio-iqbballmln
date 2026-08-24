# Structure — stack & susunan halaman

## Stack teknis

- **Astro** — static site generator, ship JS minimal
- **Tailwind CSS** — utility styling, dikombinasikan dengan CSS variable
  custom untuk design tokens (lihat `design.md`)
- **MDX** — untuk konten proyek (tiap proyek = satu file `.mdx`,
  campur teks + komponen visual)
- **React** (opsional, via Astro island) — hanya untuk bagian interaktif
  kecil, misal galeri gambar atau counter angka
- **GSAP + ScrollTrigger** — animasi reveal saat scroll
- Deploy: **Vercel** atau **Netlify**

## Struktur folder (Astro)

```
src/
  components/
    Hero.astro
    Journey.astro
    ProjectCard.astro
    SkillList.astro
    Contact.astro
    ChapterNumber.astro      # komponen kecil untuk nomor bab (01, 02, ...)
  content/
    projects/
      coverage-report-automator.mdx
      penyiraman-tanaman.mdx
      smart-mcb.mdx
  layouts/
    BaseLayout.astro
  pages/
    index.astro
  styles/
    tokens.css               # CSS variable warna, font, spacing
    global.css
public/
  images/
    projects/                # screenshot & diagram asli, bukan stok foto
```

## Susunan halaman (single page, scroll)

1. **Hero** — nama, satu kalimat identitas, nomor bab "01"
2. **Journey** — ringkasan perjalanan karier dalam 1 paragraf naratif
3. **Proyek** (3 entri, masing-masing nomor bab sendiri: 02, 03, 04)
   - Tiap proyek: masalah → proses → hasil, dengan screenshot/diagram asli
4. **Skill & tools** — dikelompokkan per kategori (bukan progress bar)
5. **Kontak** — email, LinkedIn, CTA sederhana, nomor bab penutup

## Catatan build

- Tiap section punya `id` untuk anchor scroll (`#journey`, `#projects`, dst)
- Gambar proyek wajib pakai aset asli (screenshot Coverage Report Automator,
  diagram Smart MCB, foto/dashboard PenyiramanTanaman) — jangan generate
  gambar AI atau pakai stok foto
- Mobile: grid asimetris tetap dipakai, tapi rasio kolom disesuaikan
  (misal 1.3fr/1fr desktop → stack dengan urutan foto-di-atas di mobile)
