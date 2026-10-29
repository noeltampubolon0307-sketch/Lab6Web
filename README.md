# Praktikum 6: DOM dan Event JavaScript - Pemrograman Web
Repository ini dibuat untuk menyelesaikan tugas Praktikum 6 Pemrograman Web.
 
## Identitas Mahasiswa
 
| Keterangan      | Data                          |
| --------------- | --------------------          |
| **Nama**        | Noel Marihot Tampubolon       |
| **Kelas**       | I251D                         |
| **NIM**         | 312510419                     |
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
 
<img width="118" height="204" alt="ss pertama" src="https://github.com/user-attachments/assets/71cfa3a7-1cf0-4fb0-98fd-f63915e5fb4d" />

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
 
<img width="657" height="269" alt="ss pertama benar" src="https://github.com/user-attachments/assets/41bed784-ad4f-41eb-a95f-837cc09c0c95" />

Hasil sebelum menggunakan `script.js`:
 
<img width="230" height="148" alt="ss ke 2" src="https://github.com/user-attachments/assets/3dd508ab-8bf0-4dd2-850b-8285451396ba" />

Kemudian dibuat `script.js` untuk mengambil elemen dengan `getElementById()` dan mengubah isinya menggunakan `textContent`.
 
```js
const judul = document.getElementById("judul");
const pesan = document.getElementById("pesan");
judul.textContent = "Belajar JavaScript DOM";
pesan.textContent = "Konten berhasil diubah oleh JavaScript.";
```
 
Hasil di browser: judul berubah menjadi "Belajar JavaScript DOM" dan pesan menjadi "Konten berhasil diubah oleh JavaScript."
 
<img width="362" height="142" alt="ss defer yang belum" src="https://github.com/user-attachments/assets/25f70d6a-c412-42a6-9070-b7d246044bac" />

---
 
### 2. Event Click
 
Menambahkan `addEventListener("click", ...)` pada tombol "Klik saya" untuk menampilkan waktu saat tombol ditekan.

<img width="639" height="80" alt="ss ke 4" src="https://github.com/user-attachments/assets/f8885dc9-0442-4c0b-9698-5b7f780965bc" />

 
Hasil di browser: setelah tombol diklik, muncul teks "Tombol diklik pada 4.20.36" (sesuai waktu saat diklik).
 
<img width="373" height="142" alt="ss defer" src="https://github.com/user-attachments/assets/2a715d42-d060-47b5-903e-fec35fa12a1f" />

---
 
### 3. Mengubah Kelas dan Gaya CSS
 
Menambahkan paragraf `#teksGaya` dan tombol `#tombolGaya` pada HTML. Saat tombol diklik, class `highlight` dan `teks-besar` di-*toggle* menggunakan `classList.toggle()`.
 

<img width="558" height="119" alt="ss ke 5" src="https://github.com/user-attachments/assets/4116ac33-fe52-415a-85a6-f6cff8ba36bf" />

<img width="497" height="116" alt="ss ke 6" src="https://github.com/user-attachments/assets/8327ad81-9e82-4a60-bbe7-180a3b8fde64" />



 
CSS yang digunakan pada `style.css`:
-
 

<img width="333" height="195" alt="ss ke 6 benar" src="https://github.com/user-attachments/assets/222336c6-0d96-4341-9294-f118ab293a95" />

 
Hasil di browser: teks berubah menjadi bergaya highlight dengan ukuran font lebih besar, dan kembali normal jika tombol diklik lagi.
 
<img width="337" height="104" alt="image" src="https://github.com/user-attachments/assets/c96b5c49-7fe9-4a99-8e93-3a12872ff804" />

<img width="450" height="173" alt="image" src="https://github.com/user-attachments/assets/51c1b2ca-bd4f-4ae8-a162-b8cc6a960bc7" />

---
 
### 4. Event Input dan Penghitung Karakter
 
Menambahkan `<input type="text" id="namaInput" maxlength="40">` dan `<span id="jumlahKarakter">`. Event `input` digunakan agar jumlah karakter terupdate setiap kali pengguna mengetik.
 
> Catatan: ditambahkan tag `<br /><br />` sebagai pemisah karena kotak input nama tidak turun ke baris baru.

 <img width="540" height="173" alt="ss ke 8" src="https://github.com/user-attachments/assets/a6229a0b-bb58-44f1-ab55-0c7018cad1f5" />


<img width="556" height="95" alt="ss ke 9" src="https://github.com/user-attachments/assets/7a7fcc93-db94-4d7b-80a7-16dd5a7ddbcd" />

Hasil di browser: saat mengetik "Noel Marihot Tampubolon", tampil "Jumlah karakter: 23".
 
<img width="372" height="105" alt="image" src="https://github.com/user-attachments/assets/b543ff1b-aefc-4d5a-a204-dd78c5a3d400" />

<img width="246" height="71" alt="ss ke 10" src="https://github.com/user-attachments/assets/9b4f1692-4b12-4bf0-b313-483e0eb3968a" />

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
<img width="2928" height="222" alt="ss email noel" src="https://github.com/user-attachments/assets/46b75382-5c23-47c5-978d-9eaa9a4181ee" />
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

<img width="668" height="693" alt="ss projek" src="https://github.com/user-attachments/assets/15972f1d-a6f2-4510-9bea-1879aef3caaa" />


<img width="617" height="592" alt="ss projek 2" src="https://github.com/user-attachments/assets/217b058c-6b9e-42c6-9b51-f1595214834d" />


<img width="626" height="630" alt="ss script js" src="https://github.com/user-attachments/assets/037b9bd7-0f90-43e3-8c47-fab47da7237c" />

Code Script.Js
---

<img width="686" height="670" alt="ss script js 2" src="https://github.com/user-attachments/assets/3161a798-a4cd-4eb7-ac7f-ace1b34137c0" />

<img width="677" height="666" alt="ss script js 3" src="https://github.com/user-attachments/assets/4ef26df1-f8d3-4e96-802b-904fca6f29bc" />

<img width="670" height="210" alt="ss script 4" src="https://github.com/user-attachments/assets/0bb06eba-5b21-46c6-916d-27f1fb13895c" />



Hasil tampilan di browser (desktop):
--- 

<img width="1535" height="863" alt="ss workshop" src="https://github.com/user-attachments/assets/31dd0ca3-faa3-4ccd-94e9-a735c5774e5b" />

<img width="654" height="610" alt="ss workshop 2" src="https://github.com/user-attachments/assets/b3a52a4a-60b9-455b-9ed9-116845943050" />


Hasil tampilan responsif (mobile) saat validasi gagal karena alasan melebihi 200 karakter:
---

<img width="1424" height="748" alt="ss email salah" src="https://github.com/user-attachments/assets/c4545bbb-2af3-4a8c-83cd-1f1d419d7d71" />

---
 
## Eksperimen Mandiri
 
### 1. To-do List dengan Tombol Hapus
 
Setiap item tugas diberi tombol "Hapus" (class `btn-hapus`). Saat diklik, item dihapus dari daftar dan muncul pesan "Tugas dihapus."
 

<img width="553" height="348" alt="ss todolist" src="https://github.com/user-attachments/assets/5f1202eb-fe69-473e-a621-3a5dc1fd2dff" />

code Script.js
---

<img width="459" height="202" alt="ss tombol tugas" src="https://github.com/user-attachments/assets/9e3fb167-93ee-4265-8ce1-2f26eff06351" />

Sebelum dihapus:
---
 <img width="340" height="219" alt="image" src="https://github.com/user-attachments/assets/87c6ddc5-0012-457d-9d46-7803f1f3a460" />

Sesudah tugas "Pemograman Web" dihapus:
---

<img width="364" height="209" alt="image" src="https://github.com/user-attachments/assets/0c7411d9-98c5-4069-b713-afc302bc2850" />
 
### 3. Validasi Tambahan: Nama Minimal 3 Karakter
 
Pada Form Pendaftaran Workshop ditambahkan validasi tambahan menggunakan `querySelector()` untuk memastikan nama minimal terdiri dari 3 karakter. Jika kurang, `preventDefault()` dan `stopImmediatePropagation()` dipanggil, pesan "Nama minimal terdiri dari tiga karakter." ditampilkan, dan fokus dikembalikan ke input nama.
 

<img width="523" height="218" alt="ss mini project" src="https://github.com/user-attachments/assets/aa109a5c-86b2-4c5d-ab54-e637b0fb34f3" />

Code script.Js
---

<img width="661" height="495" alt="ss validasi nama" src="https://github.com/user-attachments/assets/cb48313a-ef22-42d8-b114-82ebbe1bc6f4" />


Tampilan pilihan sesi pada mobile
--
<img width="417" height="182" alt="image" src="https://github.com/user-attachments/assets/bf9f6aa3-21a7-4dce-84a4-fe723ec473ff" />

Dropdown pada From Sesi Workshop
---

<img width="768" height="1397" alt="ss email di hp" src="https://github.com/user-attachments/assets/298e44cf-a8c6-4903-8d04-18f91b788041" />



### 4. Menyembunyikan / Menampilkan Paragraf dengan Class CSS
 
Menambahkan class `.sembunyi { display: none; }` dan tombol `#btnToggleParagraf`. Saat diklik, class `sembunyi` di-*toggle* pada paragraf dan teks tombol berganti antara "Sembunyikan" dan "Tampilkan".
 

<img width="674" height="189" alt="ss akhir" src="https://github.com/user-attachments/assets/6b65c7ea-b198-426b-b57d-e7d698e9135a" />

Code Style.Css
---

<img width="196" height="62" alt="ss akhir 2" src="https://github.com/user-attachments/assets/584aa5fb-5fe7-4072-9169-4b2a07d9c5d4" />

Code Script.js
---

<img width="673" height="214" alt="ss akhir 3" src="https://github.com/user-attachments/assets/22488bd9-b04d-4d47-b6c7-5bf02d7b4268" />


 Hasil nya :

 Sebelum di klik 
 ---
<img width="498" height="117" alt="image" src="https://github.com/user-attachments/assets/a1a5bae9-3fcf-4a58-9f6b-d1429af55182" />

Setelah di klik 
---
<img width="267" height="91" alt="image" src="https://github.com/user-attachments/assets/1db171cb-8997-471d-bcba-fd6791a71aa2" />

### 5. Script di `<head>` Tanpa `defer`
 
Tag `<script src="script.js">` dipindahkan ke dalam `<head>` **tanpa** atribut `defer`. Hasilnya, console menampilkan error:


<img width="651" height="191" alt="ss end benar" src="https://github.com/user-attachments/assets/55d40771-ffb5-4fba-b5d6-536958fe66ad" />

 
Error terjadi karena script dijalankan sebelum elemen HTML selesai dimuat, sehingga `getElementById()` mengembalikan `null`. Solusinya adalah meletakkan script di akhir `<body>` atau menambahkan atribut `defer` pada tag script.
 

<img width="1920" height="1080" alt="Screenshot 2026-10-29 182544" src="https://github.com/user-attachments/assets/202a3891-3b57-4ff2-bf95-35d5cae0605a" />

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
