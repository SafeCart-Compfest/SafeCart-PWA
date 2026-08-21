# SafeCart

Mobile-first progressive web app untuk SafeCart.

SafeCart PWA hanya berkomunikasi dengan `SafeCart-API`. Aplikasi ini tidak boleh memanggil `SafeCart-AI` atau `SafeCart-ScrapingData` secara langsung.

## Teknologi

- React dan TypeScript
- Vite
- TanStack Router
- TanStack Query
- Zod
- Vite PWA

TanStack Router, TanStack Query, dan Zod sudah dipasang sebagai fondasi. Integrasinya akan dilakukan pada tahap pengembangan aplikasi berikutnya.

## Prasyarat

- Node.js `20.19+` atau `22.12+`
- npm

## Setup lokal

1. Clone repository dan masuk ke folder project.

   ```bash
   git clone https://github.com/SafeCart-Compfest/SafeCart-PWA.git
   cd SafeCart-PWA
   ```

2. Instal dependency.

   ```bash
   npm install
   ```

3. Buat file environment lokal dari template.

   PowerShell:

   ```powershell
   Copy-Item .env.example .env
   ```

   macOS/Linux:

   ```bash
   cp .env.example .env
   ```

   Untuk saat ini belum ada environment variable yang wajib diisi, sehingga `.env.example` sengaja dibiarkan kosong.

4. Jalankan development server.

   ```bash
   npm run dev
   ```

   Buka alamat yang ditampilkan Vite, biasanya `http://localhost:5173`.

## Environment variables

- Simpan konfigurasi lokal di `.env`.
- Dokumentasikan nama variabel yang diperlukan di `.env.example` tanpa memasukkan nilainya.
- Hanya variabel berawalan `VITE_` yang tersedia di aplikasi browser.
- Jangan menyimpan API key, password, token, atau secret backend dalam variabel `VITE_`.

## Pengujian PWA

Service worker digunakan pada production build. Untuk mengujinya:

```bash
npm run build
npm run preview
```

Buka alamat preview, biasanya `http://localhost:4173`, lalu periksa `Application > Manifest` dan `Application > Service Workers` melalui browser DevTools.

Icon, warna, dan metadata visual PWA akan ditambahkan setelah design system SafeCart selesai.

## Script

| Perintah | Kegunaan |
| --- | --- |
| `npm run dev` | Menjalankan development server |
| `npm run build` | Memeriksa TypeScript dan membuat production build |
| `npm run lint` | Menjalankan ESLint |
| `npm run preview` | Menjalankan production build secara lokal |
