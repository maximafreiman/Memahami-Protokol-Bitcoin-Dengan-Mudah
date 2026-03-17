# Kriptografi Asimetris. Hanya 1 Arah, Susah Dimanipulasi.

Kriptografi Asimetris (juga dikenal sebagai Public Key Cryptography) adalah metode pengamanan data yang menggunakan sepasang kunci yang berbeda namun saling terhubung secara matematis. Berbeda dengan sistem simetris yang hanya menggunakan satu kunci untuk segala hal, sistem asimetris membagi tugas: satu kunci untuk mengunci informasi, dan satu kunci lainnya untuk membuka informasi tersebut.

Untuk memahami cara kerjanya tanpa pusing dengan matematika, bayangkan sebuah Kotak Surat yang tertanam di tembok depan rumahmu.

Kunci Publik (Lubang Slot): Si pengirim mengirim pesan ke sebuah kotak surat milik penerima. Kotak surat ini memiliki lubang slot yang dirancang khusus: siapa pun bisa memasukkan dokumen ke dalamnya, tapi begitu dokumen jatuh ke dasar kotak, ia langsung terkunci secara otomatis. Kotak surat dan mekanisme penguncian otomatis inilah yang disebut Public Key.

Kunci Privat (Kunci Pintu Belakang): Ini adalah kunci fisik yang hanya kamu pegang dan simpan rapat di sakumu. Kunci ini digunakan untuk membuka pintu di bagian belakang kotak surat agar kamu bisa mengambil dan membaca pesan yang masuk.


![img alt](https://github.com/maximafreiman/Memahami-Protokol-Bitcoin-Dengan-Mudah/blob/4ef8330c64da9164dc0f0b3767f8b3f41cf5cbc7/src/pict/2.%20kriptografiasimetrissss.png)

Kelebihan utama dari sistem ini adalah keamanan pertukaran kunci. Kamu tidak perlu khawatir kunci rahasiamu dicuri saat dikirim ke orang lain, selama kunci rahasia tersebut (Kunci Privat) tetap berada tanganmu.

Siapa yang memegang kunci? Penerima adalah pemegang tunggal Kunci Privat.

Siapa yang bisa mengirim? Siapa saja yang memiliki Kunci Publik (alamat) si penerima.

Siapa yang bisa membaca? Hanya si penerima yang sah.

Sistem inilah yang menjadi tulang punggung keamanan internet saat ini, mulai dari enkripsi pesan singkat hingga sistem transaksi digital yang tidak memerlukan pihak ketiga yang dipercaya (Bitcoin).
