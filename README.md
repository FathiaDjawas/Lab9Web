# Lab9Web
<table>
  <tr>
    <th colspan="2">DATA MAHASISWA</th>
  </tr>
  <tr>
    <td>Nama</td>
    <td> Fathia Wardah S.Djawas </td>
  </tr>
  <tr>
    <td>NIM</td>
    <td>312210196</td>
  </tr>
  <tr>
    <td>Kelas</td>
    <td>TI.22.A1</td>
  </tr>
  <tr>
    <td>Matkul</td>  
    <td>Pemograman Web1 </td>
    </tr> 
    </table>



## **Daftar Isi**
**[Instruksi Praktikum](#instruksi-praktikum)**         
**[Langkah-langkah Praktikum](#langkah-langkah-praktikum)**         
**[Result](#result)**

## **Instruksi Praktikum**
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama **lab9_php_modular** pada docroot webserver 
(htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

## **Langkah-langkah Praktikum**
1. **Persiapan**
Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah 
database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan 
melalui XAMPP. 

2. **Buat file baru dengan nama header.php**
    ```html
        <h1>Modularisasi</h1>
        <nav>
            <a href="home.php">Home</a>
            <a href="about.php">Tentang</a>
            <a href="kontak.php">Kontak</a>
            <a href="index.php">Data Barang</a>
        </nav>
    ```

![Screenshot (407)](https://github.com/FathiaDjawas/Lab9Web/assets/115916422/a892f9e7-0336-41ec-801e-46531ab6fe8c)


3. **Buat file baru dengan nama footer.php**
    ```html
        <footer>
            <p>&copy; 2021, Informatika, Universitas Pelita Bangsa</p>
        </footer>
    ```
![Screenshot (410)](https://github.com/FathiaDjawas/Lab9Web/assets/115916422/9d222c03-7aa6-4e29-b315-776da943f89c)


4. **Buat file baru dengan nama home.php**
```
    html 
        <?php require('header.php'); ?>

        <div class="content">
        Modul Praktikum Pemrograman Web
        Agung Nugroho (agung@pelitabangsa.ac.id) 78
        Universitas Pelita Bangsa, Bekasi
            <h2>Ini Halaman Home</h2>
            <p>Ini adalah bagian content dari halaman.</p>
        </div>

        <?php require('footer.php'); ?
```
![Screenshot 2023-12-04 201223](https://github.com/FathiaDjawas/Lab9Web/assets/115775237/77e7ea7c-744b-476f-bade-d451784494da)

5. **Buat file baru dengan nama about.php**

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About</title>
    <style>
</head>

<body>
        <?php require('header.php'); ?>
        <section id="about" class="about">
            <h2>About</h2>
            <div class="row">
                <div class="about-img">
                    <img src="WhatsApp Image 2023-09-06 at 14.54.12_98cddecc.jpg">
                </div>
                <div class="content">
                    <h3>Hello!!</h3>
                    <p>perkenalkan nama saya Fathia Wardah S.Djawas, saya anak tunggal, saat ini usia saya 19 tahun, dan saya memiliki 3 teman yang kiyowok.</p>
                </div>
        </section>
        <?php require('footer.php'); ?>
    </div>
</body>

</html>
```


![Screenshot (409)](https://github.com/FathiaDjawas/Lab9Web/assets/115916422/f7c3b10e-16e6-4b70-b103-fbd0d491a93a)


5. **Buat file baru dengan nama index.php**

```
<?php
include("koneksi.php");
// query untuk menampilkan data
$sql = 'SELECT * FROM data_barang';
$result = mysqli_query($conn, $sql);
?>

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Data Barang</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>
        <?php require('header.php'); ?>
        <h2>Data Barang</h2>
        <div class="main">
            <a class="tambah" href="">Tambah Barang</a>
            <table>
                <tr>
                    <th>Nama Barang</th>
                    <th>Katagori</th>
                    <th>Harga Jual</th>
                    <th>Harga Beli</th>
                    <th>Stok</th>
                    <th>Aksi</th>
                </tr>
                <?php if ($result): ?>
                    <?php while ($row = mysqli_fetch_array($result)): ?>
                        <tr>
                            <td>
                                <?= $row['nama']; ?>
                            </td>
                            <td>
                                <?= $row['kategori']; ?>
                            </td>
                            <td>
                                <?= $row['harga_beli']; ?>
                            </td>
                            <td>
                                <?= $row['harga_jual']; ?>
                            </td>
                            <td>
                                <?= $row['stok']; ?>
                            </td>
                            <td class="aksi">
                                <a class="ubah" href="ubah.php?id=<?= $row['id_barang']; ?>">Ubah</a>
                                <a class="hapus" href="hapus.php?id=<?= $row['id_barang']; ?>">Hapus</a>
                            </td>
                        </tr>
                    <?php endwhile; else: ?>
                    <tr>
                        <td colspan="7">Belum ada data</td>
                    </tr>
                <?php endif; ?>
            </table>
        <?php require('footer.php'); ?>
    </div>


</body>

</html>
```

![5](https://github.com/FathiaDjawas/Lab9Web/assets/115775237/24b65e7d-366e-431c-b625-323677b95635)

# Selesai, Terima kasih
