# Responsi_TEK_CLOUD
# Website Data Diri

## Deskripsi
Website ini terdiri dari dua halaman yang di-hosting di container terpisah menggunakan Docker.

## Cara Menjalankan di Killercoda Ubuntu Playground

### Langkah-langkah

1. Buat direktori `website-profil` dan file `index.html` juga file foto di dalamnya dengan isi seperti berikut:
    ```sh
    mkdir website-profil
    ```
    Buat file `index.html`
    Mengunggah foto Profil dalam bentuk png `foto.png`


3. Buat jaringan Docker dengan nama `my-evita-ishtar-dewi-network`:
    ```sh
    docker network create my-evita-ishtar-dewi-network
    ```

4. Buat Dockerfile untuk `website-profil`

5. Build image Docker untuk `website-profil`
    ```sh
    cd website-profil
    docker build -t website-profil .
    ```

6. Jalankan container `website-profil`:
    ```sh
    docker run -d --name website-profil --network my-evita-ishtar-dewi-network -p 8081:80 website-profil
    ```

7. Buat direktori `website-utama` dan file `index.html` di dalamnya dengan isi seperti berikut:
    ```sh
    mkdir website-utama
    ```
    Buat file `index.html`

8. Buat Dockerfile untuk `website-utama`

9. Build image Docker untuk `website-utama`:
    ```sh
    cd website-utama
    docker build -t website-utama .
    ```

10. Jalankan container `website-utama`:
    ```sh
    docker run -d --name website-utama --network my-evita-ishtar-dewi-network -p 8080:80 website-utama
    ```

## Pengujian
1. Akses website utama di `http://localhost:8080`.
2. Klik link "Profil Saya" dan pastikan link tersebut mengarah dan menampilkan halaman profil.
