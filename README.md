# DogeRat (Educational Device Management Toolkit)

![logo](images/logo.PNG)

> **Peringatan penting:** Proyek ini **hanya** untuk tujuan edukasi, pengujian keamanan pada perangkat milik Anda sendiri, atau untuk demonstrasi dalam lingkungan laboratorium dengan izin tertulis dari pemilik perangkat. Penggunaan untuk mengakses, memata-matai, atau merusak perangkat orang lain tanpa izin adalah **ilegal** dan **tidak etis**.

---

<p align="center">
  <img src="images/4.jpg" alt="Panel Screenshot" style="max-width: 100%; height: auto;" />
</p>

## Tentang Proyek
DogeRat (nama proyek) adalah **contoh** toolkit edukasi yang menunjukkan bagaimana mekanisme komunikasi antara server dan aplikasi Android dapat bekerja untuk tujuan **manajemen perangkat yang sah**. Tujuan dokumen ini adalah memberikan materi pembelajaran tentang arsitektur, teknik komunikasi waktu-nyata, dan praktik keamanan — **bukan** untuk melakukan penyalahgunaan.

**Komponen utama (edukasi):**
- **Server:** Node.js + Express + Socket.IO (untuk komunikasi real-time, demo)
- **Android app:** Kotlin (contoh arsitektur klien-server tanpa fitur invasif)

---

## Prinsip Etika & Kepatuhan
Sebelum menggunakan atau menguji alat ini, pastikan:
1. Anda memiliki *izin tertulis* dari pemilik perangkat.
2. Pengujian dilakukan pada perangkat milik sendiri atau di lingkungan pengujian yang terkontrol.
3. Anda mematuhi hukum lokal dan kebijakan organisasi.
4. Semua data sensitif dienkripsi atau dimock saat mendemonstrasikan alur kerja.
5. Tidak ada fungsi tersembunyi yang menyalahgunakan akses.

---

## Fitur (Contoh Aman / Administratif)
> Fitur berikut difokuskan pada manajemen perangkat yang legal dan etis — contoh untuk penggunaan enterprise / lab:

- Real-time device status (online/offline)
- Inventaris aplikasi terpasang (nama & versi saja)
- Notifikasi push terjadwal (untuk admin, bukan spoofing)
- Menampilkan informasi perangkat dasar (model, OS, kapasitas; tanpa data pribadi)
- Pengiriman pesan administratif ke perangkat (dengan persetujuan)
- Kemampuan remote lock / factory-reset **hanya** pada perangkat milik organisasi dan setelah prosedur otorisasi
- Logging aktivitas untuk audit (disimpan terpusat dan terenkripsi)
- Mekanisme otentikasi dan otorisasi tingkat lanjut (OAuth2 / JWT)
- Mode demo yang men-simulasikan fitur sensitif tanpa akses real

> **Catatan:** Fitur seperti perekaman mikrofon, pengambilan gambar kamera, keylogging, pengiriman SMS tanpa persetujuan, atau injeksi halaman phishing **tidak disertakan** pada implementasi aman ini.

---

## Bagan Arsitektur (High-level)
- Client (Android) ↔ Server (Socket.IO / REST)
- Database (mis. PostgreSQL / MongoDB) untuk penyimpanan metadata perangkat
- Dashboard web (React / Vue) untuk admin — menampilkan inventaris & log
- Mekanisme enkripsi TLS untuk semua koneksi

---

## Instalasi (Lingkungan Pengembangan)
> Petunjuk ini hanya untuk menyiapkan lingkungan dev — **tidak** berisi instruksi deploy ke tujuan ilegal.

### Prasyarat
- Node.js (LTS)
- Java + Android SDK (untuk build app)
- Kotlin (untuk kode Android)
- Git, npm/yarn

### Server (contoh)
```bash
git clone https://github.com/your-repo/example-device-manager.git
cd example-device-manager/server
npm install
cp .env.example .env
# isi variabel lingkungan (DB, SECRET_KEY, dll.) dengan nilai lokal/dev
npm run dev