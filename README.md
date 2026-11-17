# Katalog Produk (JavaFX + SQLite)

Aplikasi sederhana untuk mengelola katalog produk (tambah, ubah, hapus) menggunakan JavaFX, FXML, Maven, dan database SQLite.

## Kebutuhan
- JDK 17 atau lebih baru
- Apache NetBeans
- Koneksi internet (Maven mengunduh library JavaFX dan SQLite saat pertama kali build)

## Cara Membuka Proyek di NetBeans

### Opsi A: Clone langsung dari GitHub
1. Buka NetBeans.
2. Pilih menu **Team > Git > Clone**.
3. Isi **Repository URL** dengan alamat repo GitHub proyek ini, 'https://github.com/nadillasri12/katalogprodukdatabase.git'
4. Kosongkan kolom Username dan Password (repo bersifat publik), lalu klik **Next**.
5. Pilih branch **main**, lalu klik **Next**.
6. Tentukan folder tujuan di komputer, lalu klik **Finish**.
7. Saat muncul pertanyaan "Open Project?", klik **Open Project**.

### Opsi B: Download ZIP
1. Di halaman repo GitHub, klik tombol hijau **Code > Download ZIP**.
2. Ekstrak file ZIP tersebut.
3. Di NetBeans, pilih **File > Open Project**, lalu pilih folder `KatalogProduk` hasil ekstrak.

## Cara Menjalankan Aplikasi
1. Tunggu NetBeans selesai mengunduh dependency (lihat progress bar di pojok kanan bawah).
2. Klik kanan proyek **KatalogProduk**, lalu pilih **Properties > Actions**.
3. Pilih **Run project**, lalu isi **Execute Goals** dengan:
   `clean javafx:run`
4. Pilih **Debug project**, lalu isi **Execute Goals** dengan:
   `clean javafx:run@ide-debug`
5. Klik **OK**.
6. Jalankan dengan **Run Project** (F6) atau tombol hijau di toolbar.

Catatan: gunakan **Run Project**, bukan Run File pada `MainApp.java`. File database (`data/katalog.db`) dibuat otomatis kalau belum ada.

### Alternatif lewat terminal
Buka terminal di folder proyek, lalu jalankan:

    mvn clean javafx:run

## Cara Menggunakan Aplikasi
1. Isi **Nama produk**, **Harga** (angka bulat, contoh 5000), dan pilih **Foto contoh**, lalu klik **Simpan**.
2. Produk yang tersimpan muncul sebagai kartu di katalog.
3. Klik **Edit** pada kartu untuk mengubah data, lalu klik **Simpan Perubahan** (atau **Batal**).
4. Klik **Hapus** pada kartu, lalu pilih **OK** pada dialog konfirmasi.


## Tampilan Aplikasi

1. Tampilan awal aplikasi Katalog Produk. Form input (Nama produk, Harga, Foto contoh) masih kosong dan Jumlah produk masih 0, jadi belum ada data yang tampil di katalog.
<img width="999" height="569" alt="Screenshot 2026-11-17 203320" src="https://github.com/user-attachments/assets/13015772-5cba-4015-ab5f-6ddd9d53180b" />



2. Validasi input kosong. Saat tombol Simpan diklik dengan semua kolom kosong, aplikasi menampilkan pesan "Isi lengkap semua kolom. Harga harus angka bulat, contoh 5000", dan data tidak disimpan.
<img width="998" height="523" alt="Screenshot 2026-11-17 203343" src="https://github.com/user-attachments/assets/dee96e3d-3fd3-4406-bba6-937db92d27e8" />



3. Fitur tambah produk (Create). Setelah form diisi dan Simpan diklik, muncul pesan "Produk berhasil disimpan". Produk "kedelai hangat" seharga Rp3000 tampil sebagai kartu di katalog, dan Jumlah produk menjadi 1.
<img width="997" height="713" alt="Screenshot 2026-11-17 203419" src="https://github.com/user-attachments/assets/de208dc4-e9d5-43e0-a959-b5c802b9b43b" />



4. Validasi harga. Nama produk sudah diisi tetapi harga kosong, sehingga aplikasi menolak penyimpanan dan menampilkan pesan peringatan bahwa semua kolom harus diisi dengan harga berupa angka bulat.
<img width="1000" height="683" alt="Screenshot 2026-11-17 203454" src="https://github.com/user-attachments/assets/ac49e66b-ed18-4425-8e0e-11cd5730a68b" />



5. Validasi nama produk. Harga sudah diisi tetapi nama kosong, sehingga muncul pesan "Nama produk wajib diisi" dan jumlah produk tetap 1.
<img width="997" height="707" alt="Screenshot 2026-11-17 203520" src="https://github.com/user-attachments/assets/f20757eb-239b-4367-8cce-2296f4314238" />



6. Fitur ubah produk (Update), tahap edit. Setelah tombol Edit pada produk ID 1 diklik, data produk dimuat kembali ke form. Tombol berubah menjadi "Simpan Perubahan" dan "Batal", disertai pesan "Mengedit produk ID 1".
<img width="993" height="713" alt="Screenshot 2026-11-17 205050" src="https://github.com/user-attachments/assets/dc345f2f-be74-4ec7-ba3f-0bb1293519b3" />



7. Hasil ubah produk. Setelah Simpan Perubahan diklik, muncul pesan "Produk berhasil diperbarui" dan foto produk "kedelai hangat" berubah dari roti.png menjadi susu.png. Katalog kini berisi 2 produk.
<img width="994" height="710" alt="Screenshot 2026-11-17 205107" src="https://github.com/user-attachments/assets/9929c210-beee-4a1e-9141-850d9ef380dd" />



8. Konfirmasi hapus (Delete). Saat tombol Hapus diklik, muncul dialog konfirmasi "Hapus 'kedelai dingin'?" dengan peringatan bahwa data akan dihapus permanen dari database. Pengguna dapat memilih OK atau Cancel.
<img width="996" height="710" alt="Screenshot 2026-11-17 205137" src="https://github.com/user-attachments/assets/b26a7081-50c3-4de8-ba0f-f18d492f9a5f" />



9. Hasil hapus produk. Setelah OK dipilih, muncul pesan "Produk berhasil dihapus", produk yang dipilih hilang dari katalog, dan Jumlah produk berkurang menjadi 1.
<img width="997" height="698" alt="Screenshot 2026-11-17 205155" src="https://github.com/user-attachments/assets/8e06d9c6-a170-48da-a035-fa38e032a1b2" />
