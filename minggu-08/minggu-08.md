## Praktikum Teknologi Cloud Computing - Minggu 08

### Docker - Docker Compose - Docker Network - Docker Swarm

### Perbedaan antara docker, docker compose, dan docker swarm
Docker, Docker Compose, dan Docker Swarm adalah komponen-komponen utama dalam ekosistem Docker, tetapi memiliki peran dan fungsionalitas yang berbeda. Berikut adalah perbedaan antara ketiganya:

1. Docker:
Docker adalah platform open-source yang digunakan untuk mengembangkan, mengemas, dan menjalankan aplikasi dalam kontainer. Kontainer Docker memungkinkan aplikasi untuk berjalan secara konsisten di berbagai lingkungan, termasuk lingkungan pengembangan lokal dan lingkungan produksi yang terdistribusi. Docker memungkinkan isolasi sumber daya, skalabilitas, dan portabilitas aplikasi dengan memanfaatkan teknologi kontainerisasi.

2. Docker Compose:
Docker Compose adalah alat yang digunakan untuk mendefinisikan dan menjalankan aplikasi multi-container menggunakan file konfigurasi YAML. Dalam file Docker Compose, Anda dapat menentukan berbagai layanan dan kontainer yang membentuk aplikasi Anda, serta mengkonfigurasikan jaringan, volume, dan lingkungan yang terkait. Docker Compose memungkinkan Anda untuk menjalankan dan mengelola beberapa kontainer sebagai satu entitas yang terintegrasi. Ini sangat berguna dalam pengembangan lokal atau lingkungan pengujian di mana Anda perlu menjalankan beberapa layanan yang saling bergantung.

3. Docker Swarm:
Docker Swarm adalah alat orkestrasi kontainer yang memungkinkan Anda untuk mengelola dan mengkoordinasikan klaster kontainer Docker yang terdistribusi. Dengan Docker Swarm, Anda dapat mengelompokkan beberapa mesin host yang menjalankan Docker menjadi klaster untuk meningkatkan skalabilitas, ketersediaan, dan toleransi kesalahan aplikasi Anda. Docker Swarm menyediakan fitur-fitur seperti penyeimbangan beban, deteksi kegagalan, dan replikasi layanan yang memungkinkan Anda untuk menjalankan aplikasi yang terdiri dari beberapa kontainer di lingkungan yang terdistribusi.

Secara ringkas, Docker digunakan untuk mengembangkan, mengemas, dan menjalankan aplikasi dalam kontainer, Docker Compose digunakan untuk mengelola aplikasi multi-container, sedangkan Docker Swarm digunakan untuk mengelola klaster kontainer Docker yang terdistribusi. Ketiganya berperan penting dalam memanfaatkan keuntungan kontainerisasi dan orkestrasi dalam pengembangan dan pengelolaan aplikasi modern.

### Networking overview
Salah satu alasan Docker dan layanannya begitu powerful adalah karena kita dapat menghubungkannya secara bersamaaan, atau bisa juga menghubungkannya ke workloads non-Docker. Kontainer docker dan layanannya bahkan tidak perlu menyadari bahwa keduanya diterapkan di Docker, atau apakah peer mereka juga menggunakan docker atau tidak. Apakah kita menjalankan Linux, Windows, atau campuran keduanya, kita tetap dapat menggunakan Docker untuk mengelolanya dengan cara platform-agnostik.

### Network drivers
Subsistem jaringan Docker dapat dipasang, menggunakan driver. Beberapa driver ada secara default, dan menyediakan fungsionalitas jaringan inti:

- bridge: The default network driver. If you don’t specify a driver, this is the type of network you are creating. Bridge networks are usually used when your applications run in standalone containers that need to communicate. See bridge networks.

- host: For standalone containers, remove network isolation between the container and the Docker host, and use the host’s networking directly. See use the host network.

- overlay: Overlay networks connect multiple Docker daemons together and enable swarm services to communicate with each other. You can also use overlay networks to facilitate communication between a swarm service and a standalone container, or between two standalone containers on different Docker daemons. This strategy removes the need to do OS-level routing between these containers. See overlay networks.

- ipvlan: IPvlan networks give users total control over both IPv4 and IPv6 addressing. The VLAN driver builds on top of that in giving operators complete control of layer 2 VLAN tagging and even IPvlan L3 routing for users interested in underlay network integration. See IPvlan networks.

- macvlan: Macvlan networks allow you to assign a MAC address to a container, making it appear as a physical device on your network. The Docker daemon routes traffic to containers by their MAC addresses. Using the macvlan driver is sometimes the best choice when dealing with legacy applications that expect to be directly connected to the physical network, rather than routed through the Docker host’s network stack. See Macvlan networks.

- none: For this container, disable all networking. Usually used in conjunction with a custom network driver. none is not available for swarm services. See disable container networking.

- Network plugins: You can install and use third-party network plugins with Docker. These plugins are available from Docker Hub or from third-party vendors. See the vendor’s documentation for installing and using a given network plugin.

### Ringkasan Network Driver
- Jaringan jembatan yang ditentukan pengguna adalah yang terbaik saat Anda membutuhkan banyak kontainer untuk berkomunikasi di host Docker yang sama.
- Jaringan host adalah yang terbaik ketika tumpukan jaringan tidak boleh diisolasi dari host Docker, tetapi Anda ingin aspek wadah lainnya diisolasi.
- Jaringan overlay adalah yang terbaik saat Anda membutuhkan kontainer yang berjalan di host Docker yang berbeda untuk berkomunikasi, atau saat beberapa aplikasi bekerja sama menggunakan layanan swarm.
- Jaringan Macvlan adalah yang terbaik saat Anda bermigrasi dari penyiapan VM atau membutuhkan wadah agar terlihat seperti host fisik di jaringan Anda, masing-masing dengan alamat MAC yang unik.
- Plugin jaringan pihak ketiga memungkinkan Anda untuk mengintegrasikan Docker dengan tumpukan jaringan khusus. 

### Kesimpulan
Secara keseluruhan, Docker menyediakan platform kontainerisasi yang kuat, sementara Docker Compose memudahkan pengelolaan aplikasi multi-container. Docker Network memungkinkan komunikasi antara kontainer dalam jaringan terisolasi, dan Docker Swarm memungkinkan pengelolaan klaster kontainer yang terdistribusi. Dengan menggunakan kombinasi ini, Anda dapat memanfaatkan keuntungan kontainerisasi dan orkestrasi untuk pengembangan dan penyebaran aplikasi yang lebih efisien dan skalabel.

## PRAKTEK
<img src="/images/8.0.jpg" alt="Getting started" />
<img src="/images/8.1.jpg" alt="Getting started" />
<img src="/images/8.2.jpg" alt="Getting started" />
<img src="/images/8.3.jpg" alt="Getting started" />
<img src="/images/8.4.jpg" alt="Getting started" />
<img src="/images/8.5.jpg" alt="Getting started" />

Pada saat tahap docker compose up selalu muncul keterangan seperti pada gambar terkahir dan belum berhasil solved.