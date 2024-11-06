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