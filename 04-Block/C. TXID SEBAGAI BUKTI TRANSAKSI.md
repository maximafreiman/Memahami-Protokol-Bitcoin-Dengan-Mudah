# TXID: Mengapa Bitcoin Tidak Butuh Bank untuk Membuktikan Transaksi

TXID (Transaction ID) adalah sidik jari digital yang unik untuk setiap transaksi di jaringan Bitcoin. Bayangkan Bitcoin bukan sebagai saldo di buku tabungan, melainkan sebagai tumpukan lembaran cek fisik (UTXO) yang bisa kamu pecah atau gabungkan.

Berikut adalah penjelasan sederhana bagaimana TXID merangkum aktivitas penggunaan UTXO tersebut:

## 1. TXID sebagai "Nama File" Hasil Ringkasan
Secara teknis, TXID adalah hasil dari proses hashing (menggunakan algoritma SHA-256 dua kali) terhadap seluruh data mentah transaksi. Data ini mencakup:

- Input: UTXO mana yang kamu pakai (referensi ke transaksi sebelumnya).

- Output: Ke mana koin tersebut dikirim dan berapa sisa (kembalian) untukmu.

- Metadata: Versi transaksi dan locktime.

Jika ada satu saja angka atau huruf yang berubah dalam detail transaksi tersebut, maka TXID-nya akan berubah total. Inilah yang menjadikannya bukti otentik bahwa data transaksi tidak dimanipulasi.


## 2. Ringkasan Aktivitas UTXO
Karena Bitcoin menggunakan model UTXO (Unspent Transaction Output), setiap transaksi sebenarnya adalah aktivitas "menghancurkan" UTXO lama dan "menciptakan" UTXO baru.

- Proses Input: TXID mencatat dari mana asal koinmu. Ia menunjuk ke TXID transaksi sebelumnya dan nomor urut (index) koin yang kamu miliki di sana.

- Proses Output: TXID yang baru akan menjadi identitas bagi koin-koin "segar" yang baru saja kamu buat untuk penerima.

Dengan kata lain, TXID adalah cara efisien untuk melacak silsilah koin tanpa harus membawa seluruh sejarah blok di setiap transaksi. Cukup dengan menyebutkan satu deret kode TXID, jaringan tahu persis koin mana yang sedang dipindahkan.

## 3. Bukti Transaksi yang Tak Terbantahkan
TXID berfungsi sebagai resi digital. Kamu tidak perlu mengirimkan detail teknis yang panjang kepada orang lain untuk membuktikan pembayaran. Cukup berikan TXID-nya, dan siapa pun bisa mengeceknya di block explorer atau melalui node mereka sendiri.

Kenapa ini disebut bukti yang kuat?

- Immutability: Sekali TXID masuk ke dalam blok, data di dalamnya tidak bisa diubah tanpa mengubah TXID itu sendiri.

- Verifikasi Instan: Node (seperti Knots) hanya perlu mencocokkan hash data transaksi dengan TXID untuk memastikan transaksi tersebut valid dan belum pernah dipakai sebelumnya (double spending).

## Penjelasan Ringkas:

Proses pembentukan TXID pada Bitcoin dimulai dengan mengambil data transaksi mentah (seperti daftar UTXO yang digunakan dan alamat tujuan) kemudian "dijadikan 1 dan diringkas" SHA-256 sebanyak dua kali (Double SHA-256) untuk menghasilkan sebuah deret unik berupa 64 karakter heksadesimal (kombinasi huruf dan angka). Kesimpulannya, hashing berfungsi sebagai "blender digital" yang merangkum data kompleks menjadi satu kode ringkas yang mustahil dipalsukan; jika satu bit data di dalam transaksi berubah, maka hasil hash-nya akan berubah total, sehingga menjamin integritas dan keamanan setiap perpindahan nilai dalam jaringan.
