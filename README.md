# Lab2Web
## Praktikum 2: PHP Dasar
## Membuat program PHP sederhana.


### Instruksi Praktikum
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab2_php_dasar pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.


### Langkah-langkah Praktikum

#### Persiapan

Untuk memulai membuat kode php, perlu disiapkan web server dan interpreter PHP terlebih dahulu.
Web servar yang kita gunakan adalah Apache 2 dan interpreter PHP 7. Untuk memudahkan proses
praktikum, kita gunakan aplikasi bundle web server yaitu XAMPP.


#### Install XAMPP

Unduh XAMPP dari https://www.apachefriends.org/download.html dan pilih versi portable untuk
memudahkan proses installasi. Kemudian extract file tersebut, seusikan direktorinya (misal:
c:\xampp).

![Gambar 1  Extract XAMPP](https://user-images.githubusercontent.com/92704969/226237245-310ced88-a845-4c92-a188-0e8e6aeff42f.png)


#### Konfigurasi Web Server

• Konfigurasi Apache

Untuk konfigurasi HTTP server, seperti port yang digunakan akses HTTP, modul yang diaktifkan,
lokasi document root, dll.

Lokasi file: \xampp\apache\conf\httpd.conf


• Konfigrasi PHP

Untuk konfigurasi perilaku engine PHP yang berefek pada keamanan dan performa. Seperti batas
maksimal waktu eksekusi script, batas file yang dapat diupload, error reporting, dll.

Lokasi file: \xampp\php\php.ini


• Konfigrasi MySql
Konfigurasi server MySQL, seperti administrator user, port, timezone, dll.

Lokasi file: \xampp\mysql\bin\my.ini


#### Menjalankan Web Server
Untuk menjalankan web server dari menu XAMPP Control.


![Gambar 2  XAMPP  Control](https://user-images.githubusercontent.com/92704969/226237299-1603bbff-f9b7-4050-b6b1-ff9d8bb15b01.png)


• Uji coba apakah server sudah berkerja dengan baik
http://127.0.0.1 atau http://localhost

Tampil halaman utama XAMPP jika server sudah berkerja dengan baik.


• Dokumen Website
Semua file website tempatkan di direktori: \xampp\htdocs\


• Database MySQL
Direktori: \xampp\mysql\

Manajemen database: http://localhost/phpmyadmin


#### Memulai PHP
Buat folder lab2_php_dasar pada root directory web server (c:\xampp\htdocs)


![Gambar 3 Directory Lab2](https://user-images.githubusercontent.com/92704969/226237357-5b59bf29-22fa-4f07-92c6-5176e7302a22.png)


Kemudian untuk mengakses direktory tersebut pada web server dengan mengakses URL:
http://localhost/lab2_php_dasar/


![Gambar 4 Tampilan Web Server](https://user-images.githubusercontent.com/92704969/226237391-3f8c3092-7090-4137-bd81-8056afa6e8d1.png)


#### PHP Dasar
Buat file baru dengan nama php_dasar.php pada directory tersebut. Kemudian buat kode seperti
berikut.

```php
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>PHP Dasar</title>
</head>
<body>
<h1>Belajar PHP Dasar</h1>
<?php
echo "Hello World";
?>
</body>
</html>
```

Kemudian untuk mengakses hasilnya melalui URL: http://localhost/lab2_php_dasar/php_dasar.php


![Gambar 5 Tampilan Dasar PHP](https://user-images.githubusercontent.com/92704969/226238091-08b488bb-7896-46b2-80b6-00260de37645.png)


#### Variable PHP
Menambahkan variable pada program.

```php
<?php
$nim = "0411500400";
$nama = 'Abdullah';
echo "NIM : " . $nim . "<br>";
echo "Nama : $nama";
?>
```

![Gambar 6 Variable PHP](https://user-images.githubusercontent.com/92704969/226238412-0c8b1068-4f8e-4e07-bd8a-eca3d75a196f.png)


#### Predefine Variable $_GET

```php
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
```

Untuk mengaksesnya gunakan URL: http://localhost/lab2_php_dasar/latihan2.php?nama=Yusuf%20Putra%20Bintang%20Satria


![Gambar 7 Predefine Variable](https://user-images.githubusercontent.com/92704969/226239318-e3dc27ba-84e3-4686-a8b2-c7c34ae73e00.png)


#### Membuat Form Input

```php
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>PHP Dasar</title>
</head>
<body>
<h2>Form Input</h2>
<form method="post">
<label>Nama: </label>
<input type="text" name="nama">
<input type="submit" value="Kirim">
</form>
<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```

![Gambar 8 Form Input](https://user-images.githubusercontent.com/92704969/226239680-4980d2c6-56ca-476e-bd01-565ed371273c.png)


#### Operator

```php
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji*$pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>
```

![Gambar 9 Operator](https://user-images.githubusercontent.com/92704969/226240059-a3814eef-cd8d-4536-8d5e-12589d00eca0.png)

#### Kondisi IF

```php
<?php
$nama_hari = date("l");
if ($nama_hari == "Sunday") {
echo "Minggu";
} elseif ($nama_hari == "Monday") {
echo "Senin";
} else {
echo "Selasa";
}
?>
```

#### Kondisi Switch

```php
<?php
$nama_hari = date("l");
switch ($nama_hari) {
case "Sunday":
echo "Minggu";
break;
case "Monday":
echo "Senin";
break;
case "Tuesday":
echo "Selasa";
break;
default:
echo "Sabtu";
?>
```




#### Perulangan for

```php
<?php
echo "Perulangan 1 sampai 10 <br />";
for ($i=1; $i<=10; $i++) {
echo "Perulangan ke: " . $i . '<br />';
}
echo "Perulangan Menurun dari 10 ke 1 <br />";
for ($i=10; $i>=1; $i--) {
echo "Perulangan ke: " . $i . '<br />';
}
?>
```




#### Perulangan while

```php
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
while ($i<=10) {
echo "Perulangan ke: " . $i . '<br />';
$i++;
}
?>
```




#### Perulangan dowhile

```php
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
do {
echo "Perulangan ke: " . $i . '<br />';
$i++;
} while ($i<=10);
?>
```






#### Program Sederhana dengan menggunakan form input yang menampilkan nama, tanggal lahir, dan pekerjaan.

```php
<!DOCTYPE html>
<html>

<head>
  <title>Form Input</title>
  <style>
    table {
      border-collapse: collapse;
      border: 2px solid black;
      margin: auto;
    }

    th,
    td {
      padding: 10px;
      text-align: center;
      border: 1px solid black;
    }
  </style>
</head>

<body>
  <center><h1>Form Input</h1></center>
  <form method="post" action="">
    <table>
      <tr>
        <th>Nama:</th>
        <td><input type="text" name="nama"></td>
      </tr>
      <tr>
        <th>Tanggal Lahir:</th>
        <td><input type="date" name="tanggal_lahir"></td>
      </tr>
      <tr>
        <th>Pekerjaan:</th>
        <td>
          <select name="pekerjaan">
            <option value="programmer">Programmer</option>
            <option value="designer">Designer</option>
            <option value="manager">Manager</option>
          </select>
        </td>
      </tr>
      <tr>
        <td colspan="2"><input type="submit" value="Submit"></td>
      </tr>
    </table>
  </form>
  <br>
  <?php
  if ($_POST) {
    $nama = $_POST['nama'];
    $tanggal_lahir = $_POST['tanggal_lahir'];
    $pekerjaan = $_POST['pekerjaan'];

    // hitung umur
    $tanggal_sekarang = date('Y-m-d');
    $umur = date_diff(date_create($tanggal_lahir), date_create($tanggal_sekarang))->y;

    // hitung gaji
    switch ($pekerjaan) {
      case 'programmer':
        $gaji = 10000000;
        break;
      case 'designer':
        $gaji = 8000000;
        break;
      case 'manager':
        $gaji = 15000000;
        break;
      default:
        $gaji = 0;
        break;
    }

    // tampilkan output
    echo "<center><h2>Output</h2></center>";
    echo "<table>";
    echo "<tr><th>Nama</th><td>$nama</td></tr>";
    echo "<tr><th>Tanggal Lahir</th><td>$tanggal_lahir</td></tr>";
    echo "<tr><th>Umur</th><td>$umur tahun</td></tr>";
    echo "<tr><th>Pekerjaan</th><td>$pekerjaan</td></tr>";
    echo "<tr><th>Gaji</th><td>Rp. " . number_format($gaji, 0, ',', '.') . "</td></tr>";
    echo "</table>";
  }
  ?>
</body>

</html>
```
![Gambar 9 Program Sederhana](https://user-images.githubusercontent.com/92704969/226241767-cfc32d05-9316-44a0-8e98-c863ed9099b7.png) 




### SEKIAN, TUGAS PRAKTIKUM 2 YANG BERISI PENJELASAN TENTANG MEMBUAT PROGRAM PHP SEDERHANA DENGAN INSTRUKSI DAN LANGKAH SERTA HASIL DARI PROGRAM TERSEBUT MENGGUNAKAN BAHASA PEMROGRAMAN PHP MELALUI APLIKASI VSCODE, TERIMAKASIH