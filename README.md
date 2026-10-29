# Praktikum 6: DOM dan Event JavaScript - Pemrograman Web
Repository ini dibuat untuk menyelesaikan tugas Praktikum 6 Pemrograman Web.
 
## Identitas Mahasiswa
 
| Keterangan      | Data                          |
| --------------- | --------------------          |
| **Nama**        | Noel Marihot Tampubolon       |
| **Kelas**       | I251B                         |
| **NIM**         | 312510326                     |
| **Mata Kuliah** | Pemrograman Web               |
| **Dosen**       | Agung Nugroho, S.Kom., M.Kom. |
 
---
## Tujuan Praktikum
 
- Mahasiswa mampu memahami konsep DOM (Document Object Model) sebagai struktur dokumen HTML yang dapat diubah oleh JavaScript.
- Mahasiswa mampu memilih elemen HTML menggunakan `getElementById()`, `querySelector()`, dan `querySelectorAll()`.
- Mahasiswa mampu menangani event (`click`, `input`, `submit`) menggunakan `addEventListener()`.
- Mahasiswa mampu mengubah teks, class, dan gaya CSS secara dinamis menggunakan `textContent` dan `classList`.
- Mahasiswa mampu membuat validasi form sederhana menggunakan `preventDefault()`.
- Mahasiswa mampu membuat aplikasi interaktif sederhana (To-do List dan Form Pendaftaran Workshop).
---
 
## Struktur File Proyek
 
```
Lab6Web/
├── MiniProject/
│   ├── index.html
│   ├── script.js
│   └── style.css
├── index.html
├── script.js
├── style.css
└── README.md
```
| File / Folder | Keterangan |
| ------------- | ---------- |
| `index.html`  | Halaman utama praktikum (DOM, event click, event input, validasi form, To-do List, eksperimen mandiri) |
| `script.js`   | Seluruh logika JavaScript untuk halaman utama |
| `style.css`   | Style untuk class `highlight`, `teks-besar`, `selesai`, dan `sembunyi` |
| `MiniProject/` | Mini project Form Pendaftaran Workshop (HTML, CSS, dan JavaScript tersendiri) |
 

<img width="227" height="213" alt="image" src="https://github.com/user-attachments/assets/6cd67f16-3a57-4032-b721-bea9f18fa66e" />

---
 
## Cara Menjalankan
 
1. Clone atau download repository ini.
```bash
   git clone <url-repository>
```
2. Buka folder `Lab6Web` menggunakan **Visual Studio Code**.
3. Install ekstensi **Live Server** (jika belum ada).
4. Klik kanan pada `index.html`, lalu pilih **Open with Live Server**.
5. Halaman akan terbuka di browser, contohnya `http://127.0.0.1:5500/index.html`.
6. Untuk Mini Project, buka `MiniProject/index.html` dengan cara yang sama (`http://127.0.0.1:5500/MiniProject/index.html`).
7. Untuk melihat pesan error atau hasil `console`, buka **DevTools** browser dengan menekan `F12`.
> Alternatif: file `index.html` juga bisa langsung dibuka dengan double-click di browser tanpa Live Server.
 
---
 ## Langkah-langkah Praktikum
 
### 1. Menyiapkan Dokumen HTML dan Mengubah Teks dengan DOM
 
Membuat dokumen `index.html` dengan judul "Praktikum DOM dan Event" yang berisi `<h1 id="judul">`, `<p id="pesan">`, dan `<button id="tombolAksi">`.
 
<img width="803" height="336" alt="image" src="https://github.com/user-attachments/assets/a58b1840-2d50-4f87-91bd-935a2fccf45a" />

Hasil sebelum menggunakan `script.js`:
 
<img width="436" height="256" alt="image" src="https://github.com/user-attachments/assets/f9cd16c2-953c-4315-af20-fb5f66f3a85f" />

Kemudian dibuat `script.js` untuk mengambil elemen dengan `getElementById()` dan mengubah isinya menggunakan `textContent`.
 
```js
const judul = document.getElementById("judul");
const pesan = document.getElementById("pesan");
judul.textContent = "Belajar JavaScript DOM";
pesan.textContent = "Konten berhasil diubah oleh JavaScript.";
```
 
Hasil di browser: judul berubah menjadi "Belajar JavaScript DOM" dan pesan menjadi "Konten berhasil diubah oleh JavaScript."
 
<img width="561" height="314" alt="image" src="https://github.com/user-attachments/assets/fc966e59-eb2e-4ce5-a70a-10ce9cf5e870" />

---
 
### 2. Event Click
 
Menambahkan `addEventListener("click", ...)` pada tombol "Klik saya" untuk menampilkan waktu saat tombol ditekan.

