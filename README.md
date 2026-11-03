# DBAI-NOKIA: Nokia FastMile 5G Gateway 2 (GW2) Unified Toolkit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20x86__64%20%7C%20Armbian%20ARM64-blue?style=for-the-badge" alt="Platform">
  <img src="https://img.shields.io/badge/Device-Nokia%20FastMile%205G%20GW2-orange?style=for-the-badge" alt="Device">
  <img src="https://img.shields.io/badge/Release-Pre--compiled%20Binaries-brightgreen?style=for-the-badge" alt="Release">
  <img src="https://img.shields.io/badge/Build-Native%20Machine%20Code%20(Zero--Dependency)-purple?style=for-the-badge" alt="Build">
  <img src="https://img.shields.io/badge/Status-Tested%20%26%20Working-success?style=for-the-badge" alt="Status">
</p>

```
    ████▄  █████▄ ▄████▄ ██   ███  ██ ▄████▄ ██ ▄█▀ ██ ▄████▄
    ██  ██ ██▄▄██ ██▄▄██ ██   ██ ▀▄██ ██  ██ ████   ██ ██▄▄██
    ████▀  ██▄▄█▀ ██  ██ ██   ██   ██ ▀████▀ ██ ▀█▄ ██ ██  ██
             FASTMILE 5G GW2 UNIFIED TOOLKIT (V1.0)
```

**DBAI-NOKIA Toolkit** adalah instrumen terpadu (*all-in-one unified toolkit*) untuk modem **Nokia FastMile 5G Gateway 2 (MediaTek MT6890 / T750)**. Toolkit ini menyediakan alur otomatisasi penuh: aktivasi layanan SSH Root terintegrasi, penguncian port SSH otomatis (SSH Sniper & Guardian Daemon), streaming backup eMMC hardware partition dump (52 partisi lengkap) via TCP socket berkecepatan tinggi, validasi MD5 checksum otomatis dengan targeted auto-retry, hingga terminal interaktif root shell.

Tersedia dalam bentuk **Single Binary Executable (Zero-Dependency)** yang telah dikompilasi ke kode mesin native C. Seluruh dependensi dan aset pendukung telah terintegrasi di dalam satu file. **Tinggal download satu file dan langsung klik jalan—tanpa install Python, runtime, maupun dependensi apapun!**

---

## 📥 Link Download Binary Rilis

| Platform Target | Arsitektur | File Executable | Status | Link Download Langsung |
| :--- | :---: | :--- | :---: | :--- |
| **Windows 10 / 11** | 64-bit (`x86_64`) | `dbai-nokia-win64.exe` | ✅ Siap Pakai | [⬇️ Download Windows Binary](https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-win64.exe) |
| **PC / Laptop Linux** | 64-bit (`x86_64`) | `dbai-nokia-linux-x86_64` | ✅ Siap Pakai | [⬇️ Download Linux x86_64](https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-linux-x86_64) |
| **Armbian / SBC Linux** | ARM64 (`aarch64`) | `dbai-nokia-linux-aarch64` | ✅ Siap Pakai | [⬇️ Download Linux ARM64](https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-linux-aarch64) |

---

## ⚡ Quick Start: Jalankan Langsung (Tinggal Copas)

### 1. Windows (10 / 11 64-bit)
1. **Cara Paling Mudah**:
   - Download file [**`dbai-nokia-win64.exe`**](https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-win64.exe).
   - Letakkan di folder mana saja, lalu **klik dua kali (double-click)** pada file `dbai-nokia-win64.exe`. Toolkit akan langsung terbuka di jendela command prompt!

2. **Atau via PowerShell (1 Perintah Download & Langsung Run)**:
   ```powershell
   Invoke-WebRequest -Uri "https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-win64.exe" -OutFile "dbai-nokia-win64.exe"; .\dbai-nokia-win64.exe
   ```

---

### 2. PC / Laptop Linux (x86_64 — Ubuntu, Debian, Kali, Mint, Fedora, Arch)

Buka **Terminal Linux**, lalu *copy-paste* perintah 1 baris berikut (otomatis mengunduh, memberi hak eksekusi, dan langsung menjalankan):

