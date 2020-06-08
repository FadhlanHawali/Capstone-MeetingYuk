# Web Landing Page MeetingYuk

Web landing page MeetingYuk terdiri dari landing page untuk pengguna dan landing page untuk mitra. Web landing page berfungsi sebagai sarana profiling bagi MeetingYuk dan mitra merchant.

### Unduh Aplikasi
Web landing page MeetingYuk dapat dikunjungi melalui link [Web landing page pengguna MeetingYuk](https://meetingyuk.com/user) dan [Web landing page mitra MeetingYuk](https://meetingyuk.com/mitra).

# Arsitektur Project
Web landing page pengguna dan mitra dibangun menggunakan arsitektur MVC (Model View Controller).
![alt text](mvc.png)
- Model : Model mengatur data-data yang ada di web landing page. Untuk melengkapi HTML dan CSS yang berjalan di client side, digunakan Node.JS untuk melengkapi server side-nya.
- View : Untuk menciptakan landing page yang interaktif terhadap user, digunakan DOM(Document Object Model). DOM digunakan untuk membuat image slider, menampilkan error, dan  mengubah navigation menu. jQuery juga digunakan untuk menyederhanakan  HTML dan CSS
- Controller : Controller menghubungkan antara model dan view. Contohnya ketika sebuah button(view) ditekan, maka controller akan menghubungkan dengan model dan melakukan task yang sudah ditentukan, seperti menyimpan di storage atau redirect ke halaman lain.

## Struktur Project
Struktur dari project ini dibagi berbasis per fitur (tidak langsung membagi berdasarkan  arsitektur)
```
app
│   README.md
│
└───Fitur 1
│   │   Model
│   │   [Fitur 1]View
│   │   [Fitur 1]Contract
│   │   [Fitur 1]Controller
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
└───....
```
- [Fitur] Activity : berfungsi sebagai layer View dimana layer menampilkan data dan memberikan interaksi ke pengguna

- [Fitur] Contract : berfungsi sebagai "kontrak" fungsi apa saja yang dapat dilakukan dalam sebuah View dan Presenter. Kontrak ini berfungsi sebagai skeleton nantinya fitur ini dapat melakukan hal apa saja

- [Fitur] Presenter : berfungsi untuk mengolah data dari data yang dimasukkan oleh pengguna melalui View

- Model : berfungsi untuk definisi aturan bagaimana data nantinya dapat diubah dan dimanipulasi. Data ini bisa berupa data dari live data (API) maupun data yang digunakan dalam database.

- Utils : folder yang berfungsi sebagai helper seperti konversi unix timestamp ke java timestamp, menampilkan loading animation, dll.

- Database : berisi sebagai seluruh pengaturan yang berkaitan dengan penggunaan Room Database. Terdapat 2 folder lagi yaitu Converted dan DAO. Converter berfungsi untuk konversi data dengan tipe data kompleks (Array, JSONAray, Custom Class) menjadi ke bentuk tipe data simple (String) dan sebaliknya agar data dapat disimpan dalam Room Database. DAO berfungsi untuk menyimpan function yang berisi Query Query apa saja yang dapat dilakukan.

- API : berisi sebagai deklarasi API saja yang akan digunakan beserta dengan deklarasi request dan response body yang akan digunakan. Terdapat 2 File yaitu APIUtils dan InterfaceAPI. APIUtils berfungsi sebagai file pembantu dalam mendeklarasikan kebutuhan API dalam kasus ini membangun Base URL API MeetingYuk. InterfaceAPI sebagai file kontrak yang berisi API apa saja yang akan digunakan.
 
- SessionManager : berfungsi sebagai mengatur session state management pengguna yang masuk ke dalam aplikasi (seperti 1 time login)

## Daftar API
Berikut merupakan daftar API yang digunakan dari Sistem Backend MeetingYuk untuk membangun aplikasi mitra ini :

| Fitur | Activity | API |
| ------ | ------ | ------------ |
| Pengelolaan Profil | Detail Profil Mitra | https://api.meetingyuk.com/user/merchant/get-detail?id=id_merchant |
| | Mengubah Profil Mitra | https://api.meetingyuk.com/merchant/update-profile |




[apkmeetingyuk]: https://drive.google.com/file/d/1aJFr735BzbhJ48iiIVwsgw0HJfZSwxRA/view?usp=sharing
