
# Bitcoin Transaction Script

## Pendahuluan

Banyak orang mengira Bitcoin bekerja seperti sistem perbankan, yaitu menyimpan saldo di dalam akun.  
Sebenarnya tidak demikian.

Bitcoin **tidak menyimpan saldo dan tidak mengenal akun**.  
Bitcoin hanya mencatat bahwa ada sejumlah dana yang boleh digunakan jika suatu syarat dipenuhi.

Syarat inilah yang disebut **Script**.

Jadi ketika seseorang “mengirim Bitcoin”, yang sebenarnya terjadi adalah:
- Membuat sebuah kondisi baru.
- Kondisi itu menentukan siapa yang boleh menggunakan dana tersebut selanjutnya.
- Jaringan Bitcoin akan memverifikasi apakah kondisi itu dipenuhi atau tidak.

---

## Apa Itu Bitcoin Script

Bitcoin Script adalah kumpulan aturan sederhana yang digunakan untuk memverifikasi apakah suatu transaksi sah.

Script bukan dibuat untuk menjalankan aplikasi atau program kompleks.  
Script hanya dibuat untuk satu tujuan:

> Memastikan bahwa orang yang membelanjakan Bitcoin benar-benar memiliki hak secara kriptografi.

Ciri Script:
- Tidak memiliki memori.
- Tidak menjalankan perulangan.
- Selalu selesai dieksekusi dengan cepat.
- Hasil akhirnya hanya **valid atau tidak valid**.

Script dijalankan oleh semua node di jaringan untuk memastikan aturan yang sama dipatuhi oleh semua pihak.

---

## Dua Bagian Dalam Setiap Transaksi

Setiap transaksi Bitcoin selalu melibatkan dua bagian:

### 1. ScriptPubKey (Locking Script)

Bagian ini dibuat saat dana dikirim.  
Isinya adalah aturan yang **mengunci dana**.

ScriptPubKey menjawab pertanyaan:
> Apa yang harus dibuktikan agar dana ini bisa dipakai?

---

### 2. ScriptSig / Witness (Unlocking Data)

Bagian ini diberikan saat dana ingin digunakan kembali.  
Isinya adalah bukti untuk memenuhi aturan tadi, biasanya berupa tanda tangan digital.

Bagian ini menjawab:
> Apakah kamu benar memenuhi syarat yang diminta?

---

## Bagaimana Proses Verifikasi Terjadi

Node Bitcoin akan:
1. Menggabungkan Unlocking Data dengan Locking Script.
2. Menjalankan Script tersebut.
3. Melihat hasil akhirnya.

Jika hasilnya **True**, transaksi valid.  
Jika hasilnya **False**, transaksi ditolak.

Bitcoin tidak peduli siapa pengirimnya.  
Bitcoin hanya peduli apakah buktinya benar.

---

## Address Bitcoin Sebenarnya Bukan Tujuan Dana

Address yang kita lihat di wallet hanyalah **cara manusia menuliskan Script dalam bentuk yang lebih ringkas**.

Blockchain tidak menyimpan address.  
Blockchain menyimpan Script.

Perbedaan jenis address berarti perbedaan cara menulis aturan, bukan sistem yang berbeda.

---

## Evolusi Cara Menulis Script

Seiring waktu, cara menulis Script berkembang agar:
- Lebih efisien
- Lebih hemat biaya
- Lebih fleksibel
- Lebih privat

Berikut perkembangan utamanya.

---

## Ringkasan Perkembangan Tipe Script / Address Bitcoin

| Tipe        | Awalan Address | Fokus Utama                              | Kelebihan                                           | Kekurangan                                              | Status Sekarang              | Catatan Penting |
|-------------|----------------|------------------------------------------|-----------------------------------------------------|---------------------------------------------------------|-------------------------------|-----------------|
| P2PK        | (tidak ada)    | Langsung mengunci ke Public Key          | Paling sederhana, bentuk asli desain Bitcoin         | Tidak efisien, public key langsung terekspos             | Sudah jarang dipakai          | Tidak menggunakan address |
| P2PKH       | 1...           | Hash dari Public Key                     | Standar lama yang stabil dan kompatibel             | Fee lebih mahal, ukuran transaksi lebih besar            | Disebut "legacy"              | Masih luas didukung |
| P2SH        | 3...           | Hash dari Script (multisig, dll.)        | Fleksibel untuk aturan kompleks                     | Kurang efisien dibanding SegWit                          | Legacy / transisi             | Pernah dipakai sebagai pembungkus SegWit |
| P2SH-P2WPKH | 3...           | SegWit lewat pembungkus P2SH             | Bisa pakai SegWit sambil tetap kompatibel            | Struktur dobel, bukan desain final                       | Mulai ditinggalkan            | Disebut Nested SegWit |
| P2WPKH      | bc1q...        | SegWit native untuk user tunggal         | Fee lebih murah, struktur bersih                     | Tidak kompatibel dengan sistem sangat lama               | Sangat umum digunakan         | Native SegWit |
| P2WSH       | bc1q...        | SegWit untuk Script kompleks             | Multisig lebih efisien daripada P2SH                 | Lebih teknis                                             | Dipakai layanan & custody     | Pengganti P2SH modern |
| Taproot     | bc1p...        | Privasi dan fleksibilitas lanjut         | Lebih hemat data, multisig tersamarkan               | Adopsi masih berkembang                                  | Arah masa depan Bitcoin       | Menggunakan Schnorr |

---

## Apa Yang Sebenarnya Berubah Dari Waktu ke Waktu

Yang berubah bukan sistem Bitcoin.

Yang berubah hanyalah:
- Cara menulis kondisi.
- Cara menyimpan data agar lebih ringan.
- Cara meningkatkan privasi dan efisiensi.

Mesin verifikasi Script tetap sama sejak awal Bitcoin dibuat.

---

## Kesimpulan

Bitcoin bukan sistem akun, melainkan sistem kondisi kriptografi.

Setiap transaksi:
- Mengunci dana dengan aturan.
- Membuka dana dengan bukti.
- Diverifikasi secara independen oleh seluruh jaringan.

Script adalah fondasi dari semua transaksi Bitcoin.  
Jenis-jenis address hanyalah evolusi cara menuliskan Script tersebut agar semakin efisien digunakan oleh jaringan dan manusia.

---

## Lanjutan Pembahasan

Setelah memahami bahwa Script adalah kumpulan aturan, langkah berikutnya adalah memahami **opcode**, yaitu instruksi dasar yang digunakan di dalam Script untuk menjalankan proses verifikasi tersebut.
