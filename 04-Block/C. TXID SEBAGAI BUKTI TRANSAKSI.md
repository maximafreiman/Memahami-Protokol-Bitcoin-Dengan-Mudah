# TXID: Mengapa Bitcoin Tidak Butuh Bank untuk Membuktikan Transaksi

TXID adalah nomor identitas unik dari sebuah transaksi Bitcoin. Bentuknya berupa deretan 64 karakter (huruf dan angka).

Kalau kamu mengirim Bitcoin, sistem akan mencatat rinciannya (siapa pengirimnya, ke mana tujuannya, berapa jumlahnya). Kumpulan info ini kemudian "dibungkus" dan diberi label nomor seri. Itulah TXID.

## 1. Bagaimana TXID Muncul? (Analogi Stempel)

TXID muncul melalui proses matematika yang disebut Hashing. Anggap saja ini seperti mesin stempel otomatis:

Kamu memasukkan data transaksi ke dalam mesin.

Mesin melakukan perhitungan matematis cepat.

Mesin mengeluarkan "stempel" unik (TXID).

Sifat utamanya:

- Satu Data, Satu Hasil: Jika datanya sama, TXID-nya akan selalu sama.

- Anti-Manipulasi: Jika kamu mencoba mengubah jumlah Bitcoin yang dikirim (misal dari 0.1 jadi 1.0) meski cuma sedikit, mesin akan mengeluarkan TXID yang benar-benar berbeda. Ini yang membuat Bitcoin mustahil dipalsukan.

## Apa Fungsinya?
Di dalam jaringan Bitcoin, TXID punya tiga fungsi utama yang sangat mendasar:

- Sebagai Karcis Antrean (Mempool): Sebelum masuk ke dalam block (dicatat permanen), transaksi kamu menunggu di "ruang tunggu" bernama Mempool. TXID adalah nomor antreanmu agar kamu bisa mengecek apakah transaksi sudah diproses oleh penambang (miners) atau belum.

- Sebagai Bukti Kepemilikan (UTXO): Bitcoin bekerja dengan sistem "Koin yang Belum Terpakai" (UTXO). Saat kamu ingin mengirim Bitcoin, dompetmu akan mencari TXID lama di mana kamu pernah menerima koin, lalu menggunakannya sebagai modal untuk transaksi baru.

*Tanpa TXID, kamu tidak bisa membuktikan dari mana asal Bitcoin yang ingin kamu belanjakan.*

- Penyusun Rantai (Blockchain): Ribuan TXID ini akan dikunci di dalam sebuah Block. TXID-TXID tersebut saling mengikat secara matematis, sehingga jika ada satu saja transaksi yang coba dihapus atau diubah di masa lalu, seluruh jaringan akan tahu karena TXID-nya tidak cocok lagi.

## Bagaimana TXID Muncul? (Analogi Stempel)
TXID muncul melalui proses matematika yang disebut Hashing. Anggap saja ini seperti mesin stempel otomatis:

- Kamu memasukkan data transaksi ke dalam mesin.

- Mesin melakukan perhitungan matematis cepat.

- Mesin mengeluarkan "stempel" unik (TXID).

Sifat utamanya:

**Satu Data, Satu Hasil: Jika datanya sama, TXID-nya akan selalu sama.**

Anti-Manipulasi: Jika kamu mencoba mengubah jumlah Bitcoin yang dikirim (misal dari 0.1 jadi 1.0) meski cuma sedikit, mesin akan mengeluarkan TXID yang benar-benar berbeda. Ini yang membuat Bitcoin mustahil dipalsukan.

## Kesimpulan

TXID adalah sidik jari unik berupa deretan 64 karakter yang otomatis tercipta saat kamu melakukan transaksi Bitcoin. Ia berfungsi sebagai nomor referensi atau "tanda terima" digital yang membedakan satu transaksi dengan ribuan transaksi lainnya di dalam jaringan. Secara teknis, TXID muncul dari hasil perhitungan matematis (hashing) terhadap rincian data transaksi seperti jumlah koin dan alamat tujuan, sehingga jika ada satu detail kecil saja yang diubah, TXID tersebut akan berubah total. Inilah yang memungkinkan siapa pun untuk melacak status pengiriman dan membuktikan kepemilikan koin secara transparan tanpa perlu bergantung pada catatan tertutup milik bank.
