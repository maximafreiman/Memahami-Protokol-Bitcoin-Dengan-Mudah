# TXID: Bukti dan Ringkasan Data Transaksi yang Dibentuk dari Hash Kriptografi

TXID (Transaction ID) adalah sidik jari digital yang unik untuk setiap transaksi di jaringan Bitcoin. Bayangkan Bitcoin bukan sebagai saldo di buku tabungan, melainkan sebagai tumpukan lembaran cek fisik (UTXO) yang bisa kamu pecah atau gabungkan.

Berikut adalah penjelasan sederhana bagaimana TXID merangkum aktivitas penggunaan UTXO tersebut:

## 1. TXID sebagai "Nama File" Hasil Ringkasan
Secara teknis, TXID adalah hasil dari proses hashing (menggunakan algoritma SHA-256 dua kali)
terhadap data transaksi yang telah disusun dengan urutan tertentu. 

Data ini mencakup: 
- Input – UTXO yang digunakan sebagai sumber dana (referensi ke transaksi sebelumnya). 
- Output – alamat tujuan pengiriman dan jumlah koin, termasuk kembalian. 
- Metadata – versi transaksi dan locktime.

<img width="1920" height="1080" alt="UTXO COUPON (2)" src="https://github.com/user-attachments/assets/8fbcb83d-fe28-4d4a-98dd-975addcfef58" />


Jika ada satu saja angka atau huruf yang berubah dalam detail transaksi tersebut, maka TXID-nya akan berubah total. Inilah yang menjadikannya bukti otentik bahwa data transaksi tidak dimanipulasi.


## 2. Ringkasan Aktivitas UTXO
Karena Bitcoin menggunakan model UTXO (Unspent Transaction Output), setiap transaksi sebenarnya adalah aktivitas "menghancurkan" UTXO lama dan "menciptakan" UTXO baru.

- Proses Input: Transaksi menunjuk sumber koin, dengan mereferensikan TXID dan nomor urut (index) dari UTXO lama yang ingin digunakan.

- Proses Output: Transaksi kemudian menciptakan UTXO baru, TXID yang baru, beserta nomor urut (index)-nya akan menjadi identitas bagi koin koin "segar" yang baru dibuat untuk penerima.

Dengan kata lain, TXID adalah cara efisien untuk melacak silsilah koin tanpa harus membawa seluruh sejarah blok di setiap transaksi. 
Cukup dengan menyebutkan satu deret kode TXID, jaringan tahu persis koin mana yang sedang dipindahkan.

## 3. Bukti Transaksi yang Tak Terbantahkan
TXID berfungsi sebagai resi digital. Kamu tidak perlu mengirimkan detail teknis yang panjang kepada orang lain untuk membuktikan pembayaran. Cukup berikan TXID-nya, dan siapa pun bisa mengeceknya di block explorer atau melalui node mereka sendiri.

Kenapa ini disebut bukti yang kuat?

- Immutability: Sekali TXID masuk ke dalam blok, data di dalamnya tidak bisa diubah tanpa mengubah TXID itu sendiri.

- Verifikasi Instan: Node (seperti Knots) hanya perlu mencocokkan hash data transaksi dengan TXID untuk memastikan transaksi tersebut valid dan belum pernah dipakai sebelumnya (double spending).

## Penjelasan Ringkas:

Proses pembentukan TXID pada Bitcoin dimulai dengan mengambil data transaksi mentah (seperti daftar UTXO yang digunakan dan alamat tujuan), kemudian menyusunnya menjadi satu paket data yang di-hash menggunakan algoritma SHA-256 sebanyak dua kali (double SHA-256).

Hasilnya adalah sebuah deret unik berupa 64 karakter heksadesimal (kombinasi angka dan huruf).

Secara sederhana, hashing dapat dibayangkan seperti “blender digital” yang mengubah data kompleks menjadi satu kode ringkas. Jika satu bit saja dalam data transaksi berubah, maka hasil hash-nya akan berubah total. Inilah yang membantu menjaga integritas dan keamanan setiap perpindahan nilai dalam jaringan Bitcoin.
