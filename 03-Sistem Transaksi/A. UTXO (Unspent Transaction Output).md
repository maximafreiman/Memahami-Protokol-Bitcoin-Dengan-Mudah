UTXO (Unspent Transaction Output), Alasan Kenapa Transaksi pada Bitcoin Tidak Bisa Dimanipulasi
--

Bayangkan Bitcoin bukan sebagai deretan angka di buku tabungan, melainkan seperti dompet berisi tumpukan uang tunai yang kita kenal dengan istilah UTXO (Unspent Transaction Output). Setiap keping Bitcoin yang kamu miliki sebenarnya adalah "sisa kembalian" dari transaksi sebelumnya yang masih sah untuk dibelanjakan. Menariknya, sistem ini membuat transaksi Bitcoin hampir mustahil dimanipulasi; karena setiap unitnya punya "jejak digital" yang jelas, kamu tidak bisa sekadar mengubah angka saldo atau memakai uang yang sama dua kali. Jika kamu mencoba mengakali sistem, ribuan komputer di seluruh dunia akan langsung mendeteksi bahwa kepingan tersebut tidak valid, membuat keamanan Bitcoin tetap solid tanpa perlu campur tangan bank sentral sama sekali.

---

Aku akan coba simplifikasi dengan sederhana. Kita bisa gambarkan UTXO ini seperti sebuah... kupon. Ya, bitcoiner kebanyakan akan menggambarkan UTXO dengan pendekatan yang lain. Seperti koin emas, uang cash, dan medium penggambaran lainnya. Well, itu sudah tepat. Dan disini, aku ingin menggambarkan UTXO secara konseptual dengan pendekatan "kupon emas yang langka" tapi bisa dipecah secara nilai untuk efisiensi transaksi. 

Bentukannya kurang lebih seperti ini:

![1](https://github.com/user-attachments/assets/11897249-860c-4851-a6e0-312adb297d8d)

Sekarang bayangkan, kamu punya 3 UTXO yang sudah tercatat di blockhain

![2](https://github.com/user-attachments/assets/cdf77f2f-22ce-4c19-9562-a83c981b3371)

Ceritanya, kamu mau kirim 1 BTC. Karena diantara UTXO yang kamu punya ada yang sudah pas 1.0 BTC, maka wallet akan pilih UTXO dengan jumlah yang pas, nggak perlu pilih UTXO yang lain.

Sebelum kamu mau melakukan transaksi dengan mengirim UTXO ini ke temanmu, wallet akan 'bikin' struktur transaksi dulu.

![3](https://github.com/user-attachments/assets/39c3b160-3e27-4eb0-9997-527c1b141712)

- Input: Nilai BTC kamu (1.0 BTC)
- Output 1: Jumlah yang akan dikirim ke temen kamu (0.8 BTC)
- Output 2: Jumlah kembalian yang akan kamu terima nanti (0.199 BTC)
- Fee: Ongkos kirim ke miner (0.001 BTC)

Setelah struktur transaksi sudah diketahui oleh wallet, UTXO tidak langsung terkirim. Tetapi melewati proses pembuatan tanda tangan (signature) sebagai pengesahan kalau kamu akan mengirim UTXO ini ke temanmu, dan juga melewati proses verifikasi.

![4](https://github.com/user-attachments/assets/e03b321a-415f-4bac-93be-f313922ec5c0)

Setelah diverifikasi semuanya oleh ribuan node secara global, baru proses transaksi dimulai..

![5](https://github.com/user-attachments/assets/0844349b-93b8-4c89-894a-69eaab2546b2)

Nah sekarang, kamu dan temanmu udah terima UTXO yang baru, tapi sebelum itu, node memverifikasi lagi UTXO yang baru ini.

![6](https://github.com/user-attachments/assets/3a7de614-58d4-4b65-8881-3aabd6df1ada)

And done. Jumlah UTXO-mu yang baru sudah resmi masuk di dalam blockchain.

--

Njelimet? Sepertinya iya. UTXO model lebih kompleks daripada Account Based Model yang biasa dipakai di m-banking atau shitcoins. Tapi inilah keistimewaan Bitcoin. Bitcoin tidak akan membiarkan data transaksi kamu dimanipulasi. Sistem UTXO ini sudah bagian dalam konsensus Bitcoin dan tidak akan berubah.
