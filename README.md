# Visualisasi Kapal Phinisi 3D

Aplikasi web interaktif untuk visualisasi dan eksplorasi kapal Phinisi dalam lingkungan 3D dengan air dan langit dinamis.

## 📋 Daftar Isi

- [Fitur](#fitur)
- [Persyaratan](#persyaratan)
- [Instalasi](#instalasi)
- [Cara Menjalankan](#cara-menjalankan)
- [Cara Menggunakan](#cara-menggunakan)
- [Kontrol](#kontrol)
- [Struktur Proyek](#struktur-proyek)
- [Teknologi](#teknologi)

## ✨ Fitur

- **Visualisasi Kapal Phinisi 3D** - Model GLTF kapal Phinisi dengan detail hull, bow, 3 masts, dan sails
- **Air Dinamis** - Simulasi air dengan gelombang yang bergerak menggunakan Water shader
- **Langit Realistis** - Sky shader dengan kontrol azimuth dan elevation untuk simulasi waktu
- **Siklus Siang-Malam** - Simulasi dari pagi hingga malam dengan langit berbintang
- **Kontrol Interaktif** - Orbit controls untuk mengeksplorasi scene dari berbagai sudut
- **Mode Kontrol Kapal** - Kontrol kapal dengan keyboard WASD untuk simulasi pelayaran mini
- **Camera Following** - Kamera otomatis mengikuti kapal saat mode kontrol aktif
- **Marker Interaktif 3D** - Tiga marker yang dapat diklik untuk melihat informasi bagian kapal:
  - Marker Layar (hijau) - Informasi tentang layar Phinisi
  - Marker Body (biru) - Informasi tentang badan kapal
  - Marker Bulukumba (orange) - Informasi tentang kampung halaman Phinisi
- **Modal Popup Informasi** - Popup edukatif dengan detail tentang bagian-bagian kapal
- **Sistem Audio** - Background music dengan kontrol play/pause yang dapat di-toggle
- **GUI Kontrol** - Interface untuk mengatur parameter sky dan water secara real-time
- **Lighting Dinamis** - Pencahayaan berbasis sun position yang dapat diubah
- **Stats Monitor** - Display FPS dan memory usage untuk monitoring performa

## 📦 Persyaratan

- Node.js (v14 atau lebih tinggi)
- npm (biasanya sudah termasuk dengan Node.js)
- Browser modern yang mendukung WebGL (Chrome, Firefox, Safari, Edge)

## 🚀 Instalasi

1. **Navigasi ke folder proyek:**

   ```bash
   cd "D:\Fauzih\Kuliah\SEMESTER III\Grafika\Big Project\Kapal-Phinisi"
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

## ▶️ Cara Menjalankan

1. **Jalankan development server:**

   ```bash
   npm run dev
   ```

2. **Buka browser dan akses:**

   ```
   http://localhost:8080
   ```

3. **Tunggu hingga scene terbuka.** Anda akan melihat kapal di atas air dengan langit yang indah.

4. **Untuk stop server**, tekan `Ctrl + C` di terminal.

## 🎮 Cara Menggunakan

### Navigasi Scene

- **Rotasi Camera:**

  - Klik kanan dan drag mouse untuk merotasi view
  - Atau gunakan scroll wheel dengan drag

- **Pan Camera:**

  - Klik kiri dan drag mouse untuk pan scene

- **Zoom:**

  - Scroll mouse wheel ke atas untuk zoom in
  - Scroll mouse wheel ke bawah untuk zoom out
  - Zoom distance: 40-200 units

- **Reset View:**
  - Double-click untuk reset camera position

### Kontrol Parameter (GUI Panel)

Di sudut kanan atas, ada panel kontrol dengan folder "Sky" dan "Water":

**Sky Folder:**

- **Elevation** (0-90): Mengatur ketinggian matahari
  - 0° = matahari di horizon
  - 90° = matahari di zenith
- **Azimuth** (-180 hingga 180): Mengatur arah matahari (derajat)
  - 0° = utara
  - 90° = timur
  - 180° atau -180° = selatan
  - -90° = barat

**Water Folder:**

- **Distortion Scale** (0-8): Mengatur intensitas distorsi gelombang air
  - Nilai lebih tinggi = gelombang lebih kasar
- **Size** (0.1-10): Mengatur skala/ukuran wave pattern

### Marker Interaktif

Aplikasi dilengkapi dengan **3 marker interaktif** yang dapat diklik untuk melihat informasi edukatif:

- **Marker Hijau (Layar)**: Klik untuk melihat informasi tentang layar kapal Phinisi
- **Marker Biru (Body)**: Klik untuk melihat informasi tentang badan kapal
- **Marker Orange (Bulukumba)**: Klik untuk melihat informasi tentang kampung halaman Phinisi

**Cara menggunakan:**

1. Arahkan mouse ke salah satu marker (bola berwarna di atas kapal)
2. Klik pada marker untuk membuka modal informasi
3. Baca detail informasi yang ditampilkan
4. Klik tombol `×` atau klik di luar modal untuk menutup

Marker akan beranimasi dengan **pulsing effect** untuk memudahkan identifikasi.

### Mode Kontrol Kapal (Ship Control Mode)

Aplikasi memiliki **mode simulasi mini** untuk menggerakkan kapal:

**Mengaktifkan Mode Kontrol:**

- Klik tombol **🎮** di kanan bawah layar
- Border tombol akan berubah hijau menandakan mode aktif
- OrbitControls akan nonaktif saat mode ini aktif

**Kontrol Keyboard:**

- **W** = Gerakkan kapal maju (forward)
- **S** = Gerakkan kapal mundur (backward)
- **A** = Putar kapal ke kiri (turn left)
- **D** = Putar kapal ke kanan (turn right)

**Fitur Camera Following:**

- Kamera akan otomatis mengikuti kapal dari sisi kanan
- Smooth lerp animation untuk pergerakan kamera yang halus
- Camera lock pada posisi kapal

**Menonaktifkan Mode Kontrol:**

- Klik tombol **🎮** lagi
- Kapal akan berhenti bergerak
- OrbitControls akan aktif kembali

### Kontrol Audio

**Toggle Background Music:**

- Klik tombol **🔇** / **🔊** di kanan bawah layar
- **🔊** = Audio sedang playing
- **🔇** = Audio sedang muted/paused

**Catatan:**

- Audio akan mencoba auto-play saat aplikasi dibuka
- Jika browser memblokir auto-play, klik pada layar atau tombol audio untuk memulai
- Volume default: 50%

### Animasi Otomatis

- Kapal bergerak **naik-turun** secara otomatis dengan sinusoidal motion (bobbing effect)
- Marker 3D ber-**pulse** secara terus menerus untuk menarik perhatian
- Air terus beranimasi dengan gelombang yang mengalir

## 🔧 Teknologi
- **Three.js** (v0.182.0) - Library WebGL untuk rendering 3D
- **OrbitControls** - Mouse controls untuk navigasi camera
- **Water Shader** - Efek air dengan normal mapping
- **Sky Shader** - Realistic sky rendering
- **Stats.js** - Monitor performance (FPS, memory)
- **lil-gui** - GUI panel untuk kontrol parameter
- **http-server** - Simple development server
--

## 🏗️ Struktur Proyek

```
three/
├── build/              # Build hasil kompilasi (file three.*.js)
├── examples/           # Contoh scene dan resource
├── src/                # Modul sumber dan implementasi
├── index.html          # File HTML utama (entry)
├── main.css            # Styling / CSS
├── package.json        # Konfigurasi npm dan skrip
├── README.md           # Berkas dokumentasi ini
└── LICENSE             # Lisensi proyek
```

## 💡 Tips Penggunaan

1. **Untuk melihat kapal dengan lebih baik:**

   - Gerakkan camera dengan rotasi kanan-click
   - Zoom in/out untuk melihat detail
   - Coba posisi dari berbagai sudut

2. **Untuk hasil visual terbaik:**

   - Coba elevation 45° untuk cahaya yang balanced
   - Gunakan azimuth 180° untuk mengarahkan cahaya ke kapal
   - Set distortion scale 3-4 untuk gelombang yang natural

3. **Eksplorasi fitur edukatif:**

   - Klik semua 3 marker untuk mempelajari bagian-bagian kapal
   - Marker akan berpulse - klik untuk membuka informasi detail
   - Modal popup berisi informasi edukatif tentang kapal Phinisi

4. **Mode simulasi kapal:**

   - Aktifkan mode kontrol dengan tombol 🎮
   - Gunakan WASD untuk "berlayar" di lautan
   - Camera akan otomatis mengikuti dari samping
   - Nonaktifkan untuk kembali ke mode eksplorasi bebas

5. **Audio experience:**

   - Aktifkan audio untuk pengalaman lebih immersive
   - Jika tidak auto-play, klik tombol 🔇 untuk memulai
   - Background music menambah suasana pelayaran

6. **Performance:**
   - Monitor FPS di sudut kiri atas
   - Jika FPS rendah, kurangi window size atau distortion scale
   - Browser modern (Chrome, Firefox baru) akan memberikan performa terbaik
   - Nonaktifkan ship controls saat tidak digunakan untuk performa optimal

## 🐛 Troubleshooting

**Masalah: Server tidak bisa diakses**

- Pastikan terminal menjalankan `npm run dev` tanpa error
- Cek apakah port 8080 sudah terpakai, jika ya ubah di package.json
- Coba akses `http://127.0.0.1:8080` jika localhost tidak bekerja

**Masalah: Scene blank/tidak ada yang muncul**

- Refresh browser (Ctrl+F5)
- Cek console browser (F12) untuk error message
- Pastikan GPU mendukung WebGL

**Masalah: Performa lambat**

- Tutup aplikasi lain yang berat
- Kurangi ukuran window
- Matikan shadow rendering jika diperlukan

## 📝 Catatan

- Kapal dibuat secara procedural menggunakan Three.js geometries
- Texture air dibuat secara dinamis dari canvas
- Semua elemen 3D di-render real-time tanpa pre-baked assets

---

**Dibuat untuk**: Tugas Besar Grafika Komputer - Semester III
**Tahun**: 2025

**Kelompok 7**: Nama Anggota:

- Fauzih Falih
- Asmir
- Endro Novrianto
- Glorifair S. Bamba
