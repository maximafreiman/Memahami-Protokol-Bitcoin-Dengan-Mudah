# Hashing dalam Bitcoin, Alasan Kenapa Data yang Tersimpan Tidak Bisa Dimodifikasi Sembarangan

**A. Analogi Jus Alpukat dan Hashing**

Bayangkan data mentah (seperti file gambar atau ribuan baris teks) adalah tumpukan buah alpukat yang berat dan sulit diperiksa satu per satu kualitasnya. Dalam dunia digital, membandingkan dua data raksasa secara manual itu tidak praktis dan memakan waktu. Di sinilah Hashing berperan sebagai 'Blender Digital' (Fungsi Matematika). Kamu tidak memasukkan alpukat ke blender untuk mempermudah memakannya, melainkan untuk menghasilkan segelas jus (Hash) dengan warna dan tekstur yang sangat spesifik sebagai identitas unik. Jadi, daripada repot-repot mengecek setiap serat buah alpukat untuk memastikan kualitasnya, kamu cukup melihat satu gelas jusnya saja: jika warnanya pas, berarti isi datanya asli dan tidak berubah.

Secara teknis, Hashing adalah proses memasukkan data mentah (seperti file gambar, tulisan, atau database) ke dalam sebuah fungsi matematika (disebut Hash Function) untuk menghasilkan sebuah "ringkasan" unik dengan ukuran yang tetap.


2. Sifat Teknis Utama
Untuk menjaga keamanan data, proses "membuat jus" ini harus memenuhi tiga syarat teknis:

Satu Arah (Irreversible): Kamu tidak bisa membedah kode hash untuk mendapatkan data aslinya. Ibaratnya, Kamu bisa membuat jus dari alpukat, tapi secara teknis mustahil mengembalikan cairan jus tersebut menjadi buah alpukat yang utuh lagi..

Deterministik: Input yang sama akan selalu menghasilkan kode hash yang sama. Mirip seperti jus alpukat, jika kamu menggunakan blender yang sama dengan bahan yang sama persis (misal: 1 alpukat + 10gr gula), hasilnya akan selalu menghasilkan warna dan rasa jus yang identik.

Efek Avalanche: Memodifikasi data akan merubah seluruh Hash-nya. Jika kamu mengubah satu titik kecil saja pada data (ibarat menambahkan satu tetes pewarna pada jus), maka seluruh hasil hash (warna jus) akan berubah total, bukan hanya berubah sedikit.


(Penjelasan lebih lanjut, soon)
