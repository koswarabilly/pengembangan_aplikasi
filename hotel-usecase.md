![alt text](https://github.com/koswarabilly/pengembangan_aplikasi/blob/master/images/Untitled%20Diagram.jpg "USE-CASE")

Simbol lingkaran elips menunjukkan use case untuk proses tertentu dan simbol orang pada diagram tersebut menunjukkan staff yang terlibat dalam use case tersebut.
Simbol panah menunjukkan generalisasi, pada diagram contoh di atas staff kasir dan staff manajemenmerupakan sub dari staff.
Masing-masing use case perlu dibuatkan narasi.
# 1.	Login
## Description
User masuk ke sistem untuk tujuan meng-establish identitas user di dalam sistem (untuk keperluan pencatatan dan akuntibilitas).
Seluruh fungsi sistem hanya dapat digunakan apabila user sudah login ke dalam sistem.
### Normal Flow
i.	User menyalakan aplikasi 
ii.	Aplikasi menampilkan halaman login
iii.	User memasukkan user dan password untuk login ke sistem
iv.	Sistem memeriksa user dan password, apabila valid dan masih aktif, user akan di-login-kan ke sistem
v.	User sudah dapat menggunakan aplikasi
### Alternative Flow
User salah memasukkan user/password
vi.	User memasukkan user/password yang salah
vii.	Sistem menampilkan pesan kesalahan dan menunggu user untuk memasukkan user dan password lagi
viii.	Ulangi proses normal flow langkah ke ii.
# 2.	Logout
## Description
User keluar dari sistem. Setiap user berkewajiban untuk logout dari sistem apabila sudah selesai menggunakan sistem.
Precondition
User dalam keadaan login di sistem.
### Normal Flow
i.	Staff menekan tombol logout pada aplikasi
ii.	Sistem meng-logout user
# 3.	Add User (user management)
## Description
Menambahkan user baru ke dalam system jika ada staff receptionist yang baru.
## Precondition
User sudah login sebagai user manajemen.
### Normal Flow
i.	User membuka menu user management dan menekan tombol add untuk menambahkan user baru.
ii.	Sistem menampilkan form pendaftaran user baru
iii.	User menginput data user baru:
	nama lengkap
	nama user
	password & password verification
	jenis user (kasir/manajemen)
dan menekan tombol save untuk menyimpan data user
iv.	Sistem memeriksa validitas data user baru, menyimpan informasi user ke databse dan menampilkan pesan notifikasi ke user bahwa user sudah tersimpan.
# 4.	Remove User (staff management)
## Description
Meng-nonaktifkan user. User yang sudah di-nonaktifkan tidak dapat login ke dalam sistem.
## Precondition
User sudah login sebagai user manajemen.
### Normal Flow
i.	User membuka menu user management dan memilih account user yang akan dinonaktifkan.
ii.	Sistem menampilkan form tampilan informasi account user.
iii.	User menekan tombol non-aktif untuk meng-nonaktifkan user.
iv.	Sistem mengupdate status keaktifan user ke database.
Untuk mengaktifkan kembali user, lakukan flow yang sama.
# 5.	Update user account (user management)
## Description
Mengubah informasi mengenai user, misalnya nama lengkap atau password.
## Precondition
User sudah login sebagai user manajemen.
### Normal Flow
i.	User membuka menu user management dan memilih account user yang akan di-update.
ii.	Sistem menampilkan form tampilan informasi account user.
iii.	User mengupdate informasi user dan menekan tombol save.
iv.	Sistem menyimpan perubahan account user ke database.
# 6.	Update Product (product management)
## Description
Mengubah informasi mengenai kamar, misalnya harga atau foto kamar.
## Precondition
User sudah login sebagai user manajemen.
### Normal Flow
i.	User membuka menu product management dan memilih product yang akan di-update.
ii.	Sistem menampilkan form tampilan informasi product.
iii.	User mengupdate informasi product dan menekan tombol save.
iv.	Sistem menyimpan perubahan account product ke database.
# 7.	Order
## Description
Pelanggan melakukan order kamar.
## Precondition
User sudah masuk ke dalam sistem sebagai user kasir.
### Normal Flow
i.	Pelanggan melakukan order kepada receptionist sesuai dengan kamar yang tersedia.
ii.	Staff menginput orderan pelanggan ke dalam sistem:
	kamar yang diorder
	Jumlah (qty) product
iii.	Sistem memeriksa validitas order dan kemudian menyimpan informasi order ke database.
iv.	Sistem menampilkan total tagihan.
### Alternative Flow
Pelanggan memesan product yang tidak aktif.
v.	Pada proses validasi order, sistem menampilkan notifikasi ke user bahwa product yang di-order tidak tersedia.
vi.	User mengubah order atau membatalkan order sesuai dengan keputusan dari pelanggan.
vii.	Sistem memvalidasi order. Jika sudah valid simpan data order ke database. Jika belum ulangi proses ini.
viii.	Sistem menampilkan total tagihan (jika order tidak dibatalkan).
# 8.	Payment
## Description
Pelanggan membayar pesanan.
## Precodition
User sudah masuk ke dalam sistem sebagai user kasir. Orderan pelanggan sudah disimpan oleh sistem (order valid).
### Normal Flow
i.	Staff receptionist meminta pembayaran kepada pelanggan sesuai dengan total tagihan. Kemudian staff kasir menginput informasi pembayaran.
ii.	Sistem merekam informasi pembayaran dan kemudian mencetak faktur order dan pembayaran.
iii.	Staff kasir menginformasikan ke petugas room service untuk mengantar pelanggan ke kamarnya.
# 9.	Report POS
## Description
Menampilkan summary transaksi
## Precondition
User sudah login sebagai user manajemen.
### Normal Flow
i.	User mengakses menu laporan dan memilih laporan POS.
ii.	Sistem menampilkan form untuk menerima input kriteria laporan.
iii.	User menginput kriteria laporan dan mengklik tombol report.
iv.	Sistem mengolah data report dan kemudian menampilkan laporan kepada user.
# 10.	Report Cash Register
## Description
Menampilkan summary transaksi cash register berdasarkan kriteria tertentu.
## Precondition
User sudah login sebagai user manajemen.
### Normal Flow
i.	User mengakses menu laporan dan memilih laporan Cash Register.
ii.	Sistem menampilkan form untuk menerima input kriteria laporan.
iii.	User menginput kriteria laporan dan mengklik tombol report.
iv.	Sistem mengolah data report dan kemudian menampilkan laporan kepada user.
# 11.	Cash In/Out
## Description
Proses memasukkan uang melalui proses transaksi.
## Precondition
User sudah login sebagai user receptionist.
### Normal Flow
i.	User mengakses menu transaksi.
ii.	Sistem menampilkan form input data cash in.
iii.	User menginput data cash in:
	Jumlah
	Keterangan
dan kemudian menekan tombol save.
iv.	Sistem menyimpan data cash in ke database dan mencetak faktur cash in.
# 12.	Ganti Shift
## Description
Proses pergantian shift user. 
## Precondition
User sudah login sebagai user resepsionis.
### Normal Flow
i.	Sistem menampilkan waktu untuk melakukan pergantian shift.
ii.	Kasir pengganti memasukkan informasi login.
iii.	Sistem memeriksa login kasir pengganti.
iv.	User kasir pertama akan dilogout.