<img width="1078" height="129" alt="image" src="https://github.com/user-attachments/assets/872e74dc-87b2-4963-976d-e6a7d1de17f9" />

 
Hasil di browser: setelah tombol diklik, muncul teks "Tombol diklik pada 18.34.36" (sesuai waktu saat diklik).
 
<img width="486" height="252" alt="image" src="https://github.com/user-attachments/assets/d4c4d13f-d116-4d20-b0ef-8b3e6f51f884" />

---
 
### 3. Mengubah Kelas dan Gaya CSS
 
Menambahkan paragraf `#teksGaya` dan tombol `#tombolGaya` pada HTML. Saat tombol diklik, class `highlight` dan `teks-besar` di-*toggle* menggunakan `classList.toggle()`.
 
<img width="729" height="157" alt="image" src="https://github.com/user-attachments/assets/b7aacaea-69d1-4594-b0af-288abef84fca" />

<img width="753" height="185" alt="image" src="https://github.com/user-attachments/assets/369f19a8-64f5-4f28-9bea-7d2db4acdef8" />


 
CSS yang digunakan pada `style.css`:
-
 
<img width="410" height="243" alt="image" src="https://github.com/user-attachments/assets/99b2e6b0-7da7-44c5-914c-f215aa8a1047" />

 
Hasil di browser: teks berubah menjadi bergaya highlight dengan ukuran font lebih besar, dan kembali normal jika tombol diklik lagi.
 
<img width="337" height="104" alt="image" src="https://github.com/user-attachments/assets/c96b5c49-7fe9-4a99-8e93-3a12872ff804" />

<img width="450" height="173" alt="image" src="https://github.com/user-attachments/assets/51c1b2ca-bd4f-4ae8-a162-b8cc6a960bc7" />

---
 
### 4. Event Input dan Penghitung Karakter
 
Menambahkan `<input type="text" id="namaInput" maxlength="40">` dan `<span id="jumlahKarakter">`. Event `input` digunakan agar jumlah karakter terupdate setiap kali pengguna mengetik.
 
> Catatan: ditambahkan tag `<br /><br />` sebagai pemisah karena kotak input nama tidak turun ke baris baru.
 
<img width="853" height="282" alt="image" src="https://github.com/user-attachments/assets/d2960d70-96a7-4688-aa97-2274f20cf60a" />

 <img width="887" height="160" alt="image" src="https://github.com/user-attachments/assets/231e9456-6fd0-43cc-a184-1af707700970" />

Hasil di browser: saat mengetik "Rafli Putra Sudrajat", tampil "Jumlah karakter: 20".
 
<img width="372" height="105" alt="image" src="https://github.com/user-attachments/assets/b543ff1b-aefc-4d5a-a204-dd78c5a3d400" />

<img width="373" height="111" alt="image" src="https://github.com/user-attachments/assets/771da4f4-ce10-4dca-91ea-c02761be6ced" />

---
 
### 5. Validasi Form Pendaftaran
 
Membuat form pendaftaran (`#formPendaftaran`) dengan field Nama lengkap, Email, dan Usia (17-100). Atribut `novalidate` dipakai agar validasi dilakukan sendiri oleh JavaScript. Pada event `submit`, `event.preventDefault()` mencegah reload halaman, lalu input divalidasi:
 
- Nama tidak boleh kosong.
- Email harus sesuai format (regex).
- Usia harus berupa bilangan bulat 17-100.
Jika semua valid, pesan "Validasi berhasil. Form siap diproses." ditampilkan dan form di-reset.
 
<img width="836" height="300" alt="image" src="https://github.com/user-attachments/assets/5b752197-4297-48b1-8ec5-d8f9c9bbd227" />
<img width="842" height="452" alt="image" src="https://github.com/user-attachments/assets/eb649bce-e2d6-4aff-8e62-1182dd9cf323" />

Hasil di browser:
 
- Input valid → muncul pesan "Validasi berhasil. Formulir siap diproses."
- Email tidak valid (`emailtidakvalid`) → muncul pesan "Masukkan email yang valid."
<img width="859" height="60" alt="image" src="https://github.com/user-attachments/assets/2963774f-0279-43ee-9ab6-015bdefbcd9f" />
<img width="872" height="66" alt="image" src="https://github.com/user-attachments/assets/6b95d000-82cb-4824-a014-705a9df52636" />
<img width="881" height="81" alt="image" src="https://github.com/user-attachments/assets/c40f39bf-f983-43bd-ae15-3001b58c9325" />

<img width="881" height="109" alt="image" src="https://github.com/user-attachments/assets/7996638a-a2af-4e83-882f-3be377b6a98c" />

---
 
### 6. Daftar Tugas Sederhana (To-do List)
 
Membuat `<section>` berisi input `#inputTugas`, tombol `#tambahTugas`, pesan `#pesanTugas`, dan daftar `<ul id="daftarTugas">`. Saat tombol "Tambah" diklik:
 
