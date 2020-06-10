# Sistem Backend MeetingYuk

Pengembangan sistem backend MeetingYuk untuk melakukan integrasi aplikasi mitra dengan aplikasi MeetingYuk yang sudah ada.

### Dokumentasi API
Dokumentasi API dapat diakses pada [link berikut][dokumentasi_api]

# Arsitektur Project
Aplikasi ini dibangun menggunakan clean architecture
- Server : Komponen ini berfungsi untuk menangani permintaan langsung dari client. Untuk saat ini adalah http request. 

- Usecase : Komponen usecase berfungsi untuk menangani proses manipulasi data dan proses bisnis dalam aplikasi. 

- Domain : Domain berfungsi sebagai penghubung antara usecase dengan resource data seperti database, thirdparty (http), maupun cache. 

- Resource : Komponen ini berfungsi untuk mengakses resource data secara langsung. Resource data yang digunakan diantaranya adalah database, thirdparty (http), dan cache. 

## Struktur Project
Struktur dari project ini dibagi berbasis per fitur (tidak langsung membagi berdasarkan  arsitektur)
```
src
│
└───common
│   │   thirdparty : melakukan pemanggilan pada service lain
│   │   time : melakukan manipulasi waktu sesuai timezone
│   │   common.ts
|   
└───config
│   │   config.ts : mengatur format data config pada server
│  
└───domain
│   │   account : handle operasi data dan cache entitas account
│   │   bank-account : handle operasi data dan cache entitas akun bank mitra
│   │   chat-room : handle integrasi dengan service chat untuk pembuatan chat-room
│   │   cron-task : hanlde integrasi dengan service cron-app
│   │   data-merchant : handle operasi data dan cache entitas data mitra
│   │   file : melakukan integrasi dengan service space digitalocean untuk manipulasi file
│   │   intent-classifier : hanlde integrasi dengan dialogflow untuk intent parsing
│   │   log-event : handle operasi data dan cache entitas log server
│   │   merchant-account : handle operasi data dan cache entitas akun mitra
│   │   merchant-service : handle operasi data dan cache entitas layanan mitra
│   │   merchant-visitor : handle operasi data dan cache entitas riwayat kunjungan halaman mitra
│   │   notification : integrasi dengan chat-engine untuk notifikasi
│   │   order : handle operasi data dan cache entitas pesanan mitra
│   │   order-item : handle operasi data dan cache entitas item pesanan
│   │   payment : integrasi dengan service payment-engine untuk status pembayaran
│   │   saldo-mitra : integrasi dengan service payment-engine untuk saldo mitra
│   │   withdraw-request : integrasi dengan service payment-engine untuk permintaan penarikan
│  
└───error
│   │   error.ts : wrapper error untuk sistem backend
│  
└───server
|   |   └───http : handle request http
|
└───test : melakukan test pada sistem backend
└───types : berisi struktur data pada sistem backend
└───usecase
│   │   account : manipulasi pada entitas akun
│   │   bank-account : manipulasi pada entitas akun bank
│   │   file : manipulasi dan pengaturan akses file
│   │   log-event : manipulasi pada entitas log
│   │   merchant : manipulasi pada entitas mitra
│   │   merchant-service : manipulasi pada entitas layanan mitra
│   │   notification : manipulasi pada entitas notifikasi
│   │   order : manipulasi pada entitas pesanan
│   │   saldo-mitra : manipulasi pada entitas saldo mitra
│   │   withdraw-request : manipulasi pada entitas penarikan dana
|
└───util
│   │   cache.ts : melakukan operasi cache
│   │   const.ts : variabel konstan pada sistem backend
│   │   tracing : melakukan pengukuran performa fungsi
|
```

[dokumentasi_api]: https://documenter.getpostman.com/view/1901554/SzzdE2Bc
