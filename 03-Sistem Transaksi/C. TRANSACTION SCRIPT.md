Transaction Script, Bahasa Mesin yang Dipakai dalam Transaksi Bitcoin
--

Dalam sistem Bitcoin, setiap transaksi tidak dikirim ke sebuah "akun", melainkan dikunci ke dalam sebuah script (rangkaian instruksi komputer). Dalam pembahasan ini, akan dibagi menjadi 3 (fundamental yang melibatkan definisi dan fungsi, tipe-tipe data, dan operator codes).

## Bagian Pertama: Definisi dan Fungsi

1. Apa itu Bitcoin Script?

Bitcoin Script adalah bahasa pemrograman Stack-Based. Artinya, cara kerjanya adalah dengan menumpuk data dan memprosesnya satu per satu dari atas ke bawah.

- Stateless: Script ini tidak punya "memori". Dia tidak tahu apa yang terjadi di transaksi sebelumnya atau sesudahnya. Dia cuma fokus menyelesaikan instruksi yang ada di depannya saat itu juga.
- Non-Turing Complete: Script tidak memiliki fungsi loop (perulangan seperti `for` atau `while`). Ini sengaja dilakukan agar programnya cepat selesai dieksekusi dan tidak bisa digunakan untuk menyerang jaringan dengan kode yang berjalan selamanya.

--

2. Dua Komponen Utama: ScriptSig dan ScriptPubKey

Setiap transaksi Bitcoin terdiri dari dua bagian kode yang harus "bertemu" agar transaksi valid:

- **ScriptPubKey** (Locking Script):
Ini adalah potongan kode yang ditaruh oleh si pengirim Bitcoin di dalam output transaksi. Kode ini berisi instruksi tentang syarat apa yang harus dipenuhi agar Bitcoin tersebut bisa dipindahkan lagi di masa depan.

- **ScriptSig** (Unlocking Script):
Ini adalah data yang disediakan oleh orang yang ingin memakai Bitcoin tersebut. Isinya biasanya berupa tanda tangan digital dan kunci publik (public key).

--

3. Mekanisme Eksekusi (Verifikasi)

Ketika sebuah transaksi dikirim ke jaringan, para penambang (miners) dan node akan menjalankan proses verifikasi berikut:

- Penggabungan: Node mengambil data dari ScriptSig (milik pemakai) dan menempelkannya di depan ScriptPubKey (milik pengirim lama).

- Eksekusi Stack: Mesin Bitcoin (Virtual Machine) akan membaca kode tersebut dari kiri ke kanan.

  - Data (seperti tanda tangan) akan didorong (push) ke dalam tumpukan.
  - Perintah/Operator (seperti OP_CHECKSIG) akan mengeksekusi data yang ada di tumpukan tersebut.

- Hasil Akhir: Setelah semua instruksi selesai dijalankan, mesin akan melihat item terakhir yang tersisa di tumpukan.
  - Jika hasilnya adalah 1 (True), maka transaksi dianggap valid dan sah.
  - Jika hasilnya 0 (False) atau kosong, maka transaksi ditolak karena syaratnya tidak terpenuhi.
 
---

## Bagian 2: Tipe-tipe Script
menyusul.
