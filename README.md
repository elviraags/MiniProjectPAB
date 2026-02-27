# SmileCare Dental

**Deskripsi Aplikasi**

SmileCare Dental adalah aplikasi reservasi klinik gigi yang memungkinkan pengguna untuk melakukan pemesanan jadwal perawatan gigi guna mempermudah dan mempercepat proses bagi pengguna. Aplikasi ini dirancang dengan tampilan yang menarik untuk meningkatkan pengalaman pengguna dalam melakukan reservasi layanan dental.


**Tampilan Aplikasi**

<img width="1568" height="837" alt="image" src="https://github.com/user-attachments/assets/9b4eb4e4-2280-4981-a638-3ea01338b8a1" />

<img width="1566" height="841" alt="image" src="https://github.com/user-attachments/assets/1df12189-ddd0-4b69-9828-db6d59ab4426" />

<img width="1565" height="842" alt="image" src="https://github.com/user-attachments/assets/90953f54-67ba-43a5-813d-cb6a88ab4d49" />



**Fitur Aplikasi**

1. Menampilkan halaman utama (home page) dengan background gambar gambar klinik yang di buat dengan bantuan AI
2. Menampilkan daftar reservasi
3. Menambahkan reservasi baru
4. Form input data reservasi (nama, no telepon, jenis perawatan, dan tanggal reservasi).
5. Menampilkan pesan "Belum ada reservasi" jika data kosong
6. Dapat memperbarui data dan menghapus data (reservasi).


**Widget yang Digunakan**

**A. MaterialApp**

digunakan di main.drat, widget utama yang mengatur halaman awal, mengatur tema, routing dll.

MaterialApp(
  debugShowCheckedModeBanner: false,
  home: HomePage(),
)


**B. Scaffold**

Digunakan di HomePage dan FormPage, Kerangka dasar tampilan halaman, menyediakan AppBar, body, FloatingActionButton, Snackbar,dll.

Scaffold(
  appBar: AppBar(...),
  body: ...,
  floatingActionButton: ...
)


**C. AppBar**

Menampilkan bar di bagian atas aplikasi, berisi judul halaman, bisa berisi tombol back, action, dll.

AppBar(
  title: Text("SmileCare Dental"),
)


**D. Stack**

Menumpuk widget secara bertumpuk (layer), di aplikasi ini digunakan untuk, background gambar, overlay gelap, konten di atasnya.

Stack(
  children: [
    Image.asset(...),
    Container(...),
    Padding(...)
  ],
)


**E. Image.asset**

Menampilkan gambar dari folder assets, boxFit.cover  gambar memenuhi layar.

Image.asset(
  "assets/dentalcare.jpg",
  fit: BoxFit.cover,
)

**F. Container**

Memberi warna overlay gelap di atas background, bisa mengatur padding, margin, decoration, dll.

Container(
  color: Colors.black.withOpacity(0.5),
)


**G. SizedBox**

Memberi jarak antar widget (spacer), bisa mengatur lebar atau tinggi kosong.

SizedBox(height: 15)


**H. Padding**

Memberi jarak antara widget dan tepi

Padding(
  padding: EdgeInsets.all(20),
  child: ...
)


**I. ListView.builder**

Menampilkan daftar data secara dinamis, digunakan untuk menampilkan list reservasi.

ListView.builder(
  itemCount: dataReservasi.length,
  itemBuilder: ...
)


**J. Card**

Membuat tampilan seperti kartu, memberi efek bayangan (elevation), digunakan untuk setiap data reservasi.

Card(
  shape: RoundedRectangleBorder(
    borderRadius: BorderRadius.circular(20),
  ),
)


**K. ListTile**

Layout standar untuk list berisi: 

Title : nama pasien

subtitle : perawatan & tanggal

trailing : tombol edit & delete

ListTile(
  title: Text(...),
  subtitle: Text(...),
  trailing: Row(...)
)


**L. IconButton**

Tombol berbentuk icon, digunakan untuk edit data hapus data.

IconButton(
  icon: Icon(Icons.edit),
  onPressed: ...
)


**M. FloatingActionButton**

Tombol bulat mengambang, digunakan untuk menambah reservasi baru.

FloatingActionButton(
  onPressed: ...
)


**N. Navigator**

Berpindah halaman: digunakan saat tambah reservasi, edit reservasi.

Navigator.push(
  context,
  MaterialPageRoute(builder: (_) => FormPage())
);

**O. Form**

Mengelompokkan field input, digunakan untuk validasi form.

Form(
  key: _formKey,
  child: ...
)


**P. TextFormField**

Input teks bisa divalidasi, digunakan untuk nama pasien, no telepon.

TextFormField(
  controller: namaController,
  validator: ...
)



**Q. DropdownButtonFormField**

Dropdown pilihan, digunakan untuk memilih jenis perawatan.

DropdownButtonFormField<String>(
  items: daftarPerawatan.map(...).toList(),
)


**R. ElevatedButton**

Tombol aksi utama, digunakan untuk pilih tanggal, dan impan reservasi.

ElevatedButton(
  onPressed: ...
)


**S. showDatePicker**

Menampilkan popup kalender, digunakan untuk memilih tanggal reservasi.

showDatePicker(...)


**T. StatefulWidget vs StatelessWidget**

1. StatelessWidget (Tidak memiliki state data tidak berubah)

   class MyApp extends StatelessWidget

2. StatefulWidget (Memiliki state yang bisa berubah)

   class HomePage extends StatefulWidget
   
   class FormPage extends StatefulWidget

   Data reservasi bisa bertambah. Form bisa berubah isinya
   

**Kesimpulan**

Widget Layout : Stack, Padding, SizedBox

Widget Input : TextFormField, DropdownButtonFormField

Widget Navigasi : Navigator

Widget List : ListView, Card, ListTile

Widget Action : FloatingActionButton, ElevatedButton

Widget State : StatefulWidget
   

