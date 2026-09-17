# My Spotify Player

Web player custom untuk Spotify menggunakan **Spotify Web Playback SDK**. Tanpa iklan, tema bisa diubah (dark/light + custom accent & background color), dan menampilkan top tracks kamu.

## 📁 Struktur Folder

```
spotify_player/
├── index.html      # Seluruh aplikasi (HTML + CSS + JS jadi satu file)
└── README.md       # Dokumentasi ini
```

> Semua kode (markup, style, script) digabung dalam satu file `index.html` agar mudah dijalankan tanpa build tools.

## ⚙️ Fitur

- Player kontrol (play/pause, next, previous)
- Menampilkan cover, judul lagu, dan nama artis yang sedang diputar
- Daftar 5 top tracks (long term) — klik untuk langsung memutar
- Pengaturan tema: mode terang/gelap, warna accent, warna background (tersimpan sementara di sesi browser)
- Slider volume
- Token disimpan di `localStorage` browser (tidak dikirim ke server manapun)

## 🔑 Prasyarat

1. Akun **Spotify Premium** (wajib untuk Web Playback SDK — akun gratis tidak bisa streaming lewat SDK ini).
2. Access Token dari [Spotify Developer Dashboard](https://developer.spotify.com/dashboard) dengan scope berikut:
   - `streaming`
   - `user-read-email`
   - `user-read-private`
   - `user-read-playback-state`
   - `user-modify-playback-state`
   - `user-top-read`

## 🚀 Cara Menjalankan

1. Buka file `index.html` langsung di browser (double click), atau jalankan lewat local server, misalnya:
   ```bash
   npx serve .
   ```
2. Generate access token dari Spotify Developer Dashboard (atau lewat OAuth flow milikmu sendiri).
3. Paste token ke kolom **Spotify Access Token** di aplikasi, lalu klik **Connect Player**.
4. Setelah terhubung, top tracks kamu otomatis dimuat dan bisa langsung diputar.

## ⚠️ Catatan Penting

- Access token dari Spotify **expired dalam ±1 jam**. Jika status menunjukkan "Auth error: token expired", generate token baru dan connect ulang.
- Karena token disimpan di `localStorage`, jangan gunakan di komputer/browser publik.
- Aplikasi ini murni client-side — tidak ada backend/server yang menyimpan data kamu.

## 🛠️ Kustomisasi

- Ubah warna default di variabel CSS `:root` pada bagian `<style>` di `index.html`.
- Untuk menambah fitur (misalnya playlist, search, dsb), tambahkan endpoint baru lewat fungsi `api()` yang sudah ada.
