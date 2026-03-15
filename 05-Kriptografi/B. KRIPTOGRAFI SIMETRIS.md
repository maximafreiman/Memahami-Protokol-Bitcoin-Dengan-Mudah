# Kriptografi Simetris, Jenis Kriptografi yang Jadul


Kriptografi simetris adalah teknik pengamanan data di mana pengirim dan penerima menggunakan satu kunci yang sama untuk mengunci (menyandikan) sekaligus membuka (membaca) kembali sebuah informasi. Bayangkan seperti sebuah pintu yang hanya memiliki satu jenis kunci fisik; siapa pun yang ingin masuk atau mengunci pintu tersebut harus memegang kunci yang identik. Karena kuncinya sama, tantangan terbesar dalam sistem ini adalah bagaimana membagikan kunci tersebut kepada orang yang tepat tanpa sempat dicuri atau disalin oleh pihak lain di tengah jalan.

##

### Konsep Kriptografi Simetris: Kunci Rahasia yang Sama untuk Pengirim dan Penerima Pesan

Dalam dunia kriptografi, metode Simetris adalah cara yang paling mendasar. Bayangkan kamu ingin mengirimkan sebuah pesan rahasia di atas selembar kertas kepada seorang teman. Agar pesan tersebut tidak bisa diintip oleh siapa pun saat dalam perjalanan, kamu menggunakan sebuah peti kayu yang dilengkapi dengan gembok.

Prosesnya bekerja seperti ini:

1. Mengunci Pesan: Kamu memasukkan kertas tersebut ke dalam peti kayu, lalu menguncinya menggunakan sebuah kunci fisik yang kamu pegang.

2. Proses Transit: Peti kayu yang sudah terkunci rapat ini kemudian kamu berikan kepada kurir atau diletakkan di sebuah gudang transit (dalam dunia digital, ini adalah server aplikasi). Si kurir atau pemilik gudang memang memegang peti tersebut secara fisik, namun mereka tidak akan pernah tahu apa isi di dalamnya karena tidak memiliki kuncinya.

3. Membuka Pesan: Begitu peti sampai di tangan temanmu, ia akan menggunakan duplikat kunci yang persis sama dengan milikmu untuk membuka gembok tersebut.

![img alt](https://github.com/maximafreiman/Memahami-Protokol-Bitcoin-Dengan-Mudah/blob/6fa93912cee2e3be48b4b594d0f40c3b728683c9/src/pict/kriptografisimetris.jpg)

Kunci dari keamanan sistem ini terletak pada kerahasiaan kunci itu sendiri. Karena kunci untuk "mengunci" dan "membuka" adalah barang yang sama, maka hanya kamu dan temanmu saja yang boleh memilikinya. Jika ada orang lain (termasuk si kurir atau server) yang berhasil mendapatkan salinan kunci tersebut, maka keamanan peti kayu itu tidak lagi ada gunanya.







