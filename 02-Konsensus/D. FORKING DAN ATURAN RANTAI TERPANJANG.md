Forking dan Aturan Rantai Terpanjang
--

Sekarang, bayangkan situasi ini: Ada dua penambang di dua negara (kita pakai nama negara fiktif sebagai contoh), satu di Genovia dan satu di Kashfarstan. Secara ajaib, keduanya menemukan "angka ajaib" (Proof of Work) di detik yang hampir bersamaan.

Keduanya berteriak ke jaringan: "Aku pemenangnya! Ini catatan transaksiku!" Inilah yang disebut sebagai Fork (percabangan). Sebagian komputer di dunia mengikuti si Genovia, sebagian lagi mengikuti si Kahsfarstan. Konsensus (kesepakatan tunggal) pun terbelah dua. Bagaimana Bitcoin menyatukannya kembali?

--

**Aturan Rantai Terpanjang (The Longest Chain Rule)**

Bitcoin memiliki aturan emas untuk mengatasi perselisihan ini: "Ikuti rantai yang memiliki bukti kerja (akumulasi energi) paling banyak."

Begini prosesnya secara sederhana:

1. Dua Kandidat: Sekarang ada dua versi buku catatan (Blok A dan Blok B) yang sama-sama sah menurut aturan matematika.

2. Perlombaan Berlanjut: Penambang lain di seluruh dunia akan memilih salah satu (biasanya yang mereka terima lebih dulu) dan mulai mencoba menambang blok berikutnya di atas blok pilihan mereka.

3. Pemenang Terpilih: Karena kecepatan internet dan keberuntungan berbeda-beda, pasti salah satu tim akan menemukan blok baru lebih cepat.
   - Misalnya, tim yang mengikuti Blok A berhasil menemukan blok selanjutnya (Blok A+1).
   - Sekarang, jalur Blok A menjadi lebih panjang (dua blok) dibanding jalur Blok B (satu blok).

4. Konsensus Kembali Bersatu: Begitu komputer di jalur Blok B melihat ada jalur yang lebih panjang (Blok A + A+1), mereka secara otomatis membuang catatan Blok B dan beralih ke jalur Blok A.

--

Analogi Sederhana: Bayangkan ada dua gosip yang beredar. Kamu bingung mana yang benar. Tapi kemudian, gosip pertama memiliki bukti foto dan saksi yang jauh lebih lengkap dan panjang ceritanya. Secara logis, kamu akan meninggalkan gosip kedua dan mengikuti versi yang punya bukti lebih kuat.