```bash
curl -L -o dbai-nokia-linux-x86_64 "https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-linux-x86_64" && chmod +x dbai-nokia-linux-x86_64 && ./dbai-nokia-linux-x86_64
```

---

### 3. STB / SBC / Armbian Linux (ARM64 / aarch64 — Amlogic, RK3588, Raspberry Pi)

Buka **Terminal SSH / Console**, lalu *copy-paste* perintah 1 baris berikut:

```bash
curl -L -o dbai-nokia-linux-aarch64 "https://github.com/armarchindo/nokia-gateway-2/releases/download/nokia_hifiair_tools/dbai-nokia-linux-aarch64" && chmod +x dbai-nokia-linux-aarch64 && ./dbai-nokia-linux-aarch64
```

---

## 📋 Fitur Utama Toolkit

1. **🚀 Full Automated Pipeline (Menu `[a]`)**:
   - Satu langkah untuk mengeksekusi seluruh siklus dari awal hingga tuntas:
     `Generate Key` ➔ `Aktivasi Akses Root` ➔ `Kirim Sinyal Reboot` ➔ `SSH Sniper Lock` ➔ `Background Servers` ➔ `Full 52-Partisi eMMC Dump` ➔ `Verifikasi MD5 Checksum`.
2. **🔒 Standalone Executable (Zero-Dependency)**:
   - Terkompilasi penuh menjadi kode mesin biner mandiri.
   - Tanpa kuncian perangkat (*no device-lock*), portabel dan bebas digunakan di komputer manapun.
3. **⚡ High-Speed Direct Hardware Streaming**:
   - Menarik file partisi langsung dari block device eMMC (`/dev/mmcblk0*`) melalui socket streaming TCP (port 8888).
   - **Zero RAM Buffer di Modem**: Anti-OOM (*Out of Memory*), aman untuk partisi berukuran gigabyte (`rootfs_a`, `rootfs_b`, `container`).
4. **🛡️ Smart SSH Sniper & Anti-Watchdog Guardian**:
   - Memantau siklus reboot modem dan langsung mengunci port SSH `2222` saat sistem pertama kali membuka jalur akses.
   - Menginjeksi daemon penjaga di RAM modem untuk memastikan port SSH tetap terbuka dan stabil selama proses backup berlangsung.
5. **🔍 Validasi MD5 Otomatis dengan Targeted Auto-Retry**:
   - Menghitung hash MD5 secara independen di komputer dan mencocokkannya dengan sertifikat asli dari hardware modem (`md5sums.txt`).
   - Jika ditemukan partisi bermasalah, toolkit **hanya mengunduh ulang partisi yang gagal** (*targeted retry* hingga 3x) tanpa membuang waktu mengulang partisi lain yang sudah valid.
   - Pengecualian otomatis (*WAJAR-RW*) untuk partisi aktif dinamis (`user_data` dan `swr`).
6. **💻 Built-in Interactive SSH Terminal**:
   - Terintegrasi terminal root interaktif langsung di dalam toolkit tanpa memerlukan aplikasi pihak ketiga seperti PuTTY.

---

## ⚠️ Checklist Wajib Sebelum Melakukan Full Dump eMMC

Sebelum mengeksekusi Menu **[a]** atau Menu **[6]** (Full Dump eMMC):

| No | Langkah Persiapan | Penjelasan |
| :---: | :--- | :--- |
| 1 | **Lepas Kartu SIM** | Cabut kartu SIM seluler agar koneksi internet modem terputus dan partisi sistem tidak aktif menulis log data. |
| 2 | **Pastikan Modem IDLE** | Putuskan perangkat lain dari WiFi/LAN Nokia. Hanya hubungkan kabel LAN antara modem dan PC Anda. |
| 3 | **Catat Password Admin Web** | Password admin web tertera di stiker fisik bagian bawah modem (bukan password WiFi). |
| 4 | **Pastikan Satu Segmen IP** | PC harus berada di subnet yang sama dengan modem (`192.168.1.x`). Toolkit dilengkapi pendeteksi otomatis dan akan memberi peringatan jika subnet berbeda. |
| 5 | *(Disarankan)* **Factory Reset** | Lakukan Factory Reset lebih dulu via tombol reset di modem agar partisi read-write dalam kondisi bersih. |

