### Memahami Protokol Bitcoin Dengan Mudah
Lindungi Uang dan Nilaimu dengan Bitcoin. Cocok untuk Semuanya 

---

Bitcoin Simplicity (judul asli, ditulis oleh penulis yang sama) adalah proyek edukasi Bitcoin yang dikerjakan secara solo,
membahas semuanya mulai dari dasar hingga tingkat pengembang,
dirancang agar siapa pun, termasuk pembaca non-teknis,
dapat memahami Bitcoin secara utuh.

Pendekatannya sederhana:
Bitcoin dijelaskan berdasarkan aturan protokolnya,
tanpa jargon yang tidak perlu dan tanpa mencampurkannya dengan “kripto”.



## Scope

- Fundamental Bitcoin 
- Wallets dan Transaksi  
- Node dan Verifikasi
- Bitcoin protocol dasar 
- Bitcoin development  

Materinya disusun secara bertahap dan dapat diverifikasi secara mandiri.
---

# The Sovereign Protocoler Curriculum
> **Status:** Bitcoin is Money. Everything else is a database. 
> **Goal:** Understanding the immutable laws of the 21 Million.

| No | Tema | Topik Utama | Militant Insight (The "Why") |
|:---|:---|:---|:---|
| 1 | **Fundamental Bitcoin** | Whitepaper, Sejarah Cypherpunk, Austrian Economics basics. | Memahami bahwa Bitcoin adalah solusi atas kegagalan sistem uang fiat (Central Banking). |
| 2 | **Konsensus** | Byzantine Generals Problem, Proof of Work (PoW), Fork Rules, 21 Million Cap. | Konsensus bukan demokrasi; konsensus adalah validasi matematis yang tidak bisa disuap. |
| 3 | **Transaksi** | UTXO Model, Script (Locking/Unlocking), Fee Market, Mempool. | UTXO adalah kedaulatan; setiap satoshi harus memiliki silsilah yang jelas dan valid. |
| 4 | **Block (Current Focus)** | Block Header, Coinbase Tx, Merkle Tree, Block Subsidy vs Fees, Reorgs. | Membedah struktur blok sebagai detak jantung ekonomi yang tidak bisa dimanipulasi. |
| 5 | **Kriptografi** | SHA-256, ECC (secp256k1), ECDSA vs Schnorr, Taproot (BIP341). | Matematika adalah satu-satunya hukum yang tidak mengenal batasan negara atau sensor. |
| 6 | **Mining** | Difficulty Adjustment, Poisson Distribution, Stratum V2, 51% Attack Vectors. | Memastikan keamanan fisik jaringan tetap terdesentralisasi dan tahan terhadap paksaan negara. |
| 7 | **Node & P2P** | Full Node vs Pruned, IBD (Initial Block Download), UASF (BIP148), Peer Discovery. | "Don't Trust, Verify." Menjalankan node sendiri adalah satu-satunya cara untuk merdeka. |
| 8 | **Layer 2 (Scaling)** | Lightning Network (HTLCs), Ark Protocol, RGB, Client-side Validation. | Melakukan scaling tanpa mengorbankan integritas Layer 1 yang suci. |
| 9 | **Privacy & Fungibility** | CoinJoin, Tapscript, Output Billability, Preventing Chain Analysis. | Privasi bukan untuk menyembunyikan kejahatan, tapi untuk melindungi kebebasan individu. |
| 10 | **Bitcoin Software** | Bitcoin Core vs Knots, GPG Verification, Reproducible Builds, Gitian. | Memastikan kode yang dijalankan adalah kode yang benar-benar disepakati oleh komunitas. |
| 11 | **Protocol Governance** | BIP Process (BIP 8/9), Soft Fork vs Hard Fork, Social Consensus. | Memahami bagaimana aturan berubah tanpa menghancurkan konsensus yang sudah ada. |

---

## Technical Deep Dive: Block (Nomor 4)
*Saat ini lu di sini, pastikan lu paham poin-poin krusial ini:*

* **Block Header (80 Bytes):** Kenapa cuma 80 bytes ini yang menentukan validitas seluruh transaksi di dalamnya?
* **Coinbase Transaction:** Satu-satunya transaksi yang diizinkan "mencetak" uang dari hampa (subsidi), tapi terikat aturan halving yang ketat.
* **Merkle Tree:** Cara elegan untuk membuktikan sebuah transaksi ada dalam blok tanpa harus mendownload seluruh data blok (SPV Proof).
* **Reorg (Reorganization):** Apa yang terjadi kalau dua blok ditemukan di waktu yang hampir bersamaan? Memahami "Longest Chain" (Most Work) Rule.






---

## License

Semua konten ini berlisensi: 
**Mozilla Public License 2.0**.




