# Aplikasi MeetingYuk Merhcant

Aplikasi MeetingYuk Merchant merupakan salah satu aplikasi MeetingYuk yang dibuat untuk mitra dari MeetingYuk. Tujuan dibuatnya aplikasi ini adalah agar integrasi antara aplikasi MeetingYuk yang telah dikembangkan sebelumnya dengan mitra MeetingYuk dapat terjadi, sehingga pengguna dapat memesan tempat secara langsung dalam membuat acara pertemuan.

### Unduh Aplikasi
Aplikasi MeetingYuk Merchant dapat diunduh dengan mengunjungi link [berikut][apkmeetingyuk].

# Arsitektur Project
Aplikasi ini dibangun menggunakan arsitektur MVP (Model View Presenter).
![alt text](mvp.png)
- Model : Layer yang bertanggung jawab sebagai definisi aturan bagaimana data dapat diubah dan dimanipulasi.
- View : Layer untuk menampilkan data dan memberikan interaksi ke pengguna
- Presenter : Layer untuk menerima masukan dari pengguna melalui View dan memproses masukan dengan menggunakan bantuan data dari Model dan output akan dikembalikan lagi ke pengguna.

## Struktur Project
Struktur dari project ini dibagi berbasis per fitur (tidak langsung membagi berdasarkan  arsitektur)
```
app
│   README.md
│
└───Fitur 1
│   │   Model
│   │   [Fitur 1]Activity
│   │   [Fitur 1]Contract
│   │   [Fitur 1]Presenter
│   |   [Fitur 1]Adapter
|   
└───Fitur 2
│   │   Model
│   │   [Fitur 2]Activity
│   │   [Fitur 2]Contract
│   │   [Fitur 2]Presenter
│  
└───Utils
│  
└───Database
│   └───Converter
|       |   converter 1
│   └───DAO
│       │   [fitur]DAO
│  
└───API
|   |   APIUtils
|   |   InterfaceAPI
|
└───SessionManager
└───....
```
- [Fitur] Activity : berfungsi sebagai layer View dimana layer menampilkan data dan memberikan interaksi ke pengguna

- [Fitur] Contract : berfungsi sebagai "kontrak" fungsi apa saja yang dapat dilakukan dalam sebuah View dan Presenter. Kontrak ini berfungsi sebagai skeleton nantinya fitur ini dapat melakukan hal apa saja

- [Fitur] Presenter : berfungsi untuk mengolah data dari data yang dimasukkan oleh pengguna melalui View

- Model : berfungsi untuk definisi aturan bagaimana data nantinya dapat diubah dan dimanipulasi. Data ini bisa berupa data dari live data (API) maupun data yang digunakan dalam database.

- Utils : folder yang berfungsi sebagai helper seperti konversi unix timestamp ke java timestamp, menampilkan loading animation, dll.

- Database : berisi sebagai seluruh pengaturan yang berkaitan dengan penggunaan Room Database. Terdapat 2 folder lagi yaitu Converted dan DAO. Converter berfungsi untuk konversi data dengan tipe data kompleks (Array, JSONAray, Custom Class) menjadi ke bentuk tipe data simple (String) dan sebaliknya agar data dapat disimpan dalam Room Database. DAO berfungsi untuk menyimpan function yang berisi Query Query apa saja yang dapat dilakukan.

- API : berisi sebagai deklarasi API saja yang akan digunakan beserta dengan deklarasi request dan response body yang akan digunakan. Terdapat 2 File yaitu APIUtils dan InterfaceAPI. APIUtils berfungsi sebagai file pembantu dalam mendeklarasikan kebutuhan API dalam kasus ini membangun Base URL API MeetingYuk. InterfaceAPI sebagai file kontrak yang berisi API apa saja yang akan digunakan.

## Daftar API
Berikut merupakan daftar API yang digunakan dari Sistem Backend MeetingYuk untuk membangun aplikasi mitra ini :

| Fitur | Activity | API |
| ------ | ------ | ------------ |
| Autentikasi Mitra | Login | https://api.meetingyuk.com/merchant/v2/login |
|  | SignUp | https://api.meetingyuk.com/merchant/signup |
| Pengelolaan Pesanan | Daftar Pesanan | https://api.meetingyuk.com/merchant/order/get-with-filter|
|  | Detail Pesanan | https://api.meetingyuk.com/merchant/order/get-with-filter |
| | Mengunduh Invoice | https://api.meetingyuk.com/merchant/order/invoice/:id_order/token:token/invoice.pdf |
| | Menambah Pesanan | https://api.meetingyuk.com/merchant/order/add-order |
| Pengelolaan Daftar Layanan | Daftar Layanan | https://api.meetingyuk.com/merchant/service |
| | Edit Layanan | https://api.meetingyuk.com/merchant/service/update/:id_
service |
| | Menambah Layanan | https://api.meetingyuk.com/merchant/service/add |
| | Menghapus Layanan | https://api.meetingyuk.com/merchant/service/delete/:id_
service |
| Pesan | Daftar Pesan | https://message.meetingyuk.com/message/room/list-
room |
| | Detail Pesan | https://message.meetingyuk.com/message/last |
| Laporan Statistik Pesanan dan Saldo Merchant | Laporan (Mingguan / 1 Bulan / 4 Bulan / 1 Tahun) | https://api.meetingyuk.com/merchant/order/report/:(week,month,quarter,year) |
| | Menambah Akun Bank | https://api.meetingyuk.com/merchant/bank-account/add |
| | Daftar Akun Bank | https://api.meetingyuk.com/merchant/bank-account |
| | Riwayat Penarikan Saldo | https://api.meetingyuk.com/merchant/saldo-mitra/withdraw|
| Pengelolaan Profil | Detail Profil Mitra | https://api.meetingyuk.com/user/merchant/get-
detail?id=id_merchant |
| | Mengubah Profil Mitra | https://api.meetingyuk.com/merchant/update-profile |
| | Menambah Admin | https://api.meetingyuk.com/merchant/account/add-admin |
| | Menghapus Admin | https://api.meetingyuk.com/merchant/admin/delete/:email |
| | Menampilkan List Admin | https://api.meetingyuk.com/merchant/account/admin |




[apkmeetingyuk]: https://drive.google.com/file/d/1aJFr735BzbhJ48iiIVwsgw0HJfZSwxRA/view?usp=sharing