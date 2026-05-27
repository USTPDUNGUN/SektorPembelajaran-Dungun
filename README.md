# Sektor Pembelajaran PPD Dungun

Landing page interaktif menggunakan HTML, CSS dan JavaScript vanilla.

## Fungsi

- Paparan umum sektor dan paparan mengikut unit
- Carian maklumat
- Borang tambah maklumat
- Pautan atau dokumen boleh dipautkan melalui URL
- Sokongan Firebase Realtime Database
- Fallback offline menggunakan `localStorage`

## Setup Firebase Realtime Database

1. Buka [Firebase Console](https://console.firebase.google.com/).
2. Create project baharu.
3. Tambah Web App.
4. Salin Firebase config yang diberi.
5. Tampal nilai config ke dalam `firebase-config.js`.
6. Buka Realtime Database dan create database.
7. Path data yang digunakan ialah `sectorInfo`.

Contoh `firebase-config.js`:

```js
window.PPD_FIREBASE_CONFIG = {
  apiKey: "ISI_API_KEY",
  authDomain: "project-id.firebaseapp.com",
  databaseURL: "https://project-id-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "project-id",
  storageBucket: "project-id.appspot.com",
  messagingSenderId: "ISI_SENDER_ID",
  appId: "ISI_APP_ID"
};

window.PPD_FIREBASE_COLLECTION = "sectorInfo";
```

Rules asas Realtime Database untuk ujian:

```json
{
  "rules": {
    "sectorInfo": {
      ".read": true,
      ".write": true
    }
  }
}
```

Untuk production, tukar rules supaya hanya pengguna dibenarkan boleh tambah/padam maklumat.

## Publish ke GitHub Pages

1. Create repository baharu di GitHub.
2. Upload semua fail dalam folder ini.
3. Pergi ke Settings > Pages.
4. Pilih Deploy from a branch.
5. Branch: `main`, folder: `/root`.
6. Save dan tunggu URL GitHub Pages dijana.

## Jalankan secara lokal

```bash
python3 -m http.server 4173
```

Kemudian buka:

```txt
http://localhost:4173
```
