# greenhouse_gallery

## Tugas 7
### Pertanyaan
#### Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.
widget adalah elemen dasar untuk membangun antarmuka aplikasi. Ada dua jenis utama widget, yaitu StatelessWidget dan StatefulWidget. StatelessWidget adalah widget yang tidak memiliki keadaan internal. Ini berarti nilai-nilai yang ditampilkan widget ini tidak berubah setelah pertama kali ditetapkan dan hanya menampilkan data yang telah diberikan.  
Sedangkan StatefulWidget adalah widget yang memiliki keadaan yang dapat berubah selama siklus hidup widget. State dapat diubah karena berbagai faktor, seperti aksi pengguna, perubahan data, atau perubahan status aplikasi.
   
#### Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.  
**MaterialApp**  
Widget utama untuk aplikasi Flutter dengan gaya Material Design. MaterialApp mengatur berbagai pengaturan global untuk aplikasi, seperti tema, routes, dan halaman home.  

**AppBar**  
AppBar adalah widget bilah atas yang menampilkan judul atau aksi lainnya.  

**Icon**  
Icon adalah widget yang menampilkan ikon dari koleksi ikon bawaan Flutter seperti add dan logout.  
  
**Inkwell**  
InkWell adalah widget yang memberikan efek tapping seperti animasi ripple saat widget disentuh.  
  
**Snackbar**  
SnackBar adalah widget untuk menampilkan pesan sementara di bagian bawah layar.  

#### Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.  
setState() adalah metode yang digunakan pada StatefulWidget untuk memperbarui tampilan ketika ada perubahan pada state. Fungsi setState() memberi tahu Flutter bahwa ada perubahan data yang membutuhkan rebuild atau pembaruan pada widget yang terpengaruh, sehingga tampilan dapat segera menyesuaikan dengan data terbaru. Hanya variabel-variabel yang tergolong sebagai bagian dari state widget yang dapat diperbarui dengan setState().  
  
#### Jelaskan perbedaan antara const dengan final.  
Di Dart, const dan final adalah kata kunci yang digunakan untuk mendefinisikan variabel yang nilainya tidak bisa diubah.Perbedaan terjadi saat evaluasi waktu, const dievaluasi pada waktu kompilasi, sementara final dievaluasi pada waktu runtime. final cocok digunakan ketika nilai variabel hanya perlu diatur sekali, tetapi tidak harus diketahui pada waktu kompilasi. Sedangkan const digunakan untuk nilai yang konstan pada waktu kompilasi, artinya nilai variabel diketahui sebelum aplikasi berjalan.  
  
#### Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.  
Pertama, saya membuat program flutter baru dengan flutter create. Kemudian saya menggunakan MaterialApp dan Scaffold untuk mengatur tema dan tampilan utama aplikasi. Untuk menambah tombol saya membuat daftar ItemHomepage sebagai data tiap tombol, kemudian buat widget ItemCard untuk me-render setiap tombol berdasarkan informasi dari daftar items. Kemudian setiap tombol diberi warna yang berbeda melalui properti color pada objek ItemHomepage. Kemudian pada bagian InkWell di ItemCard, tambahkan aksi onTap untuk memunculkan SnackBar ketika tombol ditekan. Pesan yang ditampilkan di SnackBar dapat disesuaikan berdasarkan teks dari item.name.

## Tugas 8  
### Pertanyaan  
#### Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?  
const digunakan untuk mendeklarasikan nilai atau widget yang konstan atau tetap. Karena nilainya yang tidak berubah maka const dapat menghemat waktu kompilasi karena widget yang tidak berubah tidak perlu di rebuild ulang dan tidak perlu diperiksa ulang. const sebaiknya digunakan pada widget statis atau yang tidak akan berubah setelah dibuat, seperti teks label, ikon, atau kontainer yang memiliki nilai tetap, sedangkan untuk data yang dinamis atau widget yang nilainya berubah-ubah sebaiknya jangan menggunakan const  
  
#### Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!  
Dalam Flutter, Column dan Row adalah widget dasar yang sering digunakan untuk menata layout secara vertikal atau horizontal. Contoh implementasi row terdapat pada file menu.dart untuk menampilkan nama, npm, dan kelas secara horizontal :  
          children: [
            Row(
              mainAxisAlignment: MainAxisAlignment.spaceEvenly,
              children: [
                InfoCard(title: 'NPM', content: npm),
                InfoCard(title: 'Name', content: name),
                InfoCard(title: 'Class', content: className),
              ],
            ),

Contoh implementasi column berikut untuk menata icon-icon secara vertikal:  
        body: Center(
        child: Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: <Widget>[
            Icon(Icons.home, size: 40, color: Colors.blue),
            Icon(Icons.favorite, size: 40, color: Colors.red),
            Icon(Icons.person, size: 40, color: Colors.green),
          ],
        ),
      ),

#### Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!  
Pada halaman form terdapat beberapa elemen input seperti TextFormField untuk Name, Description dan Amount dan ElevatedButton sebagai tombol Save. Terdapat juga beberapa elemen input lain seperti CheckboxListTile, RadioListTile, Slider, dan lainya yang tidak digunakan pada tugas kali ini.

#### Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?  
Tema dapat diatur dengan memanfaatkan properti theme pada MaterialApp, kita dapat menyesuaikan tema seperti palet warna, ukuran teks, dan lainya untuk aplikasi yang kita buat. Pada tugas kali ini saya mengimplementasikan palet warna untuk menyesuaikan dengan tema aplikasi saya.

#### Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?  
Untuk navigasi sederhana saya menggunakan Navigator untuk push halaman baru ke atas stack dan pop jika ingin kembali, namun untuk aplikasi dengan banyak halaman menggunakan named routes dapat membantu karena kita bisa mendefinisikan semua rute di satu tempat, membuat navigasi lebih terstruktur dan mudah dikelola. 

## Tugas 8  
### Pertanyaan 
#### Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?  
Membuat model untuk pengambilan atau pengiriman data JSON memberikan banyak keuntungan seperti validasi, kemudahan manipulasi, dan integrasi. Tidak menggunakan model tidak langsung menyebabkan error, tetapi dapat meningkatkan risiko bug dan kesulitan dalam mengelola data yang lebih kompleks.

#### Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini  
Library http dalam Flutter berfungsi sebagai alat komunikasi antara aplikasi Flutter dan server Django melalui protokol HTTP. Dalam implementasi ini, library http memungkinkan Flutter mengirim berbagai jenis permintaan HTTP, seperti GET untuk mengambil data dari server Django (misalnya daftar produk atau informasi pengguna), POST untuk mengirim data baru (seperti menambahkan produk), PUT atau PATCH untuk memperbarui data, dan DELETE untuk menghapus data. Respons dari Django yang biasanya dalam format JSON dapat diolah menggunakan library ini, sehingga data dapat diubah menjadi objek Dart seperti Map atau List untuk digunakan di aplikasi Flutter. Dengan tambahan fitur untuk menangani error dan waktu tunggu (timeout), library http memastikan aplikasi tetap responsif meskipun server mengalami gangguan.

#### Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.  
CookieRequest adalah alat untuk menangani cookie secara otomatis, memungkinkan autentikasi berbasis sesi, dan memastikan komunikasi yang lancar antara Flutter dan server. Membagikan instance CookieRequest ke semua komponen dalam aplikasi Flutter penting untuk menjaga konsistensi state dan kemudahan implementasi, terutama dalam aplikasi yang mengandalkan cookie untuk autentikasi atau sesi.  
  
#### Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.  
Input: Pengguna memasukkan data di aplikasi Flutter melalui UI -> Pengiriman Data: Flutter mengirimkan data ke server -> Django menggunakan HTTP (biasanya POST) -> Pemrosesan di Back-End: Django memproses data, memvalidasi, dan menyimpannya di database -> Pengambilan Data: Flutter meminta data dari server Django menggunakan HTTP (GET) -> Tampilkan Data: Flutter menampilkan data yang diterima dari server di UI.
  
#### Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.  
Register: Pengguna memasukkan data akun di Flutter → Data dikirim ke Django → Django membuat akun → Flutter menampilkan pesan sukses.
Login: Pengguna memasukkan kredensial di Flutter → Data dikirim ke Django → Django memverifikasi dan mengembalikan token → Flutter menyimpan token dan menavigasi ke menu utama.
Tampilkan Menu: Flutter menggunakan token untuk meminta data menu → Django memverifikasi token dan mengembalikan data → Flutter menampilkan data di UI.
Logout: Flutter mengirim permintaan logout → Django menghapus token/sesi → Pengguna kembali ke halaman login.  

#### Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).  
Pertama saya membuat aplikasi baru bernama authentication pada projek django yang berfungsi untuk menangani autentikasi user serta menangani fungsi login, register, dan logout pada aplikasi. Kemudian saya mebuat berkas login dan register sebagai halaman dan fungsi login dan register. Kemudian dengan bantuan library http saya menghubungkan aplikasi authentication sebagai autentikasi untuk project flutter ini. Kemudian saya membuat model kustom dengan bantuan website quicktype dan membuat berkas berkas list_product.dart untuk menampilkan daftar product yang terasosiasi dengan user.
  
          