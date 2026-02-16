Transaction Fee, Balas Budi ke Miner
--

Transaction Fee adalah "ongkos kirim" yang kamu bayar kepada para Miner (penambang) agar mereka mau memasukkan catatan transaksi kamu ke dalam buku besar Bitcoin (Blockchain).

Kenapa kita perlu untuk bayar fee? Bitcoin tidak punya karyawan atau kantor pusat. Salah satu kontributor terbesar dalam Bitcoin network adalah miner. Miner (penambang) tersebar di seluruh dunia, menggunakan komputer super kuat dan listrik yang besar. Karena effort miner dalam memasukkan transaksi dan mencetak blok itulah, miner perlu dihargai jasanya, berupa memberi mereka fee.

--

Setidaknya ada tiga alasan utama kenapa biaya ini wajib ada dalam sistem Bitcoin:

**1. Menjaga Keamanan Jaringan (Insentif untuk Miner)**

Bitcoin tidak punya karyawan atau kantor pusat. Keamanannya dijaga oleh ribuan Miner (penambang) di seluruh dunia yang menggunakan komputer super kuat dan listrik yang besar.

Upah Kerja: Miner mau mengeluarkan biaya listrik mahal karena mereka berharap dapat imbalan.

Masa Depan Bitcoin: Saat ini, Miner memang masih dapat hadiah koin baru dari sistem (Block Subsidy). Namun, jumlah koin baru ini makin lama makin sedikit (karena peristiwa Halving). Suatu saat nanti, hanya transaction fee yang akan menjadi gaji utama bagi para Miner agar mereka tetap mau menjaga keamanan jaringan Bitcoin.

**2. Mencegah Serangan "Spam"**

Bayangkan jika transaksi Bitcoin itu gratis. Apa yang terjadi?

Satu orang jahat bisa iseng mengirim 1 miliar transaksi sampah (misal: kirim 1 Rupiah ke diri sendiri berkali-kali) dalam sekejap.

Akibatnya, jaringan Bitcoin akan langsung macet, memori komputer para pengelola jaringan akan penuh, dan transaksi "asli" milikmu tidak akan pernah sampai.

Fee berfungsi sebagai filter: Dengan adanya biaya (meskipun kecil), serangan spam menjadi sangat mahal dan tidak masuk akal untuk dilakukan.

**3. Mengatur Antrean (Prioritas)**

Ruang di dalam satu "Blok" Bitcoin itu terbatas (hanya sekitar 1MB hingga 4MB saja). Karena kapasitasnya terbatas sementara yang mau pakai banyak, harus ada cara adil untuk menentukan siapa yang berhak masuk duluan.

Tanpa fee, tidak ada cara untuk menentukan siapa yang harus didahului.

Dengan fee, sistem menjadi pasar bebas yang adil: Siapa yang punya urusan sangat mendesak bisa membayar lebih untuk "menyalip" antrean, sedangkan yang santai bisa membayar murah dan menunggu saat jaringan sepi.

--

Bagaimana Cara Perhitungannya?
 
Berbeda dengan transfer bank yang biasanya memotong persentase (misal 1%), Bitcoin menggunakan satuan satoshis per virtual byte (sats/vB).

Rumus Sederhana: $$Total Fee = Ukuran Transaksi (vB) \times Tarif Fee (sats/vB)$$

- Ukuran Transaksi: Tergantung pada riwayat saldo kamu. Jika kamu mengirim 1 BTC hasil dari 10 pecahan 10 UTXO (0,1 BTC x 10), ukuran datanya akan lebih besar (lebih mahal) dibanding mengirim 1 BTC yang didapat dari satu UTXO bulat.
- Tarif (sats/vB): Ini adalah harga yang kamu tawarkan.

Kita ambil contoh:

Misalkan kamu melakukan transaksi dengan ukuran data sebesar 140 vB.

| Kondisi | Tarif fee (sats/vB) } | Total Fee | Estimasi Waktu |
|---------|-----------------------|-----------|----------------|
| Darurat | 100 sats/vB | 100 \times 140 = 14.000 sats | Paling cepat |
| Santai Saja | 10 sats/vB | 10 \times 110 = 1.400 sats | Lebih lambat |

Semakin mahal fee yang kamu berikan, maka transaksi kamu akan diprioritaskan untuk dicatat oleh miner ke dalam blok.

--

Kalau mau fee murah, kamu punya dua pilihan:

- Menunggu saat pasar sepi (tarif sats/vB rendah).

- Menggunakan teknologi alamat yang lebih modern seperti SegWit atau Taproot yang secara otomatis membuat "ukuran data" transaksi kamu lebih ramping (vB lebih kecil).

-- 

Oke, itu tadi adalah bagaimana mekanisme dan perhitungan fee bekerja.

Tapi sebentar. Segwit? Taproot? Apa itu? Ini adalah Bitcoin Address Script.

Untuk pembahasan ini, kita next ke sub-bab selanjutnya.
