# Replaced By Fee (RBF)

Replace-By-Fee (RBF) adalah fitur dalam protokol Bitcoin yang memungkinkan pengirim transaksi untuk mengganti transaksi yang masih "tertunda" (di dalam mempool) dengan transaksi baru yang memiliki biaya (fee) lebih tinggi.

1. Mengapa RBF Dibutuhkan?
Terkadang, sebuah transaksi bisa "nyangkut" atau membutuhkan waktu sangat lama untuk dikonfirmasi karena fee yang dipasang terlalu rendah dibandingkan dengan transaksi milik orang lain di jaringan Bitcoin. Dengan RBF, kamu nggak perlu menunggu berhari-hari. Kamu cukup mengirimkan kembali transaksi yang sama tetapi dengan fee yang lebih kompetitif agar penambang (miners) lebih tertarik untuk memprosesnya.

2. Cara Kerjanya
Saat kamu mengirim transaksi dengan fitur RBF aktif, transaksi tersebut ditandai sebagai "replaceable". Jika kamu memutuskan untuk menaikkan fee:
- Kamu membuat transaksi baru menggunakan input yang sama (UTXO yang sama).
- Setelah itu atur biaya transaksi ($fee$) yang lebih tinggi dari sebelumnya.
- Node Bitcoin akan melihat transaksi baru ini memiliki nilai ekonomi yang lebih tinggi dan akan menggantikan transaksi lama di dalam mempool.

3. Manfaat Utama
- Efisiensi Biaya: Kamu bisa mulai dengan fee rendah saat jaringan sepi, dan hanya menaikannya jika ternyata jaringan tiba-tiba sibuk.
- Koreksi Kesalahan: Memungkinkan pengirim untuk mengubah alamat tujuan atau nominal (dalam kondisi tertentu), selama transaksi tersebut belum masuk ke dalam blok.

4. Hal Penting yang Perlu Diperhatikan
- Status Konfirmasi: RBF hanya berlaku untuk transaksi yang memiliki 0 konfirmasi. Setelah transaksi masuk ke dalam blok, ia tidak bisa lagi diganti.

- Keamanan bagi Penerima: Merchant atau penerima pembayaran sebaiknya tidak menganggap transaksi "0-conf" (belum dikonfirmasi) sebagai pembayaran final, terutama jika transaksi tersebut memiliki tanda RBF, karena pengirim secara teknis bisa mengarahkan kembali dana tersebut ke dompet mereka sendiri sebelum dikonfirmasi oleh penambang.

Singkatnya, RBF adalah alat bantu untuk memastikan transaksi kamu tetap fleksibel dan tidak terjebak dalam antrean panjang akibat salah estimasi biaya.
