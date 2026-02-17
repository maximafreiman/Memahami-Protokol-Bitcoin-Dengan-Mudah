Bitcoin Script, Bahasa Mesin yang Dipakai dalam Transaksi Bitcoin
--

Dalam sistem Bitcoin, setiap transaksi tidak dikirim ke sebuah "akun", melainkan dikunci ke dalam sebuah script (rangkaian instruksi komputer). Dalam pembahasan ini, akan dibagi menjadi 2 (fundamental yang melibatkan definisi dan fungsi dan tipe-tipe script).

--

## Bagian Pertama: Definisi dan Fungsi

Bitcoin Script adalah sistem aturan yang dipakai jaringan Bitcoin untuk menentukan apakah suatu dana boleh dipakai atau tidak.

Script bekerja seperti daftar instruksi sederhana yang dijalankan oleh setiap node di jaringan saat memverifikasi transaksi. Script tidak dipakai untuk membuat aplikasi atau menjalankan program kompleks. Script hanya dipakai untuk memeriksa syarat kepemilikan dana.

Cara kerjanya berbasis stack. Data dimasukkan ke dalam tumpukan, lalu instruksi dijalankan satu per satu untuk memproses data tersebut sampai menghasilkan nilai akhir benar atau salah.

Sifat penting Bitcoin Script:

- Stateless: Script tidak menyimpan informasi dari masa lalu. Setiap transaksi diperiksa secara mandiri hanya berdasarkan data yang ada di transaksi itu sendiri.

- Non-Turing Complete: Script tidak memiliki perulangan seperti for atau while. Semua instruksi harus selesai dalam waktu terbatas. Desain ini memastikan verifikasi selalu cepat, terukur, dan tidak bisa disalahgunakan untuk membebani jaringan.

Tujuan utama Script adalah memastikan bahwa hanya pihak yang memenuhi syarat yang bisa menggunakan dana.

--

2. Dua Komponen Utama: ScriptSig dan ScriptPubKey

Setiap transaksi Bitcoin terdiri dari dua bagian kode yang harus "bertemu" agar transaksi valid:

Setiap transaksi Bitcoin melibatkan dua bagian yang saling berhubungan.

- **ScriptPubKey** disebut **locking script.**
Bagian ini dibuat oleh pengirim saat membuat output transaksi. Script ini berisi aturan yang harus dipenuhi agar dana tersebut bisa digunakan di kemudian hari.

- **ScriptSig** disebut **unlocking script.**
Bagian ini dibuat oleh pihak yang ingin menggunakan dana tersebut. Isinya adalah data yang membuktikan bahwa ia memenuhi aturan yang ditetapkan sebelumnya, biasanya berupa tanda tangan digital.

Pada transaksi modern seperti SegWit dan Taproot, data pembuktian ini ditempatkan di bagian yang disebut Witness, tetapi fungsinya tetap sama yaitu memenuhi syarat dari ScriptPubKey.

--

3. Mekanisme Eksekusi (Verifikasi)

Ketika transaksi disiarkan ke jaringan, setiap node menjalankan proses verifikasi yang sama.

Langkah pertama adalah penggabungan.
Node menggabungkan data pembuktian dari ScriptSig atau Witness dengan aturan yang ada di ScriptPubKey.

Langkah kedua adalah eksekusi.
Bitcoin menjalankan instruksi Script dari kiri ke kanan menggunakan sistem stack.

- Data seperti tanda tangan dimasukkan ke dalam stack.
- Perintah yang disebut opcode memproses data tersebut. Contohnya `OP_CHECKSIG` yang memeriksa apakah tanda tangan valid terhadap kunci publik dan isi transaksi. (Untuk opcodes, akan di bahas di bagian ketiga dalam pembahasan ini).

Langkah ketiga adalah evaluasi hasil.
Setelah semua instruksi selesai dijalankan, node melihat nilai terakhir yang tersisa di stack.

- Jika hasilnya True, transaksi dianggap valid.
- Jika hasilnya False atau tidak menghasilkan nilai, transaksi ditolak.

Semua node melakukan proses ini secara independen. Jika hasilnya tidak valid, transaksi tidak akan diterima ke dalam blok.

--

Dari penjelasan di atas, kita bisa melihat bahwa Bitcoin tidak menggunakan konsep akun atau saldo yang tersimpan di suatu tempat. Bitcoin menggunakan sistem aturan yang melekat pada setiap output transaksi. Aturan inilah yang disebut Script, dan seluruh jaringan bertugas memastikan bahwa aturan tersebut dipatuhi sebelum dana bisa dipindahkan kembali.

Dengan kata lain, yang diverifikasi oleh jaringan bukan siapa orangnya, melainkan apakah bukti yang diberikan sesuai dengan kondisi yang sudah ditetapkan sebelumnya.

Pemahaman ini penting karena semua bentuk address Bitcoin sebenarnya hanyalah cara berbeda untuk menuliskan kondisi Script tersebut. Address bukan tujuan akhir pengiriman dana, melainkan representasi yang lebih ringkas dari ScriptPubKey.
 
