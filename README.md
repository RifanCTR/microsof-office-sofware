# Cara Menghapus Microsoft Word, Excel, dan PowerPoint Sampai Bersih

Tutorial ini menjelaskan cara **menghapus Microsoft Office sampai bersih**, kemudian memasangnya kembali menggunakan **Office Deployment Tool**.

Cara ini cocok dilakukan jika Office mengalami error, gagal dibuka, atau ingin melakukan instalasi ulang dengan kondisi yang lebih bersih.

---

# BAGIAN 1 — MENGHAPUS MICROSOFT OFFICE

## 1. Hapus Office melalui Settings

Pertama, buka Settings dengan menekan:

**Windows + I**

Kemudian pilih:

**Aplikasi → Aplikasi terinstal**

Pada kolom pencarian, cari:

* Microsoft 365
* Microsoft Office
* Office

Nama Office bisa berbeda-beda tergantung versi yang digunakan.

Contohnya:

**Microsoft Office LTSC Professional Plus 2021 - en-us**

Jika sudah ditemukan:

**Klik ⋯ → Uninstall / Hapus instalan**

Ikuti prosesnya sampai selesai.

---

## 2. Cek Office melalui Control Panel

Setelah itu, kita cek apakah Office masih terdaftar di Windows.

Tekan:

**Windows + R**

Kemudian ketik:

```text
appwiz.cpl
```

Tekan **Enter**.

Akan muncul jendela **Programs and Features**.

Cari:

* Microsoft Office
* Microsoft 365
* atau paket Microsoft Office lainnya

Jika masih ada, klik Office tersebut lalu pilih:

**Uninstall**

Ikuti prosesnya sampai selesai.

---

## 3. Gunakan Tool Resmi Microsoft

Jika ingin menghapus Office dengan lebih menyeluruh, gunakan panduan resmi Microsoft:

**Microsoft — Menghapus instalan Microsoft 365 atau Office dari PC**

https://support.microsoft.com/id-id/office/lifecycle/officeinstall/uninstall-microsoft-365-or-office-from-a-pc

Ikuti petunjuk yang diberikan Microsoft dan gunakan tool penghapusan jika tersedia untuk versi Office yang digunakan.

Setelah selesai, **restart komputer**.

---

# BAGIAN 2 — MEMBERSIHKAN SISA OFFICE

Setelah komputer menyala kembali, kita bisa mengecek apakah masih ada folder Office yang tertinggal.

Tekan:

**Windows + R**

Kemudian masukkan lokasi berikut satu per satu.

### Folder 1

```text
%ProgramFiles%\Microsoft Office
```

### Folder 2

```text
%ProgramFiles(x86)%\Microsoft Office
```

### Folder 3

```text
%ProgramData%\Microsoft\Office
```

### Folder 4

```text
%AppData%\Microsoft\Office
```

### Folder 5

```text
%LocalAppData%\Microsoft\Office
```

Tidak semua folder tersebut pasti masih ada. Kalau Windows mengatakan folder tidak ditemukan, **tidak masalah**.

Biasanya folder berikut masih bisa ditemukan:

```text
%AppData%\Microsoft\Office
```

dan:

```text
%LocalAppData%\Microsoft\Office
```

Jika Office sudah berhasil di-uninstall dan folder tersebut memang merupakan sisa Office, folder **Office** dapat dihapus.

Contohnya:

```text
Microsoft
└── Office
```

Yang dihapus hanya:

```text
Office
```

**Jangan hapus folder `Microsoft` secara keseluruhan**, karena folder tersebut digunakan oleh banyak aplikasi dan komponen Windows lainnya.

Setelah selesai, Office lama sudah dihapus dan sisa folder Office yang masih tertinggal juga sudah dibersihkan.

---

# BAGIAN 3 — MENYIAPKAN FILE INSTALLER OFFICE

Setelah Office lama dihapus, kita bisa melakukan instalasi Office kembali menggunakan **Office Deployment Tool (ODT)**.

## 1. Download file Office Deployment Tool

Download **Office Deployment Tool** dari sumber yang digunakan untuk menyediakan file instalasi.

Jika file tersedia di GitHub:

Klik:

**Code → Download ZIP**

Setelah selesai download, cari file ZIP tersebut.

---

## 2. Extract file ZIP

Klik kanan file ZIP → pilih:

**Extract All...**

Kemudian pilih lokasi untuk menyimpan hasil extract.

Setelah selesai, buka folder hasil extract tersebut.

Di dalamnya biasanya terdapat file seperti:

```text
Office Deployment Tool
Configuration 32 bit
Configuration 64 bit
```

---