- Jika input kosong → muncul pesan "Tulis tugas terlebih dahulu."
- Jika terisi → dibuat elemen `<li>` baru dengan `createElement()` berisi teks tugas dan tombol "Tandai selesai".
- Tombol "Tandai selesai" men-*toggle* class `selesai` (teks dicoret) dan mengubah label tombol menjadi "Batalkan selesai".
<img width="540" height="261" alt="image" src="https://github.com/user-attachments/assets/d653425b-b589-4437-b0cf-739c4f0ab127" />

<img width="714" height="428" alt="image" src="https://github.com/user-attachments/assets/dcedff29-26ba-4c54-a9c9-9722ce26d58c" />

Hasil di browser:
<img width="424" height="118" alt="image" src="https://github.com/user-attachments/assets/2cd81823-062a-4b56-bf6d-22d79126d4b6" />
<img width="388" height="185" alt="image" src="https://github.com/user-attachments/assets/0c9f6522-747c-4b9a-a86e-bedada92b9b6" />
<img width="364" height="167" alt="image" src="https://github.com/user-attachments/assets/16554ead-e7a9-49e7-92fc-e3aa55d43e08" />

---
 
## Mini Project: Form Pendaftaran Workshop
 
Mini project berada di folder `MiniProject/` dan berisi form pendaftaran workshop dengan fitur:
 
- Field **Nama Lengkap**, **Alamat Email**, **Pilih Sesi** (Sesi Pagi 08:00 - 12:00 / Sesi Siang 13:00 - 17:00), dan **Ringkasan / Alasan Mengikuti** (textarea).
- **Penghitung karakter** pada textarea secara langsung menggunakan event `input` (maksimal 200 karakter, warna berubah merah jika melebihi batas).
- **Validasi** pada event `submit` dengan `preventDefault()` untuk nama, email, pilihan sesi, dan panjang alasan.
- **Pesan notifikasi** sukses (`alert-success`) atau gagal (`alert-error`).
- **Tombol Reset** yang membersihkan input, pesan error, dan hitungan karakter melalui event `reset`.
<img width="536" height="375" alt="image" src="https://github.com/user-attachments/assets/db8cf97b-d709-40a7-a982-b6e67429e40a" />

<img width="518" height="372" alt="image" src="https://github.com/user-attachments/assets/31f15351-a116-4897-adae-c29364aa5e8a" />

<img width="394" height="511" alt="image" src="https://github.com/user-attachments/assets/64d69cb9-fa87-4a35-9d8c-1b4251d2ea1b" />

Code Script.Js
---
<img width="561" height="535" alt="image" src="https://github.com/user-attachments/assets/af902af8-d62a-45a4-87b8-69686bd94bc8" />


Hasil tampilan di browser (desktop):
--- 
<img width="743" height="329" alt="image" src="https://github.com/user-attachments/assets/1163f9b1-9c0f-4bdb-8866-88977560d45a" />
<img width="414" height="439" alt="image" src="https://github.com/user-attachments/assets/76c9a554-03a5-47ad-ba84-94a19d8c0a69" />


Hasil tampilan responsif (mobile) saat validasi gagal karena alasan melebihi 200 karakter:
---
 <img width="999" height="525" alt="image" src="https://github.com/user-attachments/assets/1aa8af81-1ff6-49fb-8a3f-f95aeecccf69" />

---
 
## Eksperimen Mandiri
 
### 1. To-do List dengan Tombol Hapus
 
Setiap item tugas diberi tombol "Hapus" (class `btn-hapus`). Saat diklik, item dihapus dari daftar dan muncul pesan "Tugas dihapus."
 
<img width="767" height="544" alt="image" src="https://github.com/user-attachments/assets/25e2fc0e-671d-4741-9e49-98113dab3289" />

code Script.js
---
<img width="780" height="296" alt="image" src="https://github.com/user-attachments/assets/320beecc-2108-4f2b-89b6-4950daa63555" />

Sebelum dihapus:
---
 <img width="340" height="219" alt="image" src="https://github.com/user-attachments/assets/87c6ddc5-0012-457d-9d46-7803f1f3a460" />

Sesudah tugas "Pemograman Web" dihapus:
---

<img width="364" height="209" alt="image" src="https://github.com/user-attachments/assets/0c7411d9-98c5-4069-b713-afc302bc2850" />
 
### 3. Validasi Tambahan: Nama Minimal 3 Karakter
 
Pada Form Pendaftaran Workshop ditambahkan validasi tambahan menggunakan `querySelector()` untuk memastikan nama minimal terdiri dari 3 karakter. Jika kurang, `preventDefault()` dan `stopImmediatePropagation()` dipanggil, pesan "Nama minimal terdiri dari tiga karakter." ditampilkan, dan fokus dikembalikan ke input nama.
 
