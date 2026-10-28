# SIM-HALAL FATAYAT NU DESA MERSI (Sains Data untuk Masyarakat)
> **Portal Monitoring & Dashboard Mandiri Kesiapan Audit Sertifikasi Halal BPJPH (Jalur Self-Declare)**  
> *Pimpinan Ranting Fatayat Nahdlatul Ulama Desa Mersi, Purwokerto Timur, Kabupaten Banyumas*

---

## 🌟 Fitur Utama Terbaru

### 1. 👩‍💼 Dashboard Mandiri per Anggota UMKM (Tab 2)
Dirancang khusus agar setiap anggota Fatayat NU dapat memeriksa dan memantau status sertifikasi halalnya secara mandiri:
- **Sambutan Hangat Personal**: Identitas pelaku usaha, nama merek, kategori produk, kontak WA, alamat dapur, dan nomor NIB.
- **Pelacak Milestone Halal Journey (Syarat Sertifikasi Udah Sampai Mana Aja?)**:
  - Alur 5 tahapan kesiapan visual:
    1. *Legalitas Usaha & KBLI* (KTP, NIB OSS, KBLI Pangan)
    2. *Bahan Baku & Bumbu* (Positive List & Bukti Sertifikat Halal)
    3. *Alur Proses & Dapur* (Sanitasi, Pemisahan Alat & SOP SJPH)
    4. *Penyelia & Ikrar Materai* (SDM Muslim & Komitmen Halal)
    5. *Pengajuan Akun SIHALAL* (ptsp.halal.go.id & Submit BPJPH)
- **Komparasi 2 Kolom Transparan**:
  - **Kolom Kiri (Hijau) - Sudah Terlaksana & Terverifikasi [V]**: Menampilkan rincian butir syarat yang telah lengkap dan valid.
  - **Kolom Kanan (Merah/Amber) - Belum Terlaksana & Perlu Dilengkapi [X]**: Menampilkan daftar butir dokumen yang masih kurang beserta instruksi tindakan nyata untuk memenuhinya.
- **Matriks 4 Pilar Checklist Lengkap (18 Indikator)**: Interaktif dan dapat diklik untuk simulasi audit secara langsung.
- **Action Box & Integrasi Cepat**:
  - Cetak Lembar Hasil Audit Mandiri format A4 PDF resmi.
  - Konsultasi langsung ke WhatsApp Pendamping Halal PPH Fatayat NU.

### 2. 🖨️ Kartu Metrik KPI Interaktif & Cetak Berkas Rekapitulasi (Tab 1)
Keempat kartu metrik KPI di Tab Ringkasan kini berfungsi sebagai tombol interaktif:
1. **Siap Daftar (Skor ≥ 80% / 14 Usaha)**: Klik kartu untuk membuka modal daftar pelaku usaha yang siap diajukan ke BPJPH, lengkap dengan tombol **"Cetak / Unduh Berkas Rekap (PDF)"** untuk arsip nominasi.
2. **Perlu Pendampingan (Skor 50-79% / 22 Usaha)**: Klik kartu untuk membuka daftar usaha yang memerlukan bimbingan teknis dokumen, lengkap dengan tombol cetak agenda pendampingan.
3. **Belum Siap (Skor < 50% / 9 Usaha)**: Klik kartu untuk membuka daftar usaha sasaran fasilitasi legalitas dasar (NIB OSS-RBA di Balai Desa), lengkap dengan tombol cetak target fasilitas.
4. **Total Terdata (45 Usaha)**: Klik kartu untuk membuka dan mencetak rekapitulasi seluruh pelaku usaha anggota.

Setiap cetakan grup memuat **Kop Surat Resmi PR Fatayat NU Desa Mersi** dan kolom tanda tangan 3 pihak (Koordinator Pendamping PPH, Sekretaris, dan Ketua Ranting).

---

## 🏛️ Arsitektur Sistem: Object-Oriented Programming (OOP) & Clean Code

Aplikasi mengimplementasikan prinsip **Clean Architecture & OOP**:

