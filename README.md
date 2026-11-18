# Scan Kraepelin - proyek APK Android (Capacitor)

Aplikasi: kamera memindai dua angka (atas dan bawah), hasil penjumlahan
(digit terakhir) ditampilkan. Tanpa keypad. Berjalan offline.

## Syarat (di komputer Anda, perlu internet saat build)
- Node.js 18+
- JDK 17
- Android SDK (paling mudah: pasang Android Studio, lalu set ANDROID_HOME)

## Langkah build
```
npm install
npm run setup     # salin aset offline, buat proyek android, tambah izin kamera
npm run apk       # build APK debug
```
Hasil: `android/app/build/outputs/apk/debug/app-debug.apk`
(Windows: jalankan `cd android` lalu `gradlew.bat assembleDebug`.)

Alternatif: `npm run open` untuk membuka di Android Studio, lalu
Build > Build APK(s).

## Pasang di HP
Salin app-debug.apk ke HP, izinkan "install dari sumber tidak dikenal", lalu buka.
Saat pertama dibuka, izinkan akses kamera.

## Ubah tampilan/logika
Edit `www/index.html`, lalu `npm run sync` dan `npm run apk` lagi.

## Catatan
- Ini APK debug (untuk pemakaian pribadi). Untuk Play Store perlu build release
  yang ditandatangani (signed).
- Akurasi baca angka terbaik dengan cahaya cukup dan angka tercetak jelas.

## Build APK otomatis tanpa memasang apa pun (GitHub Actions)
1. Buat repositori baru di github.com (boleh private).
2. Unggah SEMUA isi folder ini (termasuk folder tersembunyi `.github`).
   Cara mudah: di halaman repo pilih "uploading an existing file", seret semua isi folder.
   Pastikan file `.github/workflows/build-apk.yml` ikut terunggah.
3. Buka tab **Actions** > **Build APK** > **Run workflow** (atau tunggu otomatis setelah upload).
4. Setelah selesai (sekitar 5-8 menit), buka run tersebut, bagian **Artifacts**,
   unduh `kraepelin-scan-apk` (berisi app-debug.apk).