<img width="550" height="91" alt="image" src="https://github.com/user-attachments/assets/b03a5fb4-e4d1-4b70-b133-b190ff4ff4c9" />

Code script.Js
---
<img width="422" height="266" alt="image" src="https://github.com/user-attachments/assets/377c27a3-c0dc-4017-8c98-ce2fcf1816e2" />


Tampilan pilihan sesi pada mobile
--
<img width="417" height="182" alt="image" src="https://github.com/user-attachments/assets/bf9f6aa3-21a7-4dce-84a4-fe723ec473ff" />

Dropdown pada From Sesi Workshop
---
<img width="215" height="391" alt="image" src="https://github.com/user-attachments/assets/8f57ce8e-12ba-4eb0-b6fe-394d5a31f813" />



### 4. Menyembunyikan / Menampilkan Paragraf dengan Class CSS
 
Menambahkan class `.sembunyi { display: none; }` dan tombol `#btnToggleParagraf`. Saat diklik, class `sembunyi` di-*toggle* pada paragraf dan teks tombol berganti antara "Sembunyikan" dan "Tampilkan".
 
<img width="1078" height="136" alt="image" src="https://github.com/user-attachments/assets/6341faa2-a903-4982-be76-f2d3aa769921" />

Code Style.Css
---
<img width="320" height="105" alt="image" src="https://github.com/user-attachments/assets/117ba51a-1f01-4596-b0a0-f49939cbc841" />

Code Script.js
---
<img width="817" height="122" alt="image" src="https://github.com/user-attachments/assets/89f8ce73-d447-479e-81cd-9c7bd0afbaf8" />


 Hasil nya :

 Sebelum di klik 
 ---
<img width="498" height="117" alt="image" src="https://github.com/user-attachments/assets/a1a5bae9-3fcf-4a58-9f6b-d1429af55182" />

Setelah di klik 
---
<img width="267" height="91" alt="image" src="https://github.com/user-attachments/assets/1db171cb-8997-471d-bcba-fd6791a71aa2" />

### 5. Script di `<head>` Tanpa `defer`
 
Tag `<script src="script.js">` dipindahkan ke dalam `<head>` **tanpa** atribut `defer`. Hasilnya, console menampilkan error:

<img width="678" height="169" alt="image" src="https://github.com/user-attachments/assets/4ad8eaca-0b8c-4da7-9e96-1d3519322ab4" />

 
Error terjadi karena script dijalankan sebelum elemen HTML selesai dimuat, sehingga `getElementById()` mengembalikan `null`. Solusinya adalah meletakkan script di akhir `<body>` atau menambahkan atribut `defer` pada tag script.
 
<img width="827" height="334" alt="image" src="https://github.com/user-attachments/assets/7ca377bf-0768-4b60-822e-84c52d3ddbc6" />

---
 
## Pertanyaan Evaluasi
 
1. **DOM**: Struktur dokumen HTML yang memungkinkan JavaScript mengubah isi atau gaya web secara dinamis tanpa reload halaman.
2. **Pemilih elemen**:
   - `getElementById()`: mengambil 1 elemen spesifik melalui atribut ID.
   - `querySelector()`: mengambil 1 elemen pertama berdasarkan selector CSS.
   - `querySelectorAll()`: mengambil semua elemen berdasarkan selector CSS (berupa kumpulan data / NodeList).
3. **`addEventListener()`**: perintah untuk mendeteksi aksi pada elemen web. Tiga contoh event: `click`, `input`, dan `submit`.
4. **`preventDefault()`**: mencegah perilaku bawaan browser, yaitu reload halaman saat formulir di-submit.
5. **`textContent` vs `innerHTML`**: `textContent` menyisipkan teks mentah (aman), sedangkan `innerHTML` mengeksekusi tag HTML sehingga rentan terhadap serangan XSS.
6. **`classList.toggle()`**: bekerja seperti saklar on/off, yaitu menambah class CSS jika belum ada dan menghapusnya jika sudah ada.
7. **3 skenario validasi**: menguji input kosong, menguji format penulisan yang salah (misalnya email), dan menguji batasan jumlah karakter input.
---
 
## Kesimpulan
 
Pada praktikum ini telah dipelajari cara memanipulasi DOM menggunakan JavaScript, mulai dari memilih elemen, mengubah teks dengan `textContent`, mengubah class dan gaya dengan `classList`, hingga menangani event `click`, `input`, `submit`, dan `reset`. Selain itu dibuat juga validasi form, To-do List dinamis, dan Mini Project Form Pendaftaran Workshop. Dari eksperimen mandiri juga dipahami bahwa urutan pemuatan script berpengaruh terhadap keberhasilan akses elemen DOM, sehingga script perlu diletakkan di akhir `<body>` atau memakai atribut `defer`.
