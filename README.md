# WordPress + MariaDB dengan Docker Compose

Proyek ini menjalankan WordPress dan MariaDB menggunakan Docker Compose serta memeriksa konfigurasi secara otomatis melalui GitHub Actions.

## Persiapan

1. Salin `.env.example` menjadi `.env`.
2. Ganti nilai password pada file `.env`.
3. Jalankan aplikasi:

   ```bash
   docker compose up -d
   ```

4. Buka WordPress melalui `http://localhost:8080`.
5. Periksa container:

   ```bash
   docker compose ps
   ```

6. Hentikan aplikasi:

   ```bash
   docker compose down
   ```

## CI dengan GitHub Actions

Workflow berada di `.github/workflows/compose-check.yml`. Workflow berjalan saat ada push ke branch `main` atau Pull Request.

Job `validate` melakukan tiga hal:
- Mengambil kode repository.
- Menyalin `.env.example` menjadi `.env`.
- Menjalankan `docker compose config -q` untuk memvalidasi konfigurasi tanpa menjalankan container.

## Badge Status

Ganti `USERNAME` dan `NAMA_REPO` dengan akun dan nama repository GitHub milikmu, lalu tambahkan ke README:

```markdown
![Compose Check](https://github.com/USERNAME/NAMA_REPO/actions/workflows/compose-check.yml/badge.svg)
```

## Keamanan

Jangan pernah mengunggah file `.env` asli ke GitHub. Yang boleh diunggah adalah `.env.example` tanpa password pribadi.
