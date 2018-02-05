#Hotel
Contoh system untuk manajemen Hotel.

##Indetifikasi stakeholder
2. Staff hotel, terdiri dari:
•	Receptionist
•	room service
•	manajemen
3.Pelanggan
Identifikasi tujuan proyek
Membangun aplikasi Point of Sale (POS) untuk digunakan pada Hotel. Aplikasi POS ini nantinya menjadi alat pencatatan transaksi dan sebagai acuan dalam akuntibilitas operasional Hotel.
Functional requirement
Fitur-fitur yang harus diimplementasikan pada aplikasi POS ini adalah:
1.	Menerima orderan pelanggan dan mencatat transaksi pembayaran.
2.	Mencetak faktur order dan pembayaran
Setiap transaksi harus mencantumkan nama staff yang menerima orderan dan memproses pembayaran.
Flow proses bisnis
1.	Pelanggan datang ke Hotel dan melakukan pemesanan kamar di-receptionist.
2.	Staff menginput pemesanan ke sistem dan kemudian mencetak faktur order dan pembayaran.
3.	Pelanggan membayar sewa kamar dan staff memberikan uang kembalian (jika ada)
4.	Petugas room service mengantar pelanggan ke kamarnya.
Non-Functional Requirements
Aplikasi yang dikembangkan harus dapat digunakan tanpa keyboard secara optimal.
Design solusi
Needs
1.	Aplikasi Point of Sales (POS)
o	identifikasi staff (berarti ada sistem login/logout)
o	input order
o	cetak faktur order/pembayaran
o	Laporan tansaksi
2.	Catatan jumlah uang pada cash register
o	Deposit (menambah uang ke cash register bukan melalui proses pembayaran)
o	Withdrawal (mengambil uang dari cash register)
o	Pergantian staff (cetak tanda serah terima)
o	Laporan jumlah uang beserta transaksi
Features
1.	Aplikasi Point of Sales (POS)
o	User management
Untuk login/logout dan identifikasi staff yang melakukan transaksi.
Fungsi untuk manajemen:
	Menambahkan user baru
	Menghapus/disable user (user tidak dapat login)
	Mengganti password user (reset password)
o	Product management
Untuk daftar kamar yang tersedia
	Mengupdate informasi ketersediaan kamar
	Mengnontaktifkan kamar
o	Order and Payment
Menerima orderan dan menerima pembayaran.
	Menerima pemesanan dari pelanggan
	Menerima pembayaran dari pelanggan
o	Report
Menampilkan daftar transaksi yang terjadi.
2.	Catatan jumlah uang pada Cash Register
o	User management
Untuk login/logout dan identifikasi staff yang melakukan transaksi.
o	Cash out/in
Untuk melakukan deposit pada saat transaksi terjadi.
o	Ganti shift
Proses pergantian staff kasir.
o	Report
Menampilkan jumlah uang dan transaksi. 


