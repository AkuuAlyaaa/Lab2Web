# TUGAS PEMROGRAMAN WEB 2 PERTEMUAN 3

Nama : Alya Sefhia Eka Putri

Kelas : TI.22.B1

Nim  : 312101018

Dosen Pengampu :  Sufajar Butsianto, S.Kom. ,M.Kom.

# Pertanyaan dan Tugas

  Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang berbeda-beda sesuai pilihan pekerjaan.

# Laporan Praktikum
  1. Buatlah repository baru dengan nama Lab2Web.
  
  2. Kerjakan semua latihan yang diberikan sesuai urutannya.

  3. Screenshot setiap perubahannya.

  4. Buatlah file README.md dan tuliskan penjelasan dari setiap langkah praktikum beserta screenshotnya.
  
  5. Commit hasilnya pada repository masing-masing.
  
  6. Kirim URL repository pada e-learning ecampus

# Jawab 

1. Membuat folder bernama lab2_php_dasar
   
   ![folder](https://github.com/AkuuAlyaaa/Lab2Web/assets/115520278/a6c7460e-235b-441e-b234-35829d6e5b42)

2. Lalu di dalam folder tersebut buat file bernama php_dasar.php

   ![php file](https://github.com/AkuuAlyaaa/Lab2Web/assets/115520278/9ec26022-2af4-4827-8c4a-05dea96dad91)

3. Ikuti Source Code di bawah ini

   - Mendefinisikan sebuah form HTML dengan input untuk nama, tanggal lahir, dan pilihan pekerjaan.

          <!DOCTYPE html>
          <html>
          <head>
              <title>Form Input</title>
          </head>
          <body>
              <h2>Form Input</h2>
              <form method="post" action="">
                  Nama: <input type="text" name="nama"><br><br>
                  Tanggal Lahir: <input type="date" name="tanggal_lahir"><br><br>
                  Pekerjaan:
                  <select name="pekerjaan">
                      <option value="Programmer">Programmer</option>
                      <option value="Operator Produksi">Operator Produksi</option>
                      <option value="Admin">Admin</option>
                  </select><br><br>
                  <input type="submit" name="submit" value="Submit">
              </form>

     OUTPUT
   
     ![kosong](https://github.com/AkuuAlyaaa/Lab2Web/assets/115520278/8d78323a-0f0b-4e3a-b788-0cd3eae2a33f)

   - Program kemudian menggunakan fungsi hitungUmur() untuk menghitung umur berdasarkan tanggal lahir yang diberikan.
  
          // Fungsi untuk menghitung umur
          function hitungUmur($tanggal_lahir) {
              $tanggal_lahir = new DateTime($tanggal_lahir);
              $today = new DateTime('today');
              $umur = $today->diff($tanggal_lahir)->y;
              return $umur;
          }
      
          if(isset($_POST['submit'])) {
              // Mengambil nilai dari form
              $nama = $_POST['nama'];
              $tanggal_lahir = $_POST['tanggal_lahir'];
              $pekerjaan = $_POST['pekerjaan'];
      
              // Menghitung umur berdasarkan tanggal lahir
              $umur = hitungUmur($tanggal_lahir);
     
     OUTPUT
   
     ![tgl](https://github.com/AkuuAlyaaa/Lab2Web/assets/115520278/a9d2b573-6062-49b2-8a53-7eaf7f8b98c3)

    - Setelah itu, program menggunakan kondisi switch untuk menentukan gaji berdasarkan pekerjaan yang dipilih. Jika pekerjaan adalah Programmer, gaji akan diatur ke 8.000.000, jika pekerjaan adalah Operator Produksi , gaji akan diatur ke 3.000.000, dan jika pekerjaan adalah Admin, gaji akan diatur ke 4.000.000. Jika pekerjaan tidak sesuai, gaji akan diatur ke 0.

          // Menghitung gaji berdasarkan pekerjaan dengan menggunakan kondisi if
              if ($pekerjaan == 'Programmer') {
                  $gaji = 8000000;
              } elseif ($pekerjaan == 'Operator Produksi') {
                  $gaji = 3000000;
              } elseif ($pekerjaan == 'Admin') {
                  $gaji = 4000000;
              } else {
                  $gaji = 0;
              }

      OUTPUT
  
      ![pekerjaan](https://github.com/AkuuAlyaaa/Lab2Web/assets/115520278/2438f94f-f4c3-41b1-849f-417a20b428ed)

    - Jika tombol "Submit" telah ditekan, program akan mengambil nilai dari form menggunakan $_POST. Program menampilkan output yang berisi nama, umur, pekerjaan, dan gaji yang telah dihitung sebelumnya

           // Menampilkan output
                  echo "<h2>Output</h2>";
                  echo "Nama: $nama<br>";
                  echo "Umur: $umur tahun<br>";
                  echo "Pekerjaan: $pekerjaan<br>";
                  echo "Gaji: Rp " . number_format($gaji, 0, ',', '.') . "<br>";
              }
              ?>
          </body>
          </html>

      OUTPUT

      ![submit](https://github.com/AkuuAlyaaa/Lab2Web/assets/115520278/556a889d-1e00-4a42-91f3-9cb22452132d)

  Sekian... Terima Kasih

  @alyasefhia_


