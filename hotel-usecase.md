![alt text](https://github.com/koswarabilly/pengembangan_aplikasi/blob/master/images/Untitled%20Diagram.jpg "USE-CASE")

Simbol lingkaran elips menunjukkan *use case* untuk proses tertentu dan simbol orang pada diagram tersebut menunjukkan *staff* yang terlibat dalam *use case* tersebut.
Simbol panah menunjukkan generalisasi, pada diagram contoh di atas *staff* resepsionis dan *staff* manajemen merupakan sub dari *staff*.
Masing-masing *use case* perlu dibuatkan narasi.

# 1.	Login
## Description
Pengguna masuk ke sistem untuk tujuan meng-*establish* identitas pengguna di dalam sistem (untuk keperluan pencatatan dan akuntibilitas).
Seluruh fungsi sistem hanya dapat digunakan apabila pengguna sudah login ke dalam sistem.

### Normal Flow
1.	Pengguna menyalakan aplikasi. 
2.	Aplikasi menampilkan halaman *login*.
3.	Pengguna memasukkan *username* dan *password* untuk masuk ke sistem.
4.	Sistem memeriksa *username* dan *password*, apabila valid dan masih aktif, pengguna akan di-*login*-kan ke sistem.
5.	Pengguna sudah dapat menggunakan aplikasi.

### Alternative Flow
##### Pengguna salah memasukkan *username/password*.
1.	Pengguna memasukkan *user/password* yang salah.
2.	Sistem menampilkan pesan kesalahan dan menunggu pengguna untuk memasukkan *username* dan *password* lagi.
3.	Ulangi proses *normal flow* dari langkah ke-2.


# 2.	Logout
## Description
Pengguna keluar dari sistem. Setiap pengguna berkewajiban untuk __*logout*__ dari sistem apabila sudah selesai menggunakan sistem.

### Precondition
User dalam keadaan __*logged in*__ di sistem.

### Normal Flow
1.	*Staff* menekan tombol *logout* pada aplikasi.
2.	Sistem meng-*logout* pengguna.


# 3.	Add User ( *user management* )
## Description
Menambahkan pengguna baru ke sistem jika ada *staff receptionist* yang __baru__.

### Precondition
User dalam keadaan __*logged in*__ di sistem.

### Normal Flow
1.	Pengguna membuka *menu user management* dan menekan tombol __*add*__ untuk menambahkan *user* baru.
2.	Sistem menampilkan *form* pendaftaran *user* baru
3.	Pengguna menginput data *user* baru:
    -	nama lengkap
    -	nama user
    -	*password & password verification*
    -	jenis *user* ( __kasir/manajemen__ )
dan menekan tombol save untuk menyimpan data *user*
    -	Sistem memeriksa validitas data *user* baru, menyimpan informasi *user* ke *database* dan menampilkan pesan notifikasi ke pengguna bahwa *user* baru sudah tersimpan


# 4.	Remove User (staff management)
## Description
Meng-nonaktifkan pengguna. Pengguna yang sudah di-nonaktifkan tidak dapat login ke dalam sistem.

### Precondition
User sudah *login* sebagai pengguna manajemen.

### Normal Flow
1.	Pengguna membuka menu *user management* dan memilih *account user* yang akan dinonaktifkan.
2.	Sistem menampilkan form tampilan informasi *account user*.
3.	Pengguna menekan tombol non-aktif untuk meng-nonaktifkan *user*.
4.	Sistem mengupdate status keaktifan *user* ke *database*.
>Untuk mengaktifkan kembali user, lakukan flow yang sama.


# 5.	Update user account ( *user management* )
## Description
Mengubah informasi mengenai pengguna, misalnya nama lengkap atau *password*.

## Precondition
User sudah __*login*__ sebagai pengguna manajemen.

### Normal Flow
1.	Pengguna membuka menu *user management* dan memilih *account user* yang akan di-*update*.
2.	Sistem menampilkan *form* tampilan informasi *account user*.
3.	User meng-*update* informasi *user* dan menekan tombol __*save*__.
4.	Sistem menyimpan perubahan *account user* ke *database*.


# 6.	Update Product (*product management*)
## Description
Mengubah informasi mengenai kamar, misalnya harga atau foto kamar.

## Precondition
Pengguna sudah *login* sebagai *user* manajemen.

### Normal Flow
1.	Pengguna membuka menu *room management* dan memilih kamar yang akan di-*update*.
2.	Sistem menampilkan form tampilan informasi kamar.
3.	Pengguna meng-*update* informasi kamar dan menekan tombol __*save*__.
4.	Sistem menyimpan perubahan informasi kamar ke *database*.


# 7.	Order
## Description
Pelanggan melakukan pemesanan kamar.

## Precondition
Pengguna sudah masuk ke dalam sistem sebagai *user* resepsionis.

### Normal Flow
1.	Pelanggan melakukan pemesanan kepada resepsionis sesuai dengan kamar yang tersedia.
2.	Pengguna menginput pesanan pelanggan ke dalam sistem:
    -	kamar yang diorder
    -	Jumlah (__qty__) kamar
3.	Sistem memeriksa validitas pesanan dan kemudian menyimpan informasi pesanan ke *database*.
4.	Sistem menampilkan total tagihan.

### Alternative Flow
Pelanggan memesan kamar yang tidak aktif.
1.	Pada proses validasi pesanan, sistem menampilkan notifikasi ke pengguna bahwa kamar yang dipesan tidak tersedia.
2.	Pengguna mengubah pesanan atau membatalkan pesanan sesuai dengan keputusan dari pelanggan.
3.	Sistem memvalidasi pesanan. Jika sudah valid simpan data pesanan ke *database*. Jika belum ulangi proses ini.
4.	Sistem menampilkan total tagihan (jika pesanan tidak dibatalkan).


# 8.	Payment
## Description
Pelanggan membayar pesanan.

## Precodition
Pengguna sudah masuk ke dalam sistem sebagai pengguna resepsionis. Pesanan pelanggan sudah disimpan oleh sistem (pesanan valid).

### Normal Flow
1.	Staff receptionist meminta pembayaran kepada pelanggan sesuai dengan total tagihan. Kemudian staff resepsionis menginput informasi pembayaran.
2.	Sistem merekam informasi pembayaran dan kemudian mencetak faktur pesanan dan pembayaran.
3.	Staff kasir menginformasikan ke petugas *room service* untuk mengantar pelanggan ke kamarnya.


# 9.	Report POS
## Description
Menampilkan *summary* transaksi.

## Precondition
Pengguna sudah login sebagai *user* manajemen.

### Normal Flow
1.	Pengguna mengakses menu laporan dan memilih laporan.
2.	Sistem menampilkan *form* untuk menerima input kriteria laporan.
3.	Pengguna menginput kriteria laporan dan mengklik tombol __*report*__.
4.	Sistem mengolah data __*report*__ dan kemudian menampilkan laporan kepada pengguna.


# 10.	Cash In/Out
## Description
Proses memasukkan uang melalui proses transaksi.

## Precondition
Pengguna sudah login sebagai *user* resepsionis.

### Normal Flow
1.	Pengguna mengakses menu transaksi.
2.	Sistem menampilkan form input data *cash in*.
3.	User menginput data *cash in*:
    -	Jumlah
    -	Keterangan
dan kemudian menekan tombol save.
4.	Sistem menyimpan data *cash in* ke database dan mencetak faktur *cash in*.


# 12.	Ganti Shift
## Description
Proses pergantian shift *staff*. 

## Precondition
Pengguna sudah login sebagai *user* resepsionis.

### Normal Flow
1.	Sistem menampilkan waktu untuk melakukan pergantian *shift*.
2.	Resepsionis pengganti memasukkan informasi *login*.
3.	Sistem memeriksa *login* resepsionis pengganti.
4.	Pengguna resepsionis pertama akan di-*logout*.

