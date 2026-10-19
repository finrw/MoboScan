# Mobo Scan — PWA

Versi Progressive Web App dari [finrw.github.io/MoboScan](https://finrw.github.io/MoboScan/).

## Yang ditambahkan

| File | Fungsi |
|------|--------|
| `manifest.json` | Nama app, icon, tampilan standalone (seperti app native) |
| `sw.js` | Service Worker — cache shell + bisa install offline |
| `icons/` | Icon 192 & 512 (any + maskable) |
| `index.html` | Link manifest + registrasi SW |

**Catatan:** Call ke Google Apps Script (`script.google.com`) **tidak di-cache** (selalu network), biar data spreadsheet tetap live.

## Cara deploy ke GitHub Pages (repo kamu)

1. Clone / buka repo `finrw/MoboScan`
2. Ganti isi folder root dengan file-file di folder `mobo-scan-pwa` ini:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - folder `icons/` (isi 4 PNG)
3. Commit & push ke branch `main` (atau branch yang dipakai GitHub Pages)
4. Buka https://finrw.github.io/MoboScan/ di Chrome/Android
5. Menu browser → **Install app** / **Add to Home screen**

## Cara install di HP

### Android (Chrome)
1. Buka URL app
2. Muncul banner “Install” atau menu ⋮ → **Install app** / **Add to Home screen**
3. App muncul di drawer seperti aplikasi biasa (tanpa address bar)

### iPhone (Safari)
1. Buka URL di Safari
2. Tap tombol Share → **Add to Home Screen**
3. Ikon muncul di home screen

## Offline

- UI app (HTML/CSS/icon) bisa dibuka offline setelah pernah dibuka sekali.
- Scan kamera + simpan ke Spreadsheet **butuh internet** (kamera + API Google).
- Salinan lokal di perangkat tetap tersedia offline (menu Data).

## Testing lokal

```bash
# dari folder ini
npx serve .
# atau
python3 -m http.server 8080
```

Buka `http://localhost:8080` — install PWA hanya jalan di localhost atau HTTPS.
