# Partially Signed Bitcoin Transaction (PSBT)

PSBT (Partially Signed Bitcoin Transaction) adalah sebuah format file standar yang memungkinkan transaksi Bitcoin "setengah jadi" dipindahkan antar perangkat dengan aman tanpa perlu menyentuh kunci pribadi (private key). Bayangkan PSBT seperti sebuah formulir cek digital yang sudah diisi nominal dan tujuannya, namun masih membutuhkan satu atau lebih tanda tangan basah agar bisa dicairkan ke bank; format ini dirancang agar dompet yang terhubung ke internet bisa menyiapkan transaksi, sementara perangkat yang offline (cold storage) bisa memeriksa dan menandatanganinya secara terpisah.

## Kenapa PSBT Penting? Dan Apa Fungsinya?

Gemini berkata
Secara sederhana, **PSBT (Partially Signed Bitcoin Transaction)** penting karena ia adalah "bahasa universal" yang memungkinkan berbagai perangkat Bitcoin saling berkomunikasi tanpa membocorkan rahasia paling penting, yaitu Private Key kamu.

Berikut adalah alasan mengapa PSBT penting dan apa fungsinya dalam penggunaan sehari-hari:

- Keamanan (Air-gap): Memungkinkan kamu menandatangani transaksi di perangkat yang tidak pernah terkoneksi internet, sehingga kunci rahasia tetap aman dari peretas.

- Bahasa Universal: Menjadi standar agar berbagai merek dompet dan aplikasi (misal: Sparrow Wallet ke SeedSigner) bisa saling nyambung tanpa kendala teknis.

- Kerja Sama (Multisig): Memudahkan proses pengumpulan tanda tangan dari beberapa orang atau perangkat berbeda untuk satu transaksi yang sama.

- Cek Ulang (Verifikasi): Menyediakan informasi lengkap bagi perangkat offline untuk memastikan jumlah koin dan biaya transaksi sudah benar sebelum disetujui.

- Efisiensi Data: Membawa semua data yang dibutuhkan (metadata) dalam satu file kecil sehingga mudah dipindahkan lewat kode QR atau kartu SD.

## Gimana Cara Kerja PSBT?

Cara kerja PSBT bisa dibagi menjadi 4 langkah sederhana seperti alur "surat persetujuan" di kantor:

1. Pembuatan (Draft): Dompet yang online (Watch-only wallet) membuat draf transaksi. Di sini ditentukan siapa penerimanya dan berapa biayanya, tapi transaksi ini belum sah karena belum ada tanda tangan.

2. Pemindahan (Transfer): File draf (PSBT) dipindahkan ke perangkat yang offline. Kamu bisa memindahkannya lewat MicroSD atau cukup scan QR Code.

3. Penandatanganan (Sign): Perangkat offline (seperti hardware wallet) membuka file tersebut, memeriksa detailnya, lalu memberikan tanda tangan digital menggunakan kunci rahasia yang tersimpan aman di dalamnya.

4. Penyiaran (Broadcast): File yang sudah ditandatangani dikirim balik ke dompet online. Dompet online kemudian menyiarkannya ke jaringan Bitcoin agar transaksi diproses secara resmi.

Singkatnya: Siapkan di online, Tandatangani di offline, lalu Kirim balik ke online untuk disiarkan.

--

**Karena PSBT ini sifatnya full praktek, bisa lihat contoh video ini:**

[Video Tutorial PSBT Simpel](https://www.youtube.com/watch?v=0qndGQL1p7o)   <-------

Di video tersebut, simulasinya menggunakan hardware wallet Cobo Vault. Dan perlu dicatat, bisa memakai hard wallet lainnya. Sama saja.

Fungsinya: Ini mencegah virus di komputer kamu menipu perangkat offline. PSBT memastikan perangkat tahu mana alamat tujuan yang asli dan mana alamat kembalian milikmu sendiri, sehingga tidak ada dana yang "nyasar" ke dompet peretas.
