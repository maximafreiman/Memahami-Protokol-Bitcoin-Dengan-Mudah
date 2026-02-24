Mempool, Ruang Tunggu Transaksi
---
Mempool adalah "ruang tunggu" digital di setiap komputer (node) yang menjalankan perangkat lunak Bitcoin. Kalau kamu mengirim Bitcoin, transaksi tersebut tidak langsung masuk ke Blockchain. Transaksi itu dikirim ke jaringan dan disimpan di dalam Mempool terlebih dahulu sebelum penambang (miners) memilihnya untuk dimasukkan ke dalam blok baru. Simpel sebenernya. Ini adalah antrean transaksi valid yang akan dilist ke dalam block. Hanya saja, kita juga perlu tahu, kenapa ada sistem antri dan siapa yang bakal jadi prioritas dalam antrean tersebut.

Prosesnya mengikuti alur berikut:

- Inisiasi: Anda menekan tombol "kirim" di dompet digital.
- Propagasi: Transaksi disiarkan ke ribuan node di seluruh dunia. Setiap node memeriksa apakah transaksi Anda valid (misalnya: apakah saldonya cukup?).
- Antrean: Jika valid, transaksi disimpan di Mempool masing-masing node.
- Konfirmasi: Penambang mengambil transaksi dari Mempool dan memasukkannya ke dalam blok. Setelah blok ditambang, transaksi Anda resmi keluar dari Mempool dan masuk ke Blockchain.

Karena kapasitas satu blok Bitcoin terbatas (sekitar 1MB hingga 4MB dengan SegWit), tidak semua orang bisa masuk ke "gerbong" berikutnya. Di sinilah terjadi sistem lelang:

| Kondisi Mempool | Dampak pada Pengguna|
|-----------------|---------------------|
| Kosong/Sepi | Transaksi cepat diproses meskipun biaya (fee) rendah. |
| Penuh/Padat | Penambang akan memprioritaskan transaksi dengan biaya per byte tertinggi. |
| Sangat Padat | Transaksi dengan biaya rendah bisa tertahan di Mempool selama berjam-jam atau berhari-hari. |

Kenapa Mempool ini penting

- Estimasi Biaya: Dompet digital Anda melihat kepadatan Mempool untuk menyarankan berapa biaya yang harus Anda bayar agar transaksi cepat sampai.
- Kesehatan Jaringan: Jika Mempool terus membengkak, itu tandanya jaringan sedang mengalami lonjakan permintaan atau serangan spam.
- Desentralisasi: Setiap node memiliki Mempool-nya sendiri. Tidak ada satu "Mempool pusat"; ukurannya bisa sedikit berbeda di tiap komputer tergantung pengaturan masing-masing.

Perkara mempool ini pun, aku juga menetapkan aturan yang ketat. Aku pakai kapasitas maksimal mempool hanya 50 MB saja, di saat normalnya minimal 100 MB. Karena aku benar2 strict untuk memastikan node ku tidak menyimpan transaksi spam.


