# Reorg (Reorganization), Solusi Jika Data Transaksi Tersimpan di Jaringan Rantai yang Pendek

Salah satu hal yang mutlak di Bitcoin adalah data transaksi tersimpan di blok dengan rantai jaringan terpanjang. Adakalanya ada 2 blok yang muncul bersamaan sehingga terjadilah temporary fork. 


<img width="1920" height="1080" alt="Untitled design (2)" src="https://github.com/user-attachments/assets/e1e8bb88-e469-4af7-96e9-639cd28dd3df" />


Kita lihat ilustrasi ini. Misal dirantai A (atas) ada blok ke 800.000, di rantai B (bawah) ada blok ke 800.000 juga. Nanti kita lihat siapa diantara 2 cabang ini yang berhasil membuat blok baru dan membentuk rantai terpanjang.


--
<img width="1920" height="1080" alt="Untitled design (3)" src="https://github.com/user-attachments/assets/525e2fbb-3a5c-447a-a614-d311d89cbdfc" />

Oh! Rantai A (atas) berhasil tercipta blok baru lebih cepat. Sehingga data tx selanjutnya masuk ke 800.001. Bagaimana dengan data-data tx yg sudah terlanjur masuk ke blok di rantai B (bawah)? Disinilah reorg terjadi. Semua data-data tx yg masuk ke blok di rantai terpendek akan dikembalikan ke mempool. Setelah itu langsung dimasukkan ke rantai panjang. Nah, misal data-data tx belum masuk semua ke 800.001, maka dia akan tetap stay di mempool sampai blok 800.002. Sebagaimana seharusnya.

--
<img width="1920" height="1080" alt="Untitled design (4)" src="https://github.com/user-attachments/assets/e337ff04-e5ba-4b0c-b935-3bdafdc10ee3" />


Reorg hanya bisa terjadi secara praktikal ketika ada 1 confirmed block muncul di salah satu rantai (panjang rantainya selisih 1 blok). Kalau sudah ada 3 blok muncul setelahnya di rantai terpanjang, sudah dianggap susah untuk melakukan reorg. 

## Apa Fungsi Reorg?

Meskipun terdengar seperti "kesalahan", reorg sebenarnya adalah fitur keamanan yang sangat vital:

- Menjaga Konsensus Global: Reorg adalah cara Bitcoin memastikan bahwa semua orang di seluruh dunia akhirnya sepakat pada satu versi sejarah transaksi yang sama, meskipun ada gangguan koneksi atau persaingan antar penambang.

- Mencegah Perpecahan Permanen: Tanpa reorg, jaringan akan terus terpecah setiap kali ada dua blok yang ditemukan bersamaan, yang akan menghancurkan nilai Bitcoin sebagai uang tunggal.

- Keamanan terhadap Penyerangan: Jika ada pihak jahat yang mencoba mengubah sejarah, mereka harus membuat jalur yang lebih panjang dari jalur asli. Mekanisme reorg memaksa node untuk selalu memilih jalur yang paling sulit dibuat (paling banyak energinya), sehingga sistem tetap aman.

## Bagaimana Peran Node dalam Reorg?

Peran Node dalam Reorg
Node secara otomatis melakukan tugas ini:

- Menerima header blok baru.

- Menyadari ada jalur yang lebih panjang (lebih banyak Proof-of-Work).

- Melakukan disconnect pada blok di jalur yang kalah.

- Melakukan connect pada blok di jalur yang menang.

## Kesimpulan

Reorg adalah proses otomatis di mana node Bitcoin beralih ke jalur blok yang lebih panjang (memiliki bukti kerja lebih besar) karena sempat terjadi percabangan sementara. Secara instan, node akan membuang blok yang kalah dan mengembalikan transaksi di dalamnya ke dalam mempool agar bisa antre kembali untuk masuk ke blok berikutnya, guna memastikan seluruh jaringan tetap memiliki satu catatan sejarah yang sinkron dan valid.
