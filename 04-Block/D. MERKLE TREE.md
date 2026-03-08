# Merkle Tree, Struktur Matematika yang Menjaga Ribuan Data (TXID) dalam 1 Kode


### A. Apa itu Merkle Tree?

Bayangkan ada ribuan TXID (transaksi) dalam satu block. Merkle Tree adalah cara meringkas ribuan transaksi itu menjadi satu kode tunggal yang disebut Merkle Root.

Jauh sebelum ada Bitcoin, seorang ilmuwan komputer bernama **Ralph Merkle** mematenkan konsep ini pada tahun 1979. Saat itu, masalah besar di dunia komputer adalah: Bagaimana cara memverifikasi data besar tanpa harus membaca seluruh data tersebut?

Ralph Merkle menciptakan solusi matematis berupa "pohon" yang saling mengikat. Penemuan ini sebenarnya sudah ada puluhan tahun, tapi hanya menjadi teori akademis sampai akhirnya Bitcoin lahir pada 2009.

### B. Cara Kerja Merkle Tree Secara Sederhana

Bayangkan sebuah block Bitcoin berisi 4 transaksi (A, B, C, dan D). Inilah yang terjadi di balik layar secara teknis:

1. Level Dasar (Transaksi): Setiap transaksi (TXID) adalah baris data mentah.

2. Hashing Pertama: Transaksi A di-hash, Transaksi B di-hash. Begitu juga C dan D.

3. Penggabungan (Pairing): Hash A digabung dengan Hash B, lalu di-hash lagi menjadi Hash AB. Begitu juga C dan D menjadi Hash CD.

4. Puncak (Merkle Root): Hash AB digabung dengan Hash CD, lalu di-hash terakhir kali menjadi Merkle Root.

Kenapa ini teknis yang jenius?
Karena jika kamu mengubah satu huruf saja di Transaksi A, maka Hash A berubah. Karena Hash A berubah, maka Hash AB ikut berubah. Akhirnya, Merkle Root di puncak pohon ikut berubah total.
