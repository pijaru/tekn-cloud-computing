## Praktikum Teknologi Cloud Computing - Minggu 06

### Tipe DBMS
Ada dua tipe utama sistem manajemen basis data (DBMS), yaitu SQL dan NoSQL. SQL (Structured Query Language) dan NoSQL (Not Only SQL) memiliki perbedaan pada cara penyimpanan dan pengambilan data.

SQL adalah tipe DBMS yang paling umum digunakan. SQL menggunakan bahasa query SQL untuk menyimpan dan mengambil data dari tabel yang terstruktur. SQL mendukung schema yang terdefinisi dengan jelas, yang berarti setiap tabel harus memiliki struktur yang sama dan tipe data yang sama untuk setiap kolom. Contoh dari DBMS SQL antara lain MySQL, Oracle, Microsoft SQL Server, dan PostgreSQL.

NoSQL adalah tipe DBMS yang digunakan untuk menyimpan data yang tidak terstruktur. NoSQL tidak menggunakan schema yang terdefinisi dengan jelas, sehingga lebih fleksibel dalam hal penyimpanan data. NoSQL dapat menyimpan data dalam format yang berbeda-beda seperti dokumen, key-value pairs, graph, atau lainnya. Contoh dari DBMS NoSQL antara lain MongoDB, Cassandra, Redis, dan Amazon DynamoDB.

Kedua tipe DBMS memiliki kelebihan dan kekurangan masing-masing. SQL memiliki kemampuan untuk menyimpan data terstruktur secara konsisten dan memiliki dukungan yang luas dari berbagai aplikasi dan platform. Sementara NoSQL memiliki kemampuan untuk menyimpan data yang tidak terstruktur dengan skala yang lebih besar dan memiliki performa yang lebih cepat.

Pilihan antara SQL dan NoSQL tergantung pada kebutuhan aplikasi Anda. Jika Anda memerlukan kemampuan untuk menyimpan data terstruktur dan mengakses data dengan bahasa SQL, maka SQL mungkin menjadi pilihan yang lebih baik. Namun, jika Anda memerlukan kemampuan untuk menyimpan data yang tidak terstruktur dan skala yang lebih besar, NoSQL bisa menjadi pilihan yang lebih baik.

### Data as a Service (DaaS) 
Data as a Service (DaaS) adalah model bisnis yang memungkinkan pengguna untuk mengakses dan menggunakan data secara on-demand melalui internet. Dalam model ini, penyedia layanan menyediakan akses ke data yang dikelola dan di-hosting di server mereka, dan pengguna dapat mengakses data tersebut dengan membayar biaya langganan atau berdasarkan penggunaan.

DaaS adalah konsep yang relatif baru dan berkembang seiring dengan perkembangan teknologi cloud computing. DaaS memungkinkan pengguna untuk mengakses data tanpa harus memiliki infrastruktur IT sendiri atau mengelola data secara internal. Dengan DaaS, pengguna dapat mengakses data dari berbagai sumber, termasuk data publik, data pribadi, atau data industri yang relevan.

Keuntungan dari DaaS adalah:

Akses ke data yang luas - DaaS memungkinkan pengguna untuk mengakses berbagai sumber data dari satu titik akses.

Efisiensi Biaya - DaaS mengurangi biaya pengelolaan infrastruktur IT, karena pengguna tidak perlu membeli atau memelihara hardware dan software untuk mengelola data mereka.

Skalabilitas - DaaS memungkinkan pengguna untuk mengelola data dengan skalabilitas yang lebih mudah, karena infrastruktur dan kapasitas server disediakan oleh penyedia layanan.

Keamanan - DaaS dapat memberikan tingkat keamanan data yang lebih tinggi karena penyedia layanan umumnya menggunakan standar keamanan yang tinggi untuk melindungi data pengguna.

Namun, ada beberapa kelemahan dari DaaS, antara lain kekhawatiran keamanan data, ketergantungan pada penyedia layanan, dan masalah privasi data.

Dalam kesimpulannya, DaaS memberikan banyak keuntungan bagi pengguna yang ingin mengakses dan menggunakan data secara efisien dan hemat biaya. Namun, keputusan untuk menggunakan model DaaS harus dipertimbangkan dengan cermat untuk memastikan bahwa data pengguna aman dan privasi data terjaga.