---

## 🖥️ Tampilan Menu Utama

```text
  ┌───────────────────────────┬───────────────────────────────┐
  │  Platform : Windows/Linux │ PC LAN IP : 192.168.1.x (OK)  │
  │  Modem IP : 192.168.1.1   │ SSH Status: Terkoneksi        │
  └───────────────────────────┴───────────────────────────────┘

 --- [ ALUR OTOMATIS PENUH ] ---
  [a] FULL PIPELINE: Generate SSH Key -> MD5 Checksum

 --- [ EKSEKUSI LANGKAH DEMI LANGKAH ] ---
  [1] Periksa / Generate Pasangan SSH Key
  [2] Aktivasi Layanan Akses Root (SSH)
  [3] Trigger Reboot Modem
  [4] Mulai SSH Sniper & Buka Terminal Interaktif
  [5] Jalankan Background Server (HTTP:8081 + TCP:8888)
  [6] Full Dump Partisi eMMC via SSH
  [7] Verifikasi Hash MD5 Checksum Hasil Backup
  [8] Backup Direktori (/data & /rom/etc) [Opsional]

 --- [ PENGATURAN ] ---
  [k] Ubah Konfigurasi (IP Modem, Port, Kredensial)
  [0] Keluar
```

---

## 📂 Output Folder Saat Dijalankan

Setelah binary dijalankan, toolkit akan secara otomatis membuat file konfigurasi dan folder backup di direktori yang sama:

```text
./
├── dbai-nokia-win64.exe (atau linux binary)   # File binary yang Anda unduh
├── fastmile_key / fastmile_key.pub            # Kunci SSH otomatis (dibuat saat opsi [1]/[a])
└── image_backup/                              # Folder hasil backup otomatis (dibuat saat opsi [6]/[a])
    ├── md5sums.txt                            # Sertifikat hash asli dari hardware modem
    ├── report.txt                             # Laporan verifikasi integritas backup
    ├── non-userarea/                          # Partisi Boot0 & Boot1
    └── *.img                                  # 50 file image partisi eMMC lengkap
```

---

## ❓ FAQ & Troubleshooting

<details>
<summary><b>1. Muncul peringatan: BEDA SUBNET dengan Modem!</b></summary>

* **Penyebab**: IP interface PC Anda tidak satu segmen dengan IP modem (`192.168.1.1`).
* **Solusi**: Sambungkan kabel LAN PC langsung ke port LAN modem Nokia dan pastikan adapter LAN PC diset DHCP (*Obtain an IP address automatically*), atau masukkan IP manual (misal: `192.168.1.100`).
</details>

<details>
<summary><b>2. Status SSH "Belum Terkoneksi" / Connection Refused</b></summary>

* **Penyebab**: Watchdog firewall internal Nokia mematikan service sshd setelah modem boot normal beberapa menit.
* **Solusi**: 
  - Pilih **Menu [4]**. Toolkit akan mendeteksi Web Admin aktif dan otomatis menawarkan opsi:
    `[1] Kirim Sinyal Reboot Resmi ke Modem & Mulai SSH Sniper (Rekomendasi)`
  - Toolkit akan memicu reboot resmi dan langsung mengunci port SSH sesaat saat modem menyala kembali.
</details>

<details>
<summary><b>3. Mengapa partisi user_data.img dan swr.img bertanda [WAJAR-RW]?</b></summary>

* **Penjelasan**: Partisi `user_data` (data aplikasi) dan `swr` (firmware rollback counter) adalah partisi *live read-write* yang ditulis secara berkala oleh sistem operasi Nokia saat modem menyala. Perbedaan hash pada partisi ini adalah normal dan tidak memengaruhi pemulihan firmware (*safe exclusion*).
</details>

---

## ⚖️ Lisensi & Disclaimer

Tool ini dikembangkan untuk tujuan pemeliharaan perangkat (*hardware backup & recovery*), riset firmware, dan edukasi pribadi. Gunakan dengan penuh tanggung jawab atas perangkat milik Anda sendiri.
