Whitepaper Bitcoin
---
![202211011450-main cropped_1667290056](https://github.com/user-attachments/assets/c705bc11-ff0a-4ff2-b2fc-0272b9561462)

Pernah dengar istilah whitepaper? Singkatnya adalah ini merupakan sebuah dokumen resmi seperti jurnal penelitian mengenai sebuah isu, ide penyelesaian, project, panduan teknis, dan seterusnya. Dalam konteks Bitcoin, Bitcoin Whitepaper berisi mengenai isu yang diangkat tentang sebuah solusi baru untuk perbaikan sistem keuangan, yang di dalamnya juga dijelaskan dengan rinci bagaimana cara Bitcoin bekerja, serta apa tujuan Bitcoin diciptakan.

Ditulis oleh pseudonim bernama **Satoshi Nakamoto** pada **31 Oktober 2008** terciptalah sebuah gagasan baru mengenai bagaimana uang dengan sistem peer to peer digital cash bisa bekerja tanpa pihak ketiga seperti perbankan. Melalui dari perkembangan kriptografi dan komputasi sejak tahun 1974, Satoshi menjelaskan bagaimana semua disiplin ilmu kriptografi dan komputer bisa diimplementasikan dalam uang cash digital.

Isi dari Whitepaper ini ada 13 bagian

- Abstrak
- Pendahuluan
- Transaksi
- Timestamp Server
- Proof of Work
- Network atau Jaringan
- Insentif
- Ruang Pemyimpanan
- Verifikasi Transaksi yang Disederhanakan
- Menggabungkan dan Memisahkan Nilai
- Privasi
- Perhitungan
- Kesimpulan

Semua yang ada di dalam Whitepaper dijelaskan dengan bahasa yang teknis, walaupun ada beberapa bagian yang disederhanakan. Tapi jangan khawatir! Per poin akan dijelaskan dengan sederhana.

--

**1. Abstrak**

Disini dijelaskan dalam bentuk ringkasan satu halaman yang menjelaskan ide besar dan cara kerja utama Bitcoin secara garis besar. Disini dijelaskan, Bitcoin adalah sistem uang digital yang memungkinkan orang mengirim pembayaran langsung tanpa bank atau perantara, dengan keamanan dijaga oleh jaringan komputer global. Transaksi diamankan dengan tanda tangan kriptografi dan dicatat dalam blockchain melalui proof-of-work, sehingga catatannya sulit diubah. Rantai terpanjang dianggap sebagai kebenaran karena mewakili tenaga komputasi terbesar dan menjaga jaringan tetap aman dari kecurangan seperti pembelanjaan ganda.

**2. Pendahuluan**

Disini dijelaskan kalau saat ini, pembayaran di internet masih bergantung pada lembaga keuangan sebagai perantara yang harus dipercaya, tetapi sistem ini mahal, lambat, dan rawan penipuan karena transaksi bisa dibatalkan dan harus dimediasi. Akibatnya, transaksi kecil jadi tidak efisien dan pedagang harus mengumpulkan banyak data pelanggan untuk mengurangi risiko. 

Bitcoin menawarkan solusi dengan mengganti kepercayaan kepada pihak ketiga menjadi bukti kriptografi, sehingga dua orang bisa bertransaksi langsung dan aman. Dengan jaringan peer-to-peer dan sistem penanda waktu berbasis proof-of-work, transaksi dicatat secara berurutan dan hampir tidak bisa diubah, serta tetap aman selama mayoritas kekuatan komputasi dijalankan oleh node yang jujur.

**3. Transaksi**

Disini dijelaskan mekanisme transfer Bitcoin, dan bagaimana aktivitas transfer-menransfer ini diverifikasi. Kita pakai analogi koin biar lebih simpel. Jadi, setiap kali seseorang mengirim koin, dia “menandatangani” bukti bahwa koin itu sekarang milik orang berikutnya. Orang yang menerima bisa mengecek tanda tangan ini untuk memastikan koin itu benar-benar datang dari pemilik sebelumnya.

Masalahnya: Seseorang bisa saja mencoba mengirim koin yang sama ke dua orang berbeda di waktu yang hampir bersamaan.

Biasanya, di sistem bank, ada kantor pusat yang mengecek semua transaksi dan menentukan mana yang sah. Tapi kalau begitu, semua orang harus percaya pada kantor itu. Nah, Bitcoin memilih cara lain: Semua transaksi diumumkan ke seluruh jaringan komputer di dunia.

Komputer-komputer ini bekerja bersama untuk sepakat transaksi mana yang datang lebih dulu.
Transaksi yang diterima pertama oleh mayoritas komputer itulah yang dianggap sah, dan yang datang belakangan otomatis ditolak.

Jadi intinya, Bitcoin tidak mencegah orang mencoba curang, tapi membuat jaringan global bersama-sama menentukan mana transaksi yang benar tanpa perlu bank atau pihak pusat.

<img width="492" height="267" alt="tx bitcoin" src="https://github.com/user-attachments/assets/6bdbdea7-6612-4bf2-9d77-e803abe4dc0f" />

**4. Timestamp Server**

Bayangkan ada papan pengumuman waktu digital.

Setiap beberapa menit, sistem mengumpulkan transaksi yang baru, lalu membuat sidik jari digital (hash) dari kumpulan itu. Sidik jari ini diumumkan ke seluruh jaringan, jadi semua orang bisa melihat: “Pada waktu ini, data seperti ini benar-benar sudah ada.”

Setiap catatan waktu baru juga memasukkan sidik jari dari catatan sebelumnya, sehingga terbentuk rantai yang saling terhubung.
Kalau ada yang mencoba mengubah catatan lama, sidik jarinya akan berubah dan semua orang bisa langsung tahu.

Timestamp server adalah cara Bitcoin memberi cap waktu pada transaksi dan menguncinya dalam rantai yang tidak bisa diubah tanpa ketahuan.

**5. Proof of Work**

Sekarang bayangkan jaringan Bitcoin itu seperti lomba memecahkan teka-teki.

Setiap komputer di jaringan berlomba mencari angka acak yang, ketika digabung dengan data transaksi lalu “diacak” (di-hash), hasilnya memenuhi aturan tertentu, misalnya hasilnya (hash) harus diawali dengan banyak nol. Mencari angka ini susah dan butuh listrik serta waktu, tapi mengeceknya sangat mudah. Kalau sudah ketemu, komputer itu berhak mengumumkan “blok” baru ke jaringan.

Blok ini juga terkunci ke blok sebelumnya. Kalau seseorang mau mengubah satu blok lama, dia harus mengulang teka-teki itu bukan cuma untuk satu blok, tapi untuk semua blok setelahnya. Dan itu hampir mustahil kalau jaringan jujur lebih cepat.

Soal “siapa yang menentukan kebenaran”:
Bitcoin tidak pakai sistem “satu orang satu suara” atau “satu komputer satu suara”.
Yang dipakai adalah siapa yang sudah mengeluarkan usaha paling besar.

Rantai blok yang punya pekerjaan terbanyak (paling banyak teka-teki yang sudah dipecahkan) dianggap sebagai catatan yang benar oleh semua orang.

Dan supaya sistem tetap stabil, jaringan menyesuaikan tingkat kesulitan teka-teki.
Kalau komputer makin cepat dan blok jadi terlalu sering muncul, teka-tekinya dibuat lebih susah.
Kalau komputer sedikit dan blok terlalu lama, teka-tekinya dibuat lebih mudah.

Proof of Work membuat Bitcoin aman dengan mengubah kejujuran menjadi hal yang paling “murah”, dan kecurangan menjadi hal yang sangat “mahal”.

<img width="354" height="87" alt="image" src="https://github.com/user-attachments/assets/115360fd-0190-49d3-b458-eebce28b7b7d" />

**6. Jaringan**

Jaringan Bitcoin seperti banyak komputer yang bekerja sebagai satu tim besar.

- Setiap kali ada transaksi baru, transaksi itu dikirim ke semua komputer di jaringan.
- Setiap komputer mengumpulkan transaksi-transaksi baru dan menyusunnya menjadi satu paket yang disebut blok.
- Semua komputer lalu berlomba memecahkan teka-teki matematika untuk mengamankan blok mereka.
- Komputer yang berhasil pertama mengumumkan bloknya ke jaringan.
- Komputer lain akan memeriksa blok itu. Jika semua transaksi di dalamnya valid dan belum pernah dipakai sebelumnya, blok tersebut diterima.
- Setelah diterima, semua komputer membangun blok berikutnya di atas blok itu, sehingga terbentuk satu rantai.

Kadang dua komputer bisa menemukan blok hampir bersamaan. Sebagian jaringan akan melihat versi A dulu, sebagian melihat versi B dulu.

Dalam kondisi ini, semua komputer sementara mengikuti versi yang pertama mereka terima. Begitu ada blok baru berikutnya, rantai yang menjadi lebih panjang dianggap benar, dan semua komputer akan berpindah ke rantai itu.

Transaksi tidak harus sampai ke semua komputer agar bisa masuk ke sistem. Selama sampai ke banyak komputer, transaksi itu akan segera masuk ke dalam sebuah blok. Kalau ada komputer yang ketinggalan satu blok, dia bisa meminta ulang saat melihat blok berikutnya dan sadar ada bagian yang terlewat.

(Akan segera update untuk lanjutan materi. Stay tune..)