```
e:\SDUM/
├── index.html                      # Main View Entrypoint (HTML5 Semantik & Resilient)
├── buka-aplikasi.bat               # Shortcut 1-klik buka langsung di browser bawaan
├── jalankan-server.bat             # Shortcut 1-klik jalankan local server & buka browser
├── package.json                    # Manifest Project & Script Server Lokal
├── README.md                       # Dokumentasi Arsitektur & Panduan
├── css/
│   └── styles.css                  # Custom Styles, Micro-Interactions, Modal & Print Stylesheet
└── js/
    ├── data/
    │   └── members.data.js         # DATA LAYER: Dataset terisolasi 45 UMKM Mersi
    ├── models/
    │   ├── Member.js               # DOMAIN MODEL: Class Entity Pelaku Usaha (Enkapsulasi, Getters, Milestones)
    │   └── AuditPillars.js         # DOMAIN MODEL: Class Matriks 4 Pilar & 18 Indikator SJPH
    ├── services/
    │   ├── AuditCalculator.js      # SERVICE: Logika Perhitungan Matematis Bobot BPJPH & Bottlenecks
    │   ├── WhatsAppService.js      # SERVICE: Generator Template Pesan & Integrasi WA
    │   ├── PrintService.js         # SERVICE: Formatter Lembar Cetak Audit Mandiri & Rekap Grup PDF A4
    │   └── ChartService.js         # SERVICE: Manajemen Diagram Donut SVG Interaktif
    ├── ui/
    │   ├── ExecutiveSummaryView.js # UI VIEW: Render Tab 1, KPI Cards Clicks, Modal Drilldown
    │   ├── MemberDetailView.js     # UI VIEW: Render Dashboard Mandiri (Milestones, Komparasi, Checklist)
    │   └── UIManager.js            # UI MANAGER: Navigasi Tab, Filter Global, & Banner Pill
    └── app.js                      # CONTROLLER: Class SimHalalApp (Main Orchestrator)
```

---

## 📊 Matriks 4 Pilar Standar SJPH BPJPH (Jalur Self-Declare)

Perhitungan kesiapan sertifikasi halal mengacu pada bobot resmi Sistem Jaminan Produk Halal (SJPH):
1. **Pilar 1: Legalitas Usaha (Bobot 25%)**: KTP Pemilik, NIB OSS-RBA, KBLI Pangan Olahan, Akun SIHALAL aktif, Surat Permohonan.
2. **Pilar 2: Bahan Baku & Bumbu (Bobot 35%)**: Formulir rincian bahan, verifikasi *positive list* non-kritis, bukti sertifikat halal bumbu pabrik, sumber air bersih.
3. **Pilar 3: Alur Proses Halal / PPH (Bobot 25%)**: Dapur bebas najis/hewan, pemisahan alat masak khusus, Manual SJPH tertulis, kemasan higienis tertutup.
4. **Pilar 4: SDM & Komitmen Halal (Bobot 15%)**: Penyelia halal muslim, salinan KTP penyelia, SK penetapan, ikrar bermaterai Rp10.000, nama merek bebas konotasi haram.

### Ambang Batas Kelayakan:
- **Siap Daftar (Skor ≥ 80%)**: 14 Usaha (31%) &mdash; Berkas memenuhi syarat inti untuk diajukan ke portal BPJPH.
- **Perlu Pendampingan (Skor 50–79%)**: 22 Usaha (49%) &mdash; Berkas utama ada, namun dokumen teknis (Manual SJPH / bukti halal bumbu) perlu dilengkapi.
- **Belum Siap (Skor < 50%)**: 9 Usaha (20%) &mdash; Masih memerlukan edukasi legalitas dasar (NIB OSS-RBA) dan akun SIHALAL.

---

## 🚀 Cara Menjalankan Aplikasi

Aplikasi bersifat *zero-dependency* saat dijalankan di browser:

### Opsi 1: Buka Langsung (1-Klik Tanpa Terminal)
Klik dua kali file **`buka-aplikasi.bat`** di folder `E:\SDUM`. Aplikasi langsung terbuka di browser utama Anda.

### Opsi 2: Menggunakan Local Web Server
Klik dua kali file **`jalankan-server.bat`**, atau ketik di PowerShell:
```bash
npm start
# atau
python -m http.server 3000
```
Buka browser pada alamat: `http://localhost:3000`

---

## 🖨️ Cara Cetak Dokumen Resmi PDF

Aplikasi menyediakan dua jenis pencetakan dokumen berstandar A4 PDF:
1. **Cetak Berkas Rekapitulasi Kelompok (Siap Daftar / Pendampingan / Belum Siap)**:
   - Pada Tab 1 Ringkasan Pengurus, klik salah satu dari 4 kartu KPI (misal tombol kartu hijau **"Siap Daftar"**).
   - Jendela popup/modal akan terbuka menampilkan seluruh anggota dalam kelompok tersebut.
   - Klik tombol **"Cetak / Unduh Berkas Rekap (PDF)"** di bagian bawah modal.
2. **Cetak Lembar Audit Mandiri Anggota**:
   - Pada Tab 2 Dashboard Mandiri, periksa hasil checklist anggota.
   - Klik tombol **"Cetak Lembar Audit (PDF)"** pada kotak aksi di bawah.
3. Pada dialog browser:
   - Pilih Printer: **Save as PDF**
   - Kertas: **A4**
   - Margin: **Default / Minimum**
   - Opsi: Centang **Background Graphics**
