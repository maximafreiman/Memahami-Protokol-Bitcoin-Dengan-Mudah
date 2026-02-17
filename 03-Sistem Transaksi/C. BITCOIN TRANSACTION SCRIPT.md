# Bitcoin Transaction Script, Penjelasan Sederhana dari Nol Bagaimana Bitcoin Dikirim dan Kepemilikannya Dikunci Tanpa Sistem Akun

Kenapa harus bahas script? Banyak orang mengira Bitcoin itu seperti:
- kirim saldo
- dari akun A ke akun B

Padahal Bitcoin tidak punya akun.

Di dalam protokol Bitcoin, yang ada hanyalah UTXO, yaitu koin yang dikunci dengan aturan.

Aturan itulah yang disebut Bitcoin Script.

---

## Konsep Paling Penting

Bitcoin tidak pernah mengirim ke “alamat”.

Bitcoin sebenarnya bekerja seperti ini:

    Mengunci koin dengan sebuah kondisi matematika.

Dan untuk membukanya:

    Kita harus membuktikan bahwa syarat itu terpenuhi.

Jadi Bitcoin bukan sistem kirim uang.

Bitcoin adalah sistem kunci dan buka kunci.

---

# **Bagian 1: Apa Itu Bitcoin Script?**

Bitcoin Script adalah bahasa instruksi sederhana yang dipakai untuk menentukan siapa yang boleh memakai koin tertentu.

Script bukan untuk membuat aplikasi.  
Script hanya untuk memverifikasi bahwa suatu transaksi sah.

## Cara Kerjanya

Script bekerja dengan sistem tumpukan (stack):

1. Data dimasukkan ke stack.
2. Perintah dijalankan untuk memproses data.
3. Jika hasil akhirnya TRUE maka transaksi valid.

## Kenapa Script Dibuat Terbatas?

Bitcoin Script sengaja dibatasi agar aman.

| Sifat | Artinya |
|------|---------|
Stateless | Tidak punya ingatan transaksi lain |
Tanpa Loop | Tidak bisa berjalan tanpa henti |
Deterministik | Semua node mendapat hasil yang sama |
Sederhana | Mudah diverifikasi oleh seluruh jaringan |

Bitcoin bukan komputer serbaguna.  
Bitcoin adalah mesin verifikasi global.

---

# **Bagian 2: Dua Komponen Dalam Transaksi**

Setiap transaksi memiliki dua bagian script yang saling berpasangan.

## ScriptPubKey (Locking Script)

Dibuat oleh pengirim.  
Berisi aturan tentang siapa yang boleh memakai koin ini di masa depan.

## ScriptSig (Unlocking Script)

Dibuat oleh pihak yang ingin membelanjakan koin.  
Berisi bukti bahwa dia memenuhi aturan tadi.

Biasanya berupa tanda tangan digital dan public key.  
Pada transaksi modern, data ini bisa berada di bagian Witness.

## Cara Node Memverifikasi

Node akan menjalankan:

    ScriptSig + ScriptPubKey

Kedua bagian digabung lalu dieksekusi.

Jika hasil akhirnya TRUE, transaksi diterima.  
Jika FALSE, transaksi ditolak.

---

# **Bagian 3: Address Itu Sebenarnya Bentuk Script**

Yang sering disebut sebagai:
- alamat Legacy
- alamat SegWit
- alamat Taproot

Sebenarnya hanyalah cara berbeda menulis ScriptPubKey.

Bukan sistem baru.  
Bukan blockchain baru.  
Hanya format penguncian yang berevolusi.

---

# **Bagian 4: Evolusi Cara Mengunci Bitcoin**

Semua tipe address adalah perkembangan desain script untuk tujuan efisiensi, keamanan, dan fleksibilitas.

## P2PK (Pay to Public Key)

Script:

    <PublicKey> OP_CHECKSIG

Artinya koin dikunci langsung ke public key.

Kelebihan:
- Sangat sederhana.

Kekurangan:
- Public key langsung terlihat.
- Tidak efisien.
- Privasi rendah.

## P2PKH (Pay to Public Key Hash)

Alamat:

    1xxxxxxxxxxxxxxxx

Script:

    OP_DUP OP_HASH160 <PubKeyHash> OP_EQUALVERIFY OP_CHECKSIG

Yang disimpan hanya hash public key.  
Public key baru muncul saat koin dibelanjakan.

Kelebihan:
- Lebih hemat ruang.
- Lebih aman.
- Lebih privat.

## P2SH (Pay to Script Hash)

Alamat:

    3xxxxxxxxxxxxxxxx

Digunakan untuk multisig dan aturan kompleks.

Bitcoin hanya menyimpan hash dari script.  
Script asli ditampilkan saat spending.

Kelebihan:
- Fleksibel.
- Cocok untuk shared custody.

## SegWit (P2WPKH dan P2WSH)

Alamat:

    bc1q...

SegWit memindahkan data tanda tangan ke bagian terpisah bernama Witness.

Tujuannya:
- Mengurangi ukuran transaksi.
- Menghilangkan masalah malleability.
- Membuat fee lebih murah.

## Taproot (P2TR)

Alamat:

    bc1p...

Menggabungkan signature, script, dan multisig dalam satu struktur berbasis Schnorr.

Kelebihan:
- Transaksi kompleks terlihat seperti transaksi biasa.
- Privasi meningkat.
- Lebih efisien.
- Lebih scalable.

---

# **Bagian 5: Yang Tidak Pernah Berubah**

Sejak awal Bitcoin, yang berubah hanyalah cara menulis ScriptPubKey.

Yang tidak berubah:
- Model UTXO
- Mesin Script
- Validasi TRUE atau FALSE
- Tidak ada akun
- Tidak ada saldo global

---

## Kesimpulan

Bitcoin bukan sistem akun.  
Bitcoin bukan sistem saldo.  
Bitcoin bukan sistem kirim uang.

Bitcoin adalah sistem pembuktian hak menggunakan UTXO.

Bitcoin Script adalah bahasa yang mendefinisikan hak tersebut.

Semua jenis address hanyalah variasi cara menulis kondisi, bukan perubahan sistem.

Jika ingin memahami Bitcoin di level protokol, cukup ingat:

    Bitcoin = UTXO + Script + Verifikasi Deterministik

Sisanya hanyalah variasi implementasi.
