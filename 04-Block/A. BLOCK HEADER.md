Pengertian Block & Block Header
---

### Block Anatomy

Kita akan pakai analogi brankas disini. Block Bitcoin adalah sebuah brankas digital yang transparan berisi tumpukan catatan transaksi yang terkunci rapat dengan 2 kombinasi keamanan. Yaitu lubang kunci dengan kode yang disebut block hash, dan sebuah gembok dengan label yang berasal dari kode block hash sebelumnya, disebut prevblockhash.


Visualnya seperti ini kira-kira, hanya untuk translasi ke bahasa visual manusia, tidak dalam arti harfiah sebenarnya. Mengingat Bitcoin ini digital:

<img width="1920" height="1080" alt="1" src="https://github.com/user-attachments/assets/7eff9734-9dcc-4846-9fe5-462b45885275" />
---

List transaksi para users Bitcoin akan dimasukkan ke "brankas" (block) tersebut

<img width="1920" height="1080" alt="2" src="https://github.com/user-attachments/assets/5c49f4c7-bbfb-4a2a-9dc7-d5d683786c90" />
---

Demikian pula dengan transaksi-transaksi sebelumnya. Karena ada kombinasi blockhash dan prevblockhash inilah, yang menyebabkan terbentuknya blockchain (atau kalau komunitas bitcoin maxi bilang sebagai timechain).

<img width="1920" height="1080" alt="3(1)" src="https://github.com/user-attachments/assets/cad69cf1-8ab9-45a5-ab9e-5eb08a78b087" />

---

### Block Header

Simpelnya, block header adala identitas dari brankas "block" itu tadi. Mari kita bahas.

**1. Version: Nomor Seri Brankas**

Ini adalah angka yang memberi tahu jaringan aturan main mana yang diikuti oleh brankas ini. Jika ada pembaruan sistem (seperti ganti jenis baja atau jenis kunci baru), angka versi ini akan berubah agar semua orang tahu standar apa yang digunakan.


**2. PrevBlockHash: Gembok dengan Nomor Kode Hash dari Brankas Sebelumnya**

Inilah yang menghubungkan satu brankas ke brankas sebelumnya. Header ini menyimpan hash dari brankas yang dibuat tepat sebelum ini. Jika ada orang jahat mencoba menukar brankas di masa lalu, gembok ini tidak akan pas lagi, dan seluruh barisan brankas setelahnya akan dianggap rusak/palsu.

**3. Merkle Root: Ringkasan Isi Brankas**

Bayangkan di dalam brankas ada ribuan surat (transaksi). Alih-alih mencatat semua judul surat di plat pintu, kita menggunakan metode matematika untuk meringkas ribuan surat itu menjadi satu kode unik. Jika ada satu huruf saja yang diubah di dalam salah satu surat di dalam brankas, "Foto Rontgen" ini akan berubah total.

**4. Timestamp: Stempel Waktu**

Mencatat kapan tepatnya brankas ini selesai dirakit dan dikunci. Ini penting agar tidak ada yang bisa memasukkan brankas "dari masa depan" atau mengacak-acak urutan kejadian.

**5. Difficulty Target: Tingkat Kerumitan Kombinasi Kunci.**

Jaringan menentukan seberapa sulit gembok ini harus dibuat. Secara teknis, ini adalah angka target yang harus dipenuhi oleh hash blok. Semakin banyak penambang (orang yang mencoba mengunci brankas), sistem akan otomatis membuat kombinasi kuncinya jadi lebih sulit agar brankas tidak dibuat terlalu cepat.

**6. Nonce: Angka yang Terus Diputar pada Roda Kombinasi.**

Inilah variabel yang dicari-cari oleh pembuat brankas (istilah resminya adalah miner alias penambang block). Karena semua data di atas (Version, PrevHash, dll) sudah tetap, penambang hanya bisa mengubah satu hal: Nonce. Mereka mencoba memasukkan angka 1, 2, 3... sampai jutaan kali, hingga seluruh data di header menghasilkan hash (lubang kunci) yang sesuai dengan Difficulty Target. Begitu angkanya ketemu, "KLIK!", brankas terkunci dan sah.







