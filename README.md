# Praktikum 5 - JavaScript

**Nama : M. Iqbal**

**Nim : 312410212**

**Kelas : TI.24.A2**

**Matkul : Pemrograman Web 1**

---
## Tujuan
1. Mahasiswa memahami sintaks dasar JavaScript.
2. Mahasiswa dapat menggunakan JavaScript untuk interaksi pada halaman web.
3. Mahasiswa dapat membuat script sederhana untuk validasi form.
4. Mahasiswa mampu memanipulasi elemen HTML menggunakan JavaScript.
---
## Langkah-langkah
1. Membuat folder lab5_javascript.
2. Membuat file validasi_form.html.
3. Menuliskan kode validasi seperti di atas.
4. Melakukan uji coba pada browser.
---
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Validasi Form dengan JavaScript</title>
    <script>
        function validasiForm() {
            let nama = document.forms["formData"]["nama"].value;
            let email = document.forms["formData"]["email"].value;
            let usia = document.forms["formData"]["usia"].value;
            let pesan = document.forms["formData"]["pesan"].value;

            // Validasi Nama
            if (nama == "") {
                alert("Nama tidak boleh kosong!");
                return false;
            }

            // Validasi Email
            if (email == "") {
                alert("Email harus diisi!");
                return false;
            } else if (!email.includes("@") || !email.includes(".")) {
                alert("Format email tidak valid!");
                return false;
            }

            // Validasi Usia
            if (usia == "" || isNaN(usia)) {
                alert("Usia harus berupa angka!");
                return false;
            } else if (usia < 17) {
                alert("Usia minimal 17 tahun!");
                return false;
            }

            // Validasi Pesan
            if (pesan == "") {
                alert("Pesan tidak boleh kosong!");
                return false;
            }

            alert("Form berhasil dikirim!");
            return true;
        }
    </script>
</head>
<body>
    <h2>Form Validasi JavaScript</h2>
    <form name="formData" onsubmit="return validasiForm()">
        <label>Nama:</label><br>
        <input type="text" name="nama"><br><br>

        <label>Email:</label><br>
        <input type="text" name="email"><br><br>

        <label>Usia:</label><br>
        <input type="text" name="usia"><br><br>

        <label>Pesan:</label><br>
        <textarea name="pesan"></textarea><br><br>

        <input type="submit" value="Kirim">
    </form>
</body>
```
---

## Hasil Tampilan

<img width="1912" height="783" alt="Screenshot 2025-10-21 011636" src="https://github.com/user-attachments/assets/a0091216-06a1-4c66-a565-4cd97fd4372d" />

---

## Penjelasan

1. Baris <script> berisi fungsi validasiForm() untuk mengecek input user.
2. document.forms["formData"] mengambil data dari form berdasarkan nama form.
3. alert() digunakan untuk menampilkan pesan peringatan bila input salah atau kosong.
4. return false menghentikan pengiriman form jika ada kesalahan input.
5. return true melanjutkan proses jika semua input valid.