---

## Bagian 2: Tipe-tipe Script

Setelah memahami fungsi dasar Script sebagai mekanisme penguncian dan pembukaan dana, langkah berikutnya adalah melihat bagaimana bentuk Script ini berkembang dari waktu ke waktu.

Bitcoin memiliki beberapa pola Script standar yang digunakan secara luas, antara lain:

- **P2PK (Pay to Public Key):**
  Bentuk paling awal, dana langsung dikunci ke public key.

- **P2PKH (Pay to Public Key Hash):**
  Menggunakan hash dari public key untuk efisiensi dan privasi.

- **P2SH (Pay to Script Hash):**
  Memungkinkan kondisi yang lebih kompleks tanpa harus langsung terlihat di blockchain.

- **SegWit, termasuk P2WPKH dan P2WSH:**
  Memperbaiki struktur data transaksi dan efisiensi verifikasi.

- **Taproot:**
  Menyederhanakan tampilan transaksi kompleks dan meningkatkan fleksibilitas Script.

Di bagian berikutnya kita akan melihat bagaimana masing-masing tipe ini sebenarnya hanya variasi cara menulis ScriptPubKey, bukan sistem yang berbeda. Dengan memahami polanya, kita bisa membaca struktur transaksi Bitcoin dengan lebih jelas.

--

## “Tipe Address” Sebenarnya Adalah Pola ScriptPubKey

Di Bitcoin, jaringan tidak pernah mengenal istilah address seperti yang biasa kita lihat di wallet.
Yang disimpan di dalam blockchain adalah ScriptPubKey, yaitu aturan teknis yang menentukan bagaimana suatu output bisa dibelanjakan.

Address hanyalah bentuk ringkas agar manusia bisa menyalin dan membagikan aturan tersebut tanpa harus melihat Script yang panjang. Jadi setiap jenis address sebenarnya mewakili pola ScriptPubKey tertentu yang sudah distandardisasi.

Karena itu, ketika kita membahas P2PK, P2PKH, atau Taproot, kita tidak sedang membahas sistem yang berbeda. Kita hanya melihat cara penulisan syarat yang berbeda, sementara mesin Script yang memverifikasi semuanya tetap sama.



## Ringkasan Perkembangan Tipe Script / Address Bitcoin

| Tipe        | Awalan Address | Fokus Utama                              | Kelebihan                                           | Kekurangan                                              | Status Sekarang              | Catatan Penting |
|-------------|----------------|------------------------------------------|-----------------------------------------------------|---------------------------------------------------------|-------------------------------|-----------------|
| P2PK        | (tidak ada)    | Langsung mengunci ke Public Key          | Paling sederhana, bentuk asli desain Bitcoin         | Tidak efisien, public key langsung terekspos             | Sudah jarang dipakai          | Tidak menggunakan address |
| P2PKH       | 1...           | Hash dari Public Key                     | Standar lama yang stabil dan kompatibel             | Fee lebih mahal, ukuran transaksi lebih besar            | Disebut "legacy"              | Masih luas didukung |
| P2SH        | 3...           | Hash dari Script (multisig, dll.)        | Fleksibel untuk aturan kompleks                     | Kurang efisien dibanding SegWit                          | Legacy / transisi             | Pernah dipakai sebagai pembungkus SegWit (Nested SegWit) |
| P2SH-P2WPKH | 3...           | SegWit lewat pembungkus P2SH             | Bisa pakai SegWit sambil tetap kompatibel            | Struktur dobel, bukan desain final                       | Mulai ditinggalkan            | Disebut Nested SegWit |
| P2WPKH      | bc1q...        | SegWit native untuk user tunggal         | Fee lebih murah, struktur bersih                     | Tidak kompatibel dengan sistem sangat lama               | Sangat umum digunakan         | Native SegWit |
| P2WSH       | bc1q...        | SegWit untuk Script kompleks             | Multisig lebih efisien daripada P2SH                 | Lebih teknis                                             | Dipakai layanan & custody     | Pengganti P2SH modern |
| Taproot     | bc1p...        | Privasi dan fleksibilitas lanjut         | Lebih hemat data, multisig tersamarkan               | Adopsi masih berkembang                                  | Arah masa depan Bitcoin       | Menggunakan Schnorr |

---

## Kesimpulan
Bitcoin bekerja bukan dengan konsep saldo akun, tetapi dengan sistem aturan kriptografi yang melekat pada setiap transaksi.

Bitcoin Script adalah mekanisme yang memastikan:
- Dana hanya bisa dipakai oleh pihak yang memiliki bukti matematis yang sah.
- Semua node bisa memverifikasi transaksi secara independen.
- Sistem tetap sederhana, deterministik, dan aman.

Tipe-tipe address yang kita kenal hanyalah evolusi cara menuliskan aturan tersebut agar semakin efisien digunakan oleh jaringan dan manusia.
