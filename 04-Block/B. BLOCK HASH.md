# Hashing dalam Bitcoin, Alasan Kenapa Data yang Tersimpan Tidak Bisa Dimodifikasi Sembarangan

**A. Analogi Jus Alpukat dan Hashing**

Bayangkan data mentah (seperti file gambar atau ribuan baris teks) adalah tumpukan buah alpukat yang berat dan sulit diperiksa satu per satu kualitasnya. Dalam dunia digital, membandingkan dua data raksasa secara manual itu tidak praktis dan memakan waktu. Di sinilah Hashing berperan sebagai 'Blender Digital' (Fungsi Matematika). Kamu tidak memasukkan alpukat ke blender untuk mempermudah memakannya, melainkan untuk menghasilkan segelas jus (Hash) dengan warna dan tekstur yang sangat spesifik sebagai identitas unik. Jadi, daripada repot-repot mengecek setiap serat buah alpukat untuk memastikan kualitasnya, kamu cukup melihat satu gelas jusnya saja: jika warnanya pas, berarti isi datanya asli dan tidak berubah.

Secara teknis, Hashing adalah proses memasukkan data mentah (seperti file gambar, tulisan, atau database) ke dalam sebuah fungsi matematika (disebut Hash Function) untuk menghasilkan sebuah "ringkasan" unik dengan ukuran yang tetap.


**2. Sifat Teknis Utama**
Untuk menjaga keamanan data, proses "membuat jus" ini harus memenuhi tiga syarat teknis:

- **Satu Arah (Irreversible):** Kamu tidak bisa membedah kode hash untuk mendapatkan data aslinya. Ibaratnya, Kamu bisa membuat jus dari alpukat, tapi secara teknis mustahil mengembalikan cairan jus tersebut menjadi buah alpukat yang utuh lagi..

- **Deterministik:** Input yang sama akan selalu menghasilkan kode hash yang sama. Mirip seperti jus alpukat, jika kamu menggunakan blender yang sama dengan bahan yang sama persis (misal: 1 alpukat + 10gr gula), hasilnya akan selalu menghasilkan warna dan rasa jus yang identik.

- **Efek Avalanche:** Memodifikasi data akan merubah seluruh Hash-nya. Jika kamu mengubah satu titik kecil saja pada data (ibarat menambahkan satu tetes pewarna pada jus), maka seluruh hasil hash (warna jus) akan berubah total, bukan hanya berubah sedikit.

**3. Cara Kerja Hashing Secara Umum**
Blender digital ini bekerja dengan cara mencacah data input menjadi potongan-potongan bit (yaitu unit data terkecil di komputer yang hanya berisi angka 0 dan 1, ibarat mencacah alpukat menjadi butiran sel terkecil).

Setelah dicacah, data tersebut "diaduk" melalui serangkaian operasi logika (seperti pergeseran posisi bit dan penambahan matematis) berkali-kali. Hasil akhirnya selalu memiliki panjang yang tetap (misalnya 64 karakter pada SHA-256), tidak peduli apakah inputnya hanya satu kata atau seluruh isi perpustakaan.

Untuk simulasi hashing, bisa main-main ke website berikut:
https://emn178.github.io/online-tools/sha256.html

Coba aja kamu tulis 'SAYA GANTENG'
Nanti dihashing, dan menghasil kan kode hash:

`47d8799e160ce9a893a46d4b144a2187847c5e48c3de80b235d8c6b850d7b983`

Tapi kalau kamu tulis 'SAYA GANTENG.' dengan tambahan titik setelahnya,
maka kode hashnya akan berubah semuanya:

`dde1e5267f5f35eb18da5f96483461d2d44bf80dd926c6dc6055deacb3e61c03`



**4. Pemakaian SHA-256 dan Nonce pada Bitcoin**
Dalam hashing, satu perubahan sedikit saja, akan memengaruhi semuanya.

Dalam sistem Bitcoin, setiap "blok" transaksi harus memiliki hash yang sah sebagai identitasnya. Namun, ada aturan tambahan: hash yang dihasilkan harus memenuhi tingkat kesulitan tertentu (misalnya, hasil hash-nya harus diawali dengan banyak angka nol).

Di sinilah peran Nonce (sebuah variabel angka acak yang fungsinya adalah untuk mengubah nilai input agar menghasilkan output hash yang berbeda tanpa merubah data transaksi asli). Karena data transaksi di dalam blok (alpukatnya) tidak boleh diubah, para penambang (miners) memasukkan Nonce sebagai bahan eksperimen tambahan agar hasil "jus" mereka berubah-ubah warnanya sampai menemukan yang sesuai aturan.

- Eksperimen 1: Data Transaksi + Nonce `0` = Hash `8f2c...` (Gagal/Warna tidak sesuai).

- Eksperimen 2: Data Transaksi + Nonce `1` = Hash `4a1b...` (Gagal).

- Eksperimen Jutaan Kali: Data Transaksi + Nonce `562.812` = Hash `000000...` (Berhasil!).


Intinya, Hashing di Bitcoin sedikit, berbeda. Ibarat pembuatan jus alpukat tadi, Nonce itu seperti tetes-tetes stevia (pemanis cair seperti gula) untuk menemukan hash (jus alpukat) yg tepat. Kalau cuma 1 tetes, kurang manis. Tambahkan lagi beberapa tetes sampai hasilnya tepat.


**5. Kesimpulan** 
Hashing adalah segel keamanan; jika hacker mengubah "resep dan bahan" (data) di masa lalu, hasilnya "jus" (hash) di blok tersebut dan setelahnya akan berubah total, sehingga manipulasi langsung ketahuan. Sementara Nonce adalah variabel eksperimen yang memastikan data tetap murni namun tetap sulit dipalsukan karena butuh kerja keras (komputasi) untuk menemukan "rasa" yang pas.
