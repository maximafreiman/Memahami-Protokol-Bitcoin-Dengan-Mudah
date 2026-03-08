# The Byzantine General Problem, dan Bagaimana Konsensus Bitcoin Menjadi Solusi


Dalam dunia komputer terdistribusi (seperti jaringan Bitcoin yang isinya ribuan komputer asing), ada satu masalah klasik yang sangat ditakuti, namanya **Byzantine Generals Problem** (Masalah Jenderal Bizantium).

Analogi Jenderal Bizantium kurang lebih seperti ini:

Bayangkan ada beberapa pasukan jenderal yang mengepung sebuah kota musuh yang kuat.

Kondisinya: Pasukan ini tersebar di berbagai sisi kota. Mereka hanya bisa menang kalau semua jenderal menyerang bersamaan. Kalau ada yang menyerang dan ada yang mundur, pasukan yang menyerang akan dihancurkan.

Masalahnya: Mereka hanya bisa berkomunikasi lewat kurir yang membawa pesan (seperti data internet).

Risikonya: 
1.  Kurir bisa ditangkap musuh atau pesannya diganti.
2.  Ada jenderal pengkhianat di antara mereka. Jenderal pengkhianat ini bisa mengirim pesan "Serang!" ke Jenderal A, tapi mengirim pesan "Mundur!" ke Jenderal B.

Hasilnya? Jenderal A menyerang sendirian dan kalah total. Konsensus gagal karena ada data palsu yang disebarkan oleh pengkhianat.

--

**Hubungannya dengan Bitcoin**

Di dalam jaringan Bitcoin, setiap komputer (node) adalah "Jenderal".

Pesannya adalah: "Si Andi mengirim 1 BTC ke Budi."

Pengkhianatnya adalah: Hacker atau orang yang ingin melakukan double spending (menggunakan uang yang sama dua kali).

Bagaimana ribuan komputer yang tidak saling kenal ini bisa yakin bahwa pesan yang mereka terima adalah pesan yang jujur dan disepakati oleh semua jenderal lainnya?

Solusi Jenius Bitcoin: Proof of Work (PoW)

Satoshi Nakamoto (pencipta Bitcoin) menyelesaikan masalah jenderal ini bukan dengan "saling percaya", tapi dengan "biaya yang mahal".

Dalam analogi jenderal tadi, PoW ibarat mewajibkan kurir untuk mengerjakan tugas yang sangat sulit dan memakan waktu lama (misalnya menyusun teka-teki rumit) sebelum bisa menyampaikan pesan.

Jika jenderal pengkhianat ingin mengirim pesan palsu yang berbeda-beda ke banyak jenderal, dia harus mengeluarkan energi dan usaha yang sangat besar (hampir mustahil dilakukan sendirian). Tentu saja. Masing-masing jenderal punya kurirnya masing-masing. Dan setiap mereka ingin mengantar pesan harus mengeluarkan effort yang besar. Bayangkan jika 99 jenderal dapat pesan yang sama, yang 1 dapat pesan yang berbeda. Maka pilihan untuk 1 jenderal ini ada 2: ikuti kesepakatan yang sudah ada, atau cari jalurnya sendiri.

Dan yang terpenting juga, jenderal lain bisa dengan mudah memverifikasi apakah "pekerjaan" kurir itu benar atau tidak.

--

**Mengapa Perbankan Justru Mengadopsi Model yang Mirip dengan Byzantine Generals Problem**

Berbeda dengan Bitcoin yang mencoba menyelesaikan masalah Byzantine, sistem perbankan modern justru menerima dan mengelola masalah tersebut dengan cara lain, yaitu melalui sentralisasi dan kepercayaan institusional.

Dalam sistem perbankan, para "jenderal" tidak benar-benar independen seperti di jaringan Bitcoin. Mereka berada di bawah struktur yang jelas: bank komersial, bank sentral, lembaga kliring, regulator, dan sistem hukum negara.

Artinya, jika ada pesan transaksi seperti:

"Si Andi mengirim uang ke Budi"

maka validitas pesan tersebut tidak ditentukan oleh konsensus ribuan komputer independen, tetapi oleh otoritas pusat yang dipercaya.

Ada beberapa mekanisme yang membuat sistem ini bekerja:

- Otoritas pusat (bank atau lembaga kliring)
Bank bertindak sebagai sumber kebenaran. Jika terjadi konflik data, catatan bank dianggap benar.

- Identitas yang diketahui (KYC)
Semua pihak dalam sistem perbankan memiliki identitas yang diverifikasi. Ini mengurangi kemungkinan "pengkhianat anonim".

- Audit dan regulasi
Bank diawasi oleh regulator dan auditor. Jika ada manipulasi data, ada konsekuensi hukum.

- Sistem pembatalan transaksi
Jika terjadi kesalahan atau penipuan, transaksi dapat dibatalkan melalui proses administratif atau hukum.

Dengan kata lain, perbankan tidak mencoba membuat sistem yang tahan terhadap pengkhianat secara matematis, seperti yang dilakukan Bitcoin.

Sebaliknya, mereka membangun sistem yang bergantung pada kepercayaan terhadap institusi, hukum, dan otoritas pusat untuk menangani konflik.

Pendekatan ini jauh lebih efisien secara energi dan kecepatan transaksi, tetapi memiliki satu konsekuensi besar:

Jika otoritas pusat gagal, disusupi, atau korup, maka seluruh sistem bisa ikut terdampak, karena semua pihak bergantung pada sumber kebenaran yang sama.

Bitcoin mencoba mengambil jalan yang berbeda: bukan dengan mempercayai institusi, tetapi dengan membuat sistem di mana bahkan jika sebagian peserta berperilaku jahat, jaringan tetap bisa mencapai konsensus yang benar.



