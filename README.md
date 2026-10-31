# Jellyfish Master — build otomatis EXE dan APK

Folder:
- `app/index.html`  : aplikasimu (ganti file ini kalau ada versi baru)
- `desktop/`        : pembungkus Electron (Windows .exe)
- `mobile/`         : pembungkus Capacitor (Android .apk)
- `.github/workflows/build.yml` : resep build otomatis

## Cara pakai
1. Buat akun di github.com (gratis), lalu buat repositori baru (**New repository**).
2. Upload SEMUA isi folder ini ke repositori (**Add file > Upload files**, drag folder-foldernya).
   Pastikan folder `.github` ikut ter-upload. Kalau tidak ikut, buat manual:
   **Add file > Create new file**, ketik nama `.github/workflows/build.yml`, lalu tempel isi file itu.
3. Buka tab **Actions**. Build jalan otomatis (sekitar 5-10 menit). Kalau tidak jalan, pilih
   "Build EXE dan APK" > **Run workflow**.
4. Setelah hijau, klik build-nya, scroll ke **Artifacts**, unduh:
   - `Jellyfish-Windows-EXE`  (berisi installer dan versi portable)
   - `Jellyfish-Android-APK`  (berisi app-debug.apk)

## Memasang
- Windows: jalankan installer `.exe` (atau versi portable tanpa install). Jika muncul peringatan
  SmartScreen: "More info" > "Run anyway" (karena aplikasi belum bertanda tangan digital).
- Android: kirim `app-debug.apk` ke HP, buka, izinkan "Install dari sumber tidak dikenal".
  Google Play Protect mungkin memberi peringatan karena ini APK debug; pilih "Install anyway".

## Catatan
- Aplikasi berjalan 100% offline. Font Google tidak dimuat offline, tampilan memakai font sistem.
- APK ini versi debug: cukup untuk pemakaian pribadi, tapi tidak bisa diunggah ke Play Store.
- Untuk Mac (.dmg), tambahkan job `macos-latest` serupa; minta saja kalau perlu.
