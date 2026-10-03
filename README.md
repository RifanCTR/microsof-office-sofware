<img width="772" height="494" alt="Screenshot 2026-10-03 082952" src="https://github.com/user-attachments/assets/1411182b-c99e-46f3-a6ae-71950de1a0f6" />
# Cara Menghapus & Menginstal Microsoft Office

> Panduan lengkap untuk menghapus Microsoft Word, Excel, dan PowerPoint, membersihkan sisa Office, kemudian melakukan instalasi kembali menggunakan Office Deployment Tool (ODT).

---

## Daftar Isi

* [1. Menghapus Microsoft Office](#1-menghapus-microsoft-office)
* [2. Membersihkan Sisa Office](#2-membersihkan-sisa-office)
* [3. Download Office Deployment Tool](#3-download-office-deployment-tool)
* [4. Extract File](#4-extract-file)
* [5. Menyiapkan Folder Office](#5-menyiapkan-folder-office)
* [6. Memilih Configuration](#6-memilih-configuration)
* [7. Download File Office](#7-download-file-office)
* [8. Install Microsoft Office](#8-install-microsoft-office)
* [9. Selesai](#9-selesai)

---

# 1. Menghapus Microsoft Office

Sebelum memasang Office kembali, hapus instalasi Office yang lama terlebih dahulu.

Hal ini berguna untuk menghindari konflik dengan instalasi Office sebelumnya.

## Uninstall melalui Settings

Tekan:

```text
Windows + I
```

Kemudian buka:

```text
Aplikasi
→ Aplikasi terinstal
```

Pada kolom pencarian, cari:

```text
Microsoft 365
Microsoft Office
Office
```

Nama Office dapat berbeda tergantung versi yang terpasang.

Contohnya:

```text
Microsoft Office LTSC Professional Plus 2021 - en-us
```

Jika sudah ditemukan:

```text
⋯ → Uninstall / Hapus instalan
```

Ikuti proses uninstall sampai selesai.

---

## Uninstall melalui Control Panel

Jika Office masih muncul atau ingin memastikan kembali, tekan:

```text
Windows + R
```

Kemudian masukkan:

```text
appwiz.cpl
```

Tekan **Enter**.

Akan muncul jendela:

```text
Programs and Features
```

Cari:

```text
Microsoft Office
Microsoft 365
```

atau paket Office lainnya.

Kemudian pilih:

```text
Uninstall
```

Tunggu sampai proses selesai.

---

# 2. Membersihkan Sisa Office

Setelah Office berhasil dihapus, restart komputer terlebih dahulu.

Setelah komputer menyala kembali, kita dapat mengecek beberapa folder yang mungkin masih tersisa.

Tekan:

```text
Windows + R
```

Kemudian cek lokasi berikut satu per satu.

### Program Files

```text
%ProgramFiles%\Microsoft Office
```

### Program Files (x86)

```text
%ProgramFiles(x86)%\Microsoft Office
```

### ProgramData

```text
%ProgramData%\Microsoft\Office
```

### AppData

```text
%AppData%\Microsoft\Office
```

### LocalAppData

```text
%LocalAppData%\Microsoft\Office
```

Tidak semua folder tersebut pasti masih ada.

Jika Windows mengatakan folder tidak ditemukan, tidak perlu khawatir.

## Menghapus Folder Sisa

Pada beberapa instalasi, folder berikut masih dapat ditemukan:

```text
%AppData%\Microsoft\Office
```

dan:

```text
%LocalAppData%\Microsoft\Office
```

Jika Office sudah benar-benar di-uninstall dan folder tersebut memang hanya berisi sisa Office, folder:

```text
Office
```

dapat dihapus.

Contohnya:

```text
Microsoft
└── Office
```

Yang dihapus:

```text
Office
```

Bukan:

```text
Microsoft
```

> Jangan menghapus seluruh folder `Microsoft`. Folder tersebut digunakan oleh banyak aplikasi Windows lainnya.

---

# 3. Download Office Deployment Tool

Setelah Office lama dibersihkan, kita dapat menyiapkan instalasi Office menggunakan:

**Office Deployment Tool (ODT)**

Download file ODT dari sumber yang digunakan untuk menyediakan installer.

Jika file tersedia dalam bentuk repository GitHub:

```text
Code → Download ZIP
```

Kemudian tunggu sampai file selesai didownload.

---

# 4. Extract File

Setelah file ZIP selesai didownload:

```text
Klik kanan file ZIP
→ Extract All...
```

Kemudian pilih lokasi untuk menyimpan hasil extract.

Buka folder hasil extract tersebut.

Di dalamnya biasanya terdapat file atau folder seperti:

```text
Office Deployment Tool
Configuration 32 bit
Configuration 64 bit
```

---

# 5. Menyiapkan Folder Office

Buka:

```text
Office Deployment Tool
```

Kemudian centang:

```text
I accept the Microsoft Software License Terms
```

Klik:

```text
Continue
```

Selanjutnya pilih lokasi untuk menyimpan file Office Deployment Tool.

Pilih:

```text
This PC
→ Local Disk (C:)
```

Kemudian buat folder baru:

```text
MsOffice
```

Sehingga lokasi folder menjadi:

```text
C:\MsOffice
```

Pilih folder tersebut dan lanjutkan.

---

# 6. Memilih Configuration

Pada file yang sudah disiapkan, biasanya terdapat pilihan:

```text
Configuration 32 bit
Configuration 64 bit
```

Pilih sesuai arsitektur Office yang ingin digunakan.

Contoh:

```text
Configuration 64 bit
```

Buka folder tersebut.

Cari file:

```text
Configuration.xml
```

Salin file tersebut ke:

```text
C:\MsOffice
```

Pastikan file utama berada di folder yang sama.

Contohnya:

```text
C:\MsOffice
│
├── setup.exe
└── configuration.xml
```

> File `configuration.xml` berisi pengaturan instalasi Office, seperti versi, bahasa, arsitektur, dan aplikasi yang akan dipasang.

---

# 7. Download File Office

Sekarang kita akan mendownload file Office menggunakan Command Prompt.

## Buka CMD sebagai Administrator

Tekan tombol:

```text
Windows
```

Kemudian cari:

```text
cmd
```

atau:

```text
Command Prompt
```

Klik kanan:

```text
Command Prompt
→ Run as administrator
```

Jika muncul User Account Control, pilih:

```text
Yes
```

## Masuk ke Folder Office

Di CMD masukkan:

```bat
cd C:\MsOffice
```

Kemudian tekan **Enter**.

Setelah itu jalankan:

```bat
setup.exe /download configuration.xml
```

Tekan **Enter**.

Office Deployment Tool akan mulai mendownload file Office.

Proses ini bisa memerlukan waktu cukup lama tergantung koneksi internet dan ukuran file Office.

Jangan tutup CMD selama proses masih berjalan.

Setelah selesai, file Office akan tersimpan di:

```text
C:\MsOffice
```

---

# 8. Install Microsoft Office

Setelah proses download selesai, pastikan CMD masih berada di:

```text
C:\MsOffice
```

Kemudian jalankan:

```bat
setup.exe /configure configuration.xml
```

Tekan **Enter**.
<img width="772" height="494" alt="Screenshot 2026-10-03 082952" src="https://github.com/user-attachments/assets/82e9c7bf-4e75-49b0-85ec-46cb851880ce" />


Office Deployment Tool akan mulai memasang Microsoft Office berdasarkan konfigurasi yang sudah dibuat.

Tunggu sampai proses instalasi selesai.

---

# 9. Selesai

Setelah instalasi selesai, buka:

```text
Start Menu
```

Kemudian cari:

```text
Word
Excel
PowerPoint
```

Jika aplikasi sudah muncul dan dapat dibuka, berarti proses instalasi Office sudah selesai.

---

## Alur Singkat

```text
Hapus Office Lama
        ↓
Restart Windows
        ↓
Bersihkan Sisa Office
        ↓
Download Office Deployment Tool
        ↓
Extract File ZIP
        ↓
Buat C:\MsOffice
        ↓
Masukkan configuration.xml
        ↓
Buka CMD sebagai Administrator
        ↓
cd C:\MsOffice
        ↓
setup.exe /download configuration.xml
        ↓
Tunggu Download Selesai
        ↓
setup.exe /configure configuration.xml
        ↓
Microsoft Office Terpasang
```

---

## Catatan Penting

* Pastikan Office lama sudah di-uninstall sebelum melakukan instalasi ulang.
* Jangan menghapus seluruh folder `Microsoft`.
* Hapus hanya folder yang memang merupakan sisa Office.
* Jangan menghapus folder sistem Windows secara sembarangan.
* Pastikan `setup.exe` dan `configuration.xml` berada pada lokasi yang benar.
* Gunakan CMD sebagai Administrator.
* Jangan menutup CMD ketika proses download atau instalasi masih berlangsung.
* Pastikan konfigurasi Office yang digunakan sesuai dengan kebutuhan.
* Gunakan lisensi atau aktivasi Office yang sah untuk edisi yang dipasang.

---

## Hasil Akhir

Setelah seluruh proses selesai, Microsoft Office akan terpasang kembali sesuai konfigurasi yang digunakan.

Contohnya:

```text
Microsoft Word
Microsoft Excel
Microsoft PowerPoint
```

Panduan ini dapat digunakan sebagai langkah untuk melakukan:

```text
Clean Uninstall
       ↓
Clean Up
       ↓
Download
       ↓
Install
```

Dengan begitu, instalasi Office lama sudah dihapus terlebih dahulu sebelum melakukan instalasi baru.