### Cloud database
Cloud database adalah jenis database yang di-hosting di cloud. Ini berarti data disimpan di infrastruktur cloud dan diakses melalui internet. Cloud database memungkinkan pengguna untuk mengakses data mereka dari mana saja dan kapan saja, dengan memanfaatkan kecepatan, skalabilitas, dan fleksibilitas yang disediakan oleh cloud.

Ada beberapa jenis cloud database, termasuk:

Cloud Relational Database: Database relasional yang di-hosting di cloud, seperti MySQL, Oracle, atau PostgreSQL. Cloud relational database memungkinkan pengguna untuk menyimpan data terstruktur dalam tabel yang berhubungan satu sama lain.

Cloud NoSQL Database: Database NoSQL seperti MongoDB atau Cassandra yang di-hosting di cloud. Cloud NoSQL database memungkinkan pengguna untuk menyimpan data yang tidak terstruktur, seperti dokumen atau grafik, dan mengakses data dengan cepat dan skalabilitas yang lebih besar.

Cloud Data Warehouse: Warehouse data yang di-hosting di cloud, seperti Amazon Redshift atau Google BigQuery. Cloud data warehouse memungkinkan pengguna untuk menyimpan, mengolah, dan menganalisis data secara efisien dalam skala besar.

Keuntungan dari menggunakan cloud database adalah:

Skalabilitas: Cloud database memungkinkan pengguna untuk menambah atau mengurangi kapasitas penyimpanan sesuai kebutuhan, tanpa harus membeli infrastruktur hardware baru.

Ketersediaan: Cloud database menyediakan tingkat ketersediaan yang tinggi, karena data disimpan di beberapa server yang terdistribusi di berbagai wilayah geografis.

Keamanan: Cloud database dilindungi oleh lapisan keamanan yang lebih tinggi dan lebih kuat, sehingga memberikan perlindungan yang lebih baik terhadap serangan dan ancaman keamanan.

Biaya: Pengguna hanya membayar biaya berdasarkan penggunaan, sehingga mereka dapat menghemat biaya operasional yang terkait dengan penyimpanan data di infrastruktur internal.

Namun, ada juga beberapa kelemahan dari cloud database, seperti kekhawatiran keamanan dan privasi data, ketergantungan pada penyedia layanan, dan kemampuan akses data yang tergantung pada ketersediaan jaringan internet.

Secara keseluruhan, cloud database menyediakan solusi efektif dan efisien untuk pengelolaan data dalam skala besar, namun keputusan untuk menggunakan cloud database harus dipertimbangkan dengan cermat, terutama dalam hal keamanan dan privasi data.

### Latihan
- Install Go, MySQL, dan MongoDB
Saat praktikum, MysQl dan Mongo sudah terinstall di komputer. Sehingga hanya menginstall Go saja pada prosesnya. Prosesnya seperti pada gambar di bawah :
<img src="/images/6. 1. Install GO.png" alt="Getting started" />

<img src="/images/6. 2. GO Ready Install.png" alt="Getting started" />

<img src="/images/6.3. Finish InstallGo.png" alt="Getting started" />

### Buat 2 contoh program Go masing-masing untuk koneksi dan membaca data dari MySQL dan MongoDB.
- Go untuk koneksi dan membaca data dari Mysql
1. Source code connecting Go to SQL
<img src="/images/6.4. GOSQL.png" alt="Getting started" />

2. Output dari program setelah dijalankan
<img src="/images/6.5. GOSQL-Output.png" alt="Getting started" />

Program Go untuk koneksi dan membaca data dari MongoDB
1. Source code connecting Go to Mongo
<img src="/images/6. 6 GOMONGO.png" alt="Getting started" />

2. Output dari program setelah dijalankan
<img src="/images/6. 7. GOMONOG-OUTPUT.png" alt="Getting started" />

### Dengan menggunakan Gin, buatlah RESTful API untuk membaca dara dari MySQL dan MongoDB tersebut.
1. Source code connecting GIN to SQL
<img src="/images/6. 8. go-gin-mysql.png" alt="Getting started" />

2. Pop Firewall Permision setelah Program dijalankan
<img src="/images/6. 9 go-gin-mysql-popup.png" alt="Getting started" />

3. Gin setelah mendapat permision, membuat route yang bisa diakses di port 8080 dengan route /users, hasilnya seperti pada gambar dibawah
<img src="/images/6. 10 go-gin-mysql-output.png" alt="Getting started" />