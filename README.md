# Penetration Testing Final Project: Security Assessment Report

**Author:** Ririn Yulandari
**Date:** December 2025
**Tools:** Kali Linux, Nmap, Wireshark, Google Dorks

---

## 📄 Project Overview (Latar Belakang)
Repository ini berisi **Laporan Teknis Security Assessment** yang disusun untuk memenuhi Tugas Besar mata kuliah Keamanan Siber. Proyek ini mensimulasikan proses audit keamanan yang komprehensif, dimulai dari pengumpulan informasi publik hingga analisis kerentanan teknis.

Tujuan utama proyek ini adalah:
1.  Melakukan pemetaan aset digital (*footprinting*) pada target nyata.
2.  Mengidentifikasi layanan dan menganalisis perilaku protokol jaringan dalam lingkungan terkontrol.
3.  Mendokumentasikan temuan sebagai bahan evaluasi keamanan.

## 🎯 Scope & Scenario (Skenario & Ruang Lingkup)
Sesuai dengan ketentuan tugas besar, proyek ini dibagi menjadi dua tahapan:

| Tahapan | Target | Deskripsi Skenario |
| :--- | :--- | :--- |
| **1. Passive Reconnaissance** | `jabarprov.go.id` (Pemerintah) | **Skenario:** Bertindak sebagai konsultan keamanan yang melakukan audit jejak digital (*OSINT*) pada domain pemerintahan untuk mencari potensi kebocoran informasi (*Information Disclosure*) tanpa melakukan interaksi langsung dengan server target. |
| **2. Active Reconnaissance** | `Localhost / 192.168.131.39` | **Skenario:** Mensimulasikan serangan internal pada lingkungan laboratorium (*Lab Simulation*) untuk menganalisis respons protokol TCP/IP saat terjadi pemindaian port (*Port Scanning*) pada layanan SSH dan HTTP. |

---

## 🛠️ Tools & Methodology

### 1. Passive Reconnaissance Tools
* **Google Dorks:** Digunakan untuk mencari file sensitif (`.sql`, `.env`, `.log`) yang terindeks mesin pencari.
* **GitHub Search:** Digunakan untuk mencari kebocoran *source code* atau kredensial pada repositori publik.
* **Whois & DNS Recon:** (Opsional) Untuk memetakan informasi pendaftaran domain.

### 2. Active Reconnaissance Tools
* **Nmap:** Digunakan untuk *Network Discovery* dan *Port Scanning* (Teknik `-sT` Connect Scan).
* **Wireshark:** Digunakan untuk *Packet Sniffing* guna memvalidasi proses *TCP 3-Way Handshake* (SYN, SYN-ACK, ACK).

---

## 📊 Summary of Findings (Ringkasan Temuan)

* **Digital Hygiene (Passive):** Target pemerintahan (`jabarprov.go.id`) menunjukkan postur keamanan yang baik. Tidak ditemukan kebocoran file konfigurasi kritis atau database di domain publik.
* **Network Analysis (Active):** Berhasil memetakan perilaku protokol jaringan:
    * **Open Port:** Terdeteksi melalui paket respons `[SYN, ACK]`.
    * **Closed Port:** Terdeteksi melalui paket respons `[RST, ACK]` (Reset).

*(Detail analisis lengkap dan bukti screenshot tersedia di dalam dokumen Laporan Akhir).*

---

## 📂 File Structure
* `LAPORAN_TUGAS.pdf`: **Laporan Utama.** Dokumen lengkap berisi pendahuluan, metodologi, analisis teknis per langkah, dan kesimpulan.
* `evidence/`: Folder repositori bukti dokumentasi (*screenshot*) pengerjaan.
    * `PassiveRecon/`: Bukti OSINT (Google Dorks, GitHub).
    * `ActiveRecon/`: Bukti Nmap dan Wireshark.
* `README.md`: Ringkasan eksekutif proyek (File ini).

---

## ⚠️ Disclaimer
*Proyek ini dilakukan semata-mata untuk tujuan pendidikan (Educational Purposes) dan memenuhi Tugas Besar. Penulis tidak bertanggung jawab atas penyalahgunaan informasi. Seluruh aktivitas pemindaian aktif dilakukan di lingkungan laboratorium milik sendiri (Localhost/Authorized Environment).*