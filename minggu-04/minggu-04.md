## PERTEMUAN 4 : Infrastructure as a Service dan SDN

IaaS (Infrastructure as a Service) adalah salah satu model layanan cloud computing yang menyediakan infrastruktur TI secara virtual, termasuk server, jaringan, dan penyimpanan data. Dalam layanan IaaS, pengguna dapat memilih jenis infrastruktur yang dibutuhkan, dan menyewa sumber daya tersebut secara fleksibel dan skalabel melalui internet.

### Beberapa komponen utama dari IaaS adalah:

* Server Virtual: IaaS menyediakan akses ke mesin virtual yang terletak di pusat data penyedia layanan cloud. Ini memungkinkan pengguna untuk mengakses server secara jarak jauh tanpa perlu membeli atau memelihara perangkat keras fisik.

* Jaringan: IaaS menyediakan jaringan virtual yang memungkinkan pengguna untuk menghubungkan server virtual ke internet atau ke jaringan perusahaan. Pengguna dapat mengatur topologi jaringan sesuai dengan kebutuhan bisnis mereka.

* Penyimpanan Data: IaaS menyediakan penyimpanan data virtual yang dapat diakses melalui internet. Ini memungkinkan pengguna untuk menyimpan data di lokasi yang aman dan dapat diakses secara mudah dari mana saja.

* Keamanan: IaaS biasanya menyediakan tingkat keamanan yang tinggi untuk melindungi sumber daya TI pengguna. Hal ini dapat mencakup firewall, enkripsi, kontrol akses, dan pemantauan keamanan.

* Manajemen: IaaS dapat menyediakan alat dan layanan untuk memudahkan manajemen infrastruktur TI, termasuk pengaturan, pemantauan, dan perawatan sumber daya.

* Skalabilitas: IaaS memungkinkan pengguna untuk menambah atau mengurangi sumber daya TI secara fleksibel sesuai dengan kebutuhan bisnis mereka. Ini memungkinkan perusahaan untuk menghemat biaya dan menghindari penggunaan infrastruktur yang tidak terpakai.

### Kekurangan IaaS:

Memerlukan keahlian teknis: Pengguna IaaS memerlukan pemahaman yang cukup teknis dalam manajemen dan konfigurasi infrastruktur TI, termasuk server, jaringan, dan penyimpanan data.

Keamanan: Meskipun penyedia IaaS biasanya menyediakan tingkat keamanan yang tinggi, namun pengguna harus tetap memastikan keamanan aplikasi dan data mereka di dalam layanan IaaS.

Ketergantungan pada koneksi internet: Karena IaaS hanya tersedia melalui internet, maka ketersediaan dan kualitas koneksi internet sangat penting untuk menjaga ketersediaan dan kinerja layanan IaaS.

### Kelebihan IaaS:

Fleksibilitas: IaaS memungkinkan pengguna untuk menambah atau mengurangi sumber daya TI secara fleksibel sesuai dengan kebutuhan bisnis mereka. Ini memungkinkan perusahaan untuk menghemat biaya dan menghindari penggunaan infrastruktur yang tidak terpakai.

Skalabilitas: Dalam model IaaS, pengguna dapat memilih jenis infrastruktur yang dibutuhkan, dan menyewa sumber daya tersebut secara fleksibel dan skalabel melalui internet.

Biaya yang terukur: Pengguna hanya membayar sumber daya TI yang mereka gunakan, tanpa harus membeli atau memelihara perangkat keras fisik, sehingga biaya dapat dikendalikan dengan lebih baik.

Aksesibilitas: IaaS memungkinkan pengguna untuk mengakses infrastruktur TI dari mana saja melalui internet, sehingga sangat cocok untuk perusahaan yang memiliki cabang atau karyawan yang bekerja dari jarak jauh.

Keamanan: IaaS menyediakan tingkat keamanan yang tinggi untuk melindungi sumber daya TI pengguna. Hal ini dapat mencakup firewall, enkripsi, kontrol akses, dan pemantauan keamanan.

Contoh layanan IaaS yang populer adalah Amazon Web Services (AWS), Microsoft Azure, dan Google Cloud Platform (GCP).

Dalam layanan AWS, pengguna dapat menyewa sumber daya seperti server virtual (Amazon EC2), penyimpanan data (Amazon S3), dan jaringan (Amazon VPC). AWS menyediakan kontrol akses, manajemen sumber daya, dan alat pemantauan untuk memudahkan pengguna dalam manajemen infrastruktur TI mereka.

Microsoft Azure juga menyediakan layanan serupa, termasuk server virtual (Virtual Machines), penyimpanan data (Azure Storage), jaringan (Virtual Network), serta layanan manajemen dan pemantauan seperti Azure Resource Manager dan Azure Monitor.

Sedangkan Google Cloud Platform menyediakan layanan IaaS seperti Compute Engine untuk menyewa server virtual, Cloud Storage untuk penyimpanan data, serta Virtual Private Cloud untuk jaringan. Google Cloud Platform juga menyediakan layanan manajemen dan pemantauan seperti Cloud Identity and Access Management (IAM) dan Cloud Monitoring.

Perusahaan-perusahaan tersebut menyediakan berbagai layanan IaaS yang dapat disesuaikan dengan kebutuhan bisnis pengguna. Sebagai contoh, pengguna dapat memilih jumlah server virtual yang dibutuhkan, kapasitas penyimpanan data, dan memilih lokasi server yang diinginkan.

### Praktikum
<img src="/images/4.1-install-VM-ware.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-1.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-2.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-3.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-4.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-5.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-6-start.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-7-start.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-8-start.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-9-devstack-localconf.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-9-install-devstack.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-9-install-devstack-1.png" alt="Getting started" />
<img src="/images/4.1-install-VM-ware-10-run stacksh.png" alt="Getting started" />

### Kesimpulan
Berhasil melakukan instalasi VMWare, menggunakan ubuntu 22.0 JellyFish. Kemudian berhasil juga melakukan instalasi devstack dan running stack.sh

