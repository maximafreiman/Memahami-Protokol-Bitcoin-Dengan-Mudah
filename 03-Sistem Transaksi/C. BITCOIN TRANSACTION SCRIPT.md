# Bitcoin Transaction Script — Penjelasan Sederhana dari Nol

## Kenapa Harus Bahas "Script"?

Banyak orang mengira Bitcoin itu seperti:
- kirim saldo  
- dari akun A ke akun B  

Padahal Bitcoin tidak punya akun.

Di dalam protokol Bitcoin, yang ada hanyalah:
> UTXO (koin) yang dikunci dengan aturan.

Aturan itulah yang disebut Bitcoin Script.

---

## Konsep Paling Penting

Bitcoin tidak pernah mengirim ke “alamat”.

Bitcoin sebenarnya:

    Mengunci koin → dengan sebuah kondisi matematika.

Dan untuk membukanya:

    Kita harus membuktikan bahwa syarat itu terpenuhi.

Jadi Bitcoin bukan sistem kirim uang.

Bitcoin adalah:
> Sistem kunci dan buka kunci.

---

# Bagian 1 — Apa Itu Bitcoin Script?

## Definisi

Bitcoin Script adalah bahasa instruksi sederhana  
yang dipakai untuk menentukan:

> Siapa yang boleh memakai koin ini?

Script bukan untuk membuat aplikasi.  
Script hanya untuk memverifikasi.

---

## Cara Kerjanya: Stack-Based

Script bekerja dengan sistem tumpukan data.

Urutannya:
1. Data dimasukkan ke stack.  
2. Operator memproses data.  
3. Jika hasil akhir TRUE maka transaksi valid.

---

## Script Sengaja Dibuat Terbatas

Bitcoin Script memiliki batasan berikut:

| Sifat | Artinya |
|------|---------|
Stateless | Tidak punya ingatan transaksi lain |
Tanpa Loop | Tidak bisa berjalan tanpa henti |
Deterministik | Semua node mendapat hasil sama |
Sederhana | Aman untuk jaringan global |

Tujuannya:
Agar tidak bisa dipakai menyerang jaringan.

Bitcoin bukan komputer umum.  
Bitcoin adalah mesin verifikasi.

---

# Bagian 2 — Dua Komponen Dalam Transaksi

Setiap transaksi selalu memiliki dua bagian script.

## ScriptPubKey (Locking Script)

Dibuat oleh pengirim.

Berisi aturan:
> Apa syarat agar koin ini boleh dipakai lagi?

---

## ScriptSig (Unlocking Script)

Dibuat oleh pihak yang ingin membelanjakan koin.

Berisi bukti:
> Bahwa dia memenuhi syarat tadi.

Biasanya berupa:
- tanda tangan digital  
- public key  

Pada transaksi modern, data ini bisa berada di Witness.

---

## Cara Node Memverifikasi

Node menjalankan:

    ScriptSig + ScriptPubKey

Script digabung lalu dieksekusi.

Jika hasil akhir TRUE:
Transaksi sah.

Jika FALSE:
Transaksi ditolak.

---

# Bagian 3 — Address Itu Hanya Representasi Script

Yang sering disebut:
- alamat Legacy  
- alamat SegWit  
- alamat Taproot  

Sebenarnya hanyalah cara berbeda menulis ScriptPubKey.

Bukan sistem baru.  
Bukan blockchain baru.  
Hanya format penguncian yang berbeda.

---

# Bagian 4 — Evolusi Cara Mengunci Bitcoin

Semua tipe address adalah evolusi desain script.

---

## P2PK — Pay to Public Key

Bentuk paling awal.

Script:

    <PublicKey> OP_CHECKSIG

Artinya:
Koin dikunci langsung ke public key.

Kelebihan:
- Sangat sederhana.

Kekurangan:
- Public key langsung terlihat.
- Tidak efisien.
- Privasi rendah.

---

## P2PKH — Pay to Public Key Hash

Menghasilkan alamat:

    1xxxxxxxxxxxxxxxx

Script:

    OP_DUP OP_HASH160 <PubKeyHash> OP_EQUALVERIFY OP_CHECKSIG

Artinya:
Yang disimpan hanya hash public key.

Public key baru muncul saat spending.

Kelebihan:
- Lebih hemat ruang.
- Lebih aman.
- Lebih privat.

Ini menjadi standar lama Bitcoin.

---

## P2SH — Pay to Script Hash

Alamat:

    3xxxxxxxxxxxxxxxx

Digunakan untuk:
- multisig
- aturan kompleks

Bitcoin hanya menyimpan hash script.
Script asli ditampilkan saat dibelanjakan.

Kelebihan:
- Fleksibel.
- Mendukung berbagai skenario custody.

---

## SegWit — P2WPKH & P2WSH

Alamat:

    bc1q...

SegWit memindahkan data tanda tangan ke bagian terpisah:
Witness.

Tujuan:
- Mengurangi ukuran transaksi.
- Menghilangkan malleability.
- Fee lebih murah.

---

## Taproot — P2TR

Alamat:

    bc1p...

Desain paling modern.

Menggabungkan:
- signature
- script
- multisig

Menggunakan Schnorr signature.

Kelebihan:
- Transaksi kompleks terlihat seperti transaksi biasa.
- Privasi meningkat.
- Lebih efisien.
- Lebih scalable.

---

# Ringkasan Semua Tipe Script

| Tipe | Prefix Address | Fokus | Kelebihan | Kekurangan |
|------|----------------|-------|-----------|------------|
P2PK | (tidak umum) | Langsung ke public key | Sederhana | Tidak efisien |
P2PKH | 1 | Standar lama | Stabil & aman | Kurang efisien |
P2SH | 3 | Script kompleks | Fleksibel | Data lebih besar |
P2WPKH | bc1q | SegWit user | Fee lebih murah | Butuh wallet modern |
P2WSH | bc1q | SegWit script | Efisien multisig | Lebih teknis |
P2TR | bc1p | Taproot | Privasi & efisiensi | Adopsi bertahap |

---

# Bagian 5 — Yang Tidak Pernah Berubah

Sejak awal Bitcoin:

Yang berubah:
Cara menulis ScriptPubKey.

Yang tidak berubah:
- Model UTXO  
- Mesin Script  
- Validasi TRUE/FALSE  
- Tidak ada akun  
- Tidak ada saldo global  

---

# Kesimpulan

Bitcoin bukan:
- sistem akun
- sistem saldo
- sistem kirim uang

Bitcoin adalah:
> Sistem pembuktian hak menggunakan UTXO.

Bitcoin Script adalah:
> Bahasa untuk mendefinisikan hak tersebut.

Semua jenis address hanyalah variasi cara menulis kondisi.
Bukan perubahan sistem.

---

Jika ingin memahami Bitcoin di level protokol, cukup ingat:

    Bitcoin = UTXO + Script + Verifikasi Deterministik

Sisanya hanyalah variasi implementasi.


