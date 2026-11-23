# Tugas Minggu 11: CI untuk Repo Compose

![CI](https://github.com/USERNAME/ci-compose-minggu11/actions/workflows/compose-check.yml/badge.svg)

*Nama:* [Irfan Christiano Aling Lalenoh]
*NIM:* [202557201080]
*Mata Kuliah:* Teknologi Open Source

## Deskripsi
Proyek ini menggunakan GitHub Actions untuk memvalidasi
konfigurasi Docker Compose WordPress dan MariaDB.
Pemeriksaan berjalan otomatis setiap ada push ke main
dan setiap ada Pull Request.

## Isi Repositori
- .github/workflows/compose-check.yml
- docker-compose.yml
- .env.example
- .gitignore
- README.md

## Cara Kerja Workflow
Workflow menggunakan job validate pada ubuntu-latest.
Tahap pertama mengambil repository, tahap kedua menyalin
.env.example menjadi .env, dan tahap ketiga memvalidasi
konfigurasi menggunakan docker compose config -q.

## Bukti

### 1. Run GitHub Actions Berhasil
![Run Hijau](bukti/1-run-hijau.png)

### 2. Pull Request dengan Check Gagal
![PR Merah](bukti/2-pr-merah.png)

### 3. Badge Status
![Badge](bukti/3-badge.png)

## Tautan Pull Request
[https://github.com/irfanlalenoh/ci-compose-minggu11/pull/1]

## Kendala dan Solusi
Kendala yang ditemukan adalah kesalahan indentasi
pada file docker-compose.yml sehingga proses validasi
gagal. Solusinya adalah memperbaiki indentasi YAML
dan menjalankan pemeriksaan kembali.

## Refleksi
GitHub Actions membantu memeriksa konfigurasi secara
otomatis setiap ada perubahan. Dengan CI, kesalahan
dapat diketahui lebih awal sebelum proyek digabungkan.
