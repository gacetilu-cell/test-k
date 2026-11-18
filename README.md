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
