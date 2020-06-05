# Aplikasi MeetingYuk Merhcant

Aplikasi MeetingYuk Merchant merupakan salah satu aplikasi MeetingYuk yang dibuat untuk mitra dari MeetingYuk. Tujuan dibuatnya aplikasi ini adalah agar integrasi antara aplikasi MeetingYuk yang telah dikembangkan sebelumnya dengan mitra MeetingYuk dapat terjadi, sehingga pengguna dapat memesan tempat secara langsung dalam membuat acara pertemuan.

### Unduh Aplikasi
Aplikasi MeetingYuk Merchant dapat diunduh dengan mengunjungi link [berikut][apkmeetingyuk].

# Arsitektur Project
Aplikasi ini dibangun menggunakan arsitektur MVP (Model View Presenter).
![alt text](https://miro.medium.com/max/1400/1*_BJNVJ369Z16Qo7BTcATRA.png)
- Model : Layer yang bertanggung jawab sebagai definisi aturan bagaimana data dapat diubah dan dimanipulasi.
- View : Layer untuk menampilkan data dan memberikan interaksi ke pengguna
- Presenter : Layer untuk menerima masukan dari pengguna melalui View dan memproses masukan dengan menggunakan bantuan data dari Model dan output akan dikembalikan lagi ke pengguna.

#### Struktur Project
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
└───Fitur 2
│   │   Model
│   │   [Fitur 1]Activity
│   │   [Fitur 1]Contract
│   │   [Fitur 1]Presenter
│  
└───Utils
│  
└───Database
│   └───Converter
|       |   converter 1
│   └───DAO
│       │   [fitur]DAO
│  
```