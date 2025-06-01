<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/laravel/art@master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="200" alt="Laravel Logo">
  <h1>Manajemen Produk API</h1>
  <p>
    Sebuah RESTful API yang dibuat dengan Laravel untuk mengelola data produk. Mendukung operasi CRUD (Create, Read, Update, Delete).
  </p>
  <p>
    <img src="https://img.shields.io/badge/PHP-8.2%2B-777BB4?style=for-the-badge&logo=php" alt="PHP Version">
    <img src="https://img.shields.io/badge/Laravel-10.x-FF2D20?style=for-the-badge&logo=laravel" alt="Laravel Version">
    <img src="https://img.shields.io/badge/API%20Status-Online-brightgreen?style=for-the-badge&logo=api" alt="API Status">
  </p>
</div>

---

## 🌟 Fitur Utama

* **List Produk**: Mengambil semua data produk.
* **Detail Produk**: Mengambil detail satu produk berdasarkan ID.
* **Tambah Produk**: Menambahkan produk baru ke dalam database.
* **Update Produk**: Memperbarui informasi produk yang sudah ada.
* **Hapus Produk**: Menghapus produk dari database.

---

## 🛠️ Teknologi yang Digunakan

* **Backend**: Laravel
* **Bahasa**: PHP
* **Database**: MySQL
* **Web Server**: Apache

---

## 🚀 Instalasi & Konfigurasi

1.  **Clone repository ini:**
    ```bash
    git clone [URL_REPOSITORY_ANDA]
    cd [NAMA_FOLDER_PROYEK]
    ```
3.  **Salin file `.env.example` menjadi `.env`:**
    ```bash
    cp .env.example .env
    ```
4.  **Generate application key:**
    ```bash
    php artisan key:generate
    ```
5.  **Konfigurasi database Anda di file `.env`:**
    ```env
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=nama_database_anda
    DB_USERNAME=username_database_anda
    DB_PASSWORD=password_database_anda
    ```
6.  **Jalankan migrasi database:**
    ```bash
    php artisan migrate
    ```
8.  **Jalankan server development:**
    ```bash
    php artisan serve
    ```
    API akan tersedia di `http://127.0.0.1:8000/api/`.

---

## 📖 Endpoint API

Berikut adalah daftar endpoint yang tersedia:

### Produk

* **GET `/api/products`**
    * **Deskripsi**: Mengambil semua data produk.
    * **Contoh Response Sukses (200 OK)**:
        ```json
        [
            {
                "id": 1,
                "nama": "Produk A",
                "deskripsi": "Deskripsi Produk A",
                "harga": 10000,
                "created_at": "2025-05-30T10:00:00.000000Z",
                "updated_at": "2025-05-30T10:00:00.000000Z"
            },
            {
                "id": 2,
                "nama": "Produk B",
                "deskripsi": "Deskripsi Produk B",
                "harga": 15000,
                "created_at": "2025-05-30T10:05:00.000000Z",
                "updated_at": "2025-05-30T10:05:00.000000Z"
            }
        ]
        ```

* **POST `/api/products`**
    * **Deskripsi**: Menambahkan produk baru.
    * **Request Body (application/json)**:
        ```json
        {
            "nama": "Produk Baru",
            "deskripsi": "Deskripsi Produk Baru yang Keren",
            "harga": 25000
        }
        ```
    * **Contoh Response Sukses (201 Created)**:
        ```json
        {
            "id": 3,
            "nama": "Produk Baru",
            "deskripsi": "Deskripsi Produk Baru yang Keren",
            "harga": 25000,
            "created_at": "2025-05-30T11:00:00.000000Z",
            "updated_at": "2025-05-30T11:00:00.000000Z"
        }
        ```
    * **Contoh Response Gagal (422 Unprocessable Entity - Validasi Error)**:
        ```json
        {
            "message": "The given data was invalid.",
            "errors": {
                "nama": [
                    "The nama field is required."
                ],
                "harga": [
                    "The harga field must be a number."
                ]
            }
        }
        ```

* **GET `/api/products/{id}`**
    * **Deskripsi**: Mengambil detail produk berdasarkan ID.
    * **Contoh Response Sukses (200 OK)**:
        ```json
        {
            "id": 1,
            "nama": "Produk A",
            "deskripsi": "Deskripsi Produk A",
            "harga": 10000,
            "created_at": "2025-05-30T10:00:00.000000Z",
            "updated_at": "2025-05-30T10:00:00.000000Z"
        }
        ```
    * **Contoh Response Gagal (404 Not Found)**:
        ```json
        {
            "message": "Product not found."
        }
        ```

* **PUT `/api/products/{id}`**
    * **Deskripsi**: Memperbarui data produk berdasarkan ID.
    * **Request Body (application/json)**:
        ```json
        {
            "nama": "Produk A (Updated)",
            "deskripsi": "Deskripsi Produk A yang sudah diupdate",
            "harga": 12000
        }
        ```
    * **Contoh Response Sukses (200 OK)**:
        ```json
        {
            "id": 1,
            "nama": "Produk A (Updated)",
            "deskripsi": "Deskripsi Produk A yang sudah diupdate",
            "harga": 12000,
            "created_at": "2025-05-30T10:00:00.000000Z",
            "updated_at": "2025-05-30T11:30:00.000000Z"
        }
        ```
    * **Contoh Response Gagal (404 Not Found)**:
        ```json
        {
            "message": "Product not found."
        }
        ```

* **DELETE `/api/products/{id}`**
    * **Deskripsi**: Menghapus produk berdasarkan ID.
    * **Contoh Response Sukses (200 OK)**:
        ```json
        {
            "message": "Product deleted successfully."
        }
        ```
    * **Contoh Response Gagal (404 Not Found)**:
        ```json
        {
            "message": "Product not found."
        }
        ```

---