## 3. Jalankan Office Deployment Tool

Buka file:

**Office Deployment Tool**

Centang:

**I accept the Microsoft Software License Terms**

Kemudian klik:

**Continue**

Windows akan meminta lokasi untuk menyimpan file hasil extract.

Kita akan membuat folder khusus untuk Office.

Pilih:

**This PC → Local Disk (C:)**

Kemudian klik:

**Make New Folder**

Buat folder dengan nama:

```text
MsOffice
```

Sehingga lokasinya menjadi:

```text
C:\MsOffice
```

Pilih folder tersebut lalu klik **OK**.

---

# BAGIAN 4 — MEMILIH KONFIGURASI OFFICE

Di folder yang sebelumnya sudah disiapkan, terdapat pilihan konfigurasi:

```text
Configuration 32 bit
Configuration 64 bit
```

Pilih konfigurasi sesuai kebutuhan komputer.

Jika menggunakan Windows 64-bit, umumnya gunakan:

**Configuration 64 bit**

Setelah memilihnya, buka folder tersebut.

Di dalamnya terdapat file:

```text
Configuration.xml
```

Salin file tersebut.

Kemudian pindahkan ke:

```text
C:\MsOffice
```

Jadi isi foldernya kurang lebih seperti:

```text
C:\MsOffice
│
├── setup.exe
└── configuration.xml
```

Pastikan **setup.exe** dan **configuration.xml** berada di folder yang sama.

---

# BAGIAN 5 — MENDOWNLOAD FILE OFFICE

Sekarang kita mulai proses download file Office.

## 1. Buka Command Prompt sebagai Administrator

Tekan tombol:

**Windows**

Kemudian cari:

```text
cmd
```

atau:

```text
Command Prompt
```

Klik kanan **Command Prompt** → pilih:

**Run as administrator**

Jika muncul pertanyaan dari Windows, pilih **Yes**.

---

## 2. Masuk ke folder Office

Di Command Prompt, masukkan:

```text
cd C:\MsOffice
```

Kemudian tekan **Enter**.

Setelah itu jalankan:

```text
setup.exe /download configuration.xml
```

Tekan **Enter**.

Office Deployment Tool akan mulai mendownload file Office sesuai konfigurasi yang dipilih.

**Proses ini bisa memerlukan waktu cukup lama**, tergantung ukuran file dan kecepatan internet.

Jangan tutup Command Prompt selama proses masih berjalan.

Setelah proses download selesai, file Office akan tersimpan di folder:

```text
C:\MsOffice
```

---

# BAGIAN 6 — MEMASANG MICROSOFT OFFICE

Setelah proses download selesai, kembali ke Command Prompt yang tadi.

Pastikan masih berada di:

```text
C:\MsOffice
```

Kemudian masukkan:

```text
setup.exe /configure configuration.xml
```

Tekan **Enter**.

Windows akan menjalankan proses instalasi Office berdasarkan konfigurasi yang sudah dibuat.

Tunggu sampai proses instalasi selesai.

---

# BAGIAN 7 — SELESAI

Jika proses instalasi selesai, buka **Start Menu** dan cari:

* Word
* Excel
* PowerPoint

Jika aplikasi tersebut sudah muncul dan dapat dibuka, berarti instalasi Office sudah selesai.

## Ringkasnya

Urutan prosesnya adalah:

**Hapus Office lama**

↓

**Restart komputer**

↓

**Bersihkan sisa folder Office**

↓

**Download Office Deployment Tool**

↓

**Extract file**

↓

**Buat folder `C:\MsOffice`**

↓

**Masukkan `setup.exe` + `configuration.xml`**

↓

**Buka CMD sebagai Administrator**

↓

```text
cd C:\MsOffice
```

↓

```text
setup.exe /download configuration.xml
```

↓

**Tunggu download selesai**

↓

```text
setup.exe /configure configuration.xml
```

↓

**Tunggu instalasi selesai**

↓

**Buka Word / Excel / PowerPoint**

---

### Catatan Penting

* Jangan menghapus seluruh folder `Microsoft` di `AppData`, `ProgramData`, atau `Program Files`.
* Yang dibersihkan secara manual hanya folder yang memang merupakan **sisa Office**.
* Pastikan file `setup.exe` dan `configuration.xml` berada di folder yang sama.
* Jangan menutup CMD ketika proses `/download` atau `/configure` masih berjalan.
* Pastikan konfigurasi **32-bit atau 64-bit** sesuai dengan Office yang ingin dipasang.
* File `configuration.xml` menentukan jenis Office, bahasa, arsitektur, dan pengaturan instalasi yang digunakan.
