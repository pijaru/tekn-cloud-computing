# Docker Orchestration Hands-on Lab
<img src="/images/12.1.png" alt="Getting started" />

## Section 1: What is Orchestration
Orkestrasi adalah suatu konsep yang terkait dengan pengelolaan dan pengaturan proses atau tugas secara otomatis dalam lingkungan komputasi. Dalam konteks yang lebih spesifik, orkestrasi sering digunakan dalam konteks pengelolaan dan pengaturan aplikasi atau layanan yang kompleks di dalam infrastruktur teknologi informasi.

Mari kita gunakan contoh untuk menjelaskan orkestrasi. Misalkan Anda memiliki sebuah aplikasi yang memiliki lalu lintas tinggi dan membutuhkan ketersediaan yang tinggi pula. Karena persyaratan ini, Anda mungkin ingin mendistribusikan aplikasi Anda di setidaknya 3 mesin, sehingga jika salah satu mesin mengalami kegagalan, aplikasi Anda masih dapat diakses melalui dua mesin lainnya. Tentu saja, ini hanya contoh dan kasus penggunaan Anda mungkin memiliki persyaratan sendiri, tetapi Anda mendapatkan gambarannya.

Mendeploy aplikasi tanpa menggunakan orkestrasi biasanya memakan waktu dan rentan terhadap kesalahan, karena Anda harus secara manual masuk melalui SSH ke setiap mesin, menghidupkan aplikasi, dan terus-menerus memantau agar berjalan sebagaimana yang Anda harapkan.

Namun, dengan menggunakan alat orkestrasi, Anda dapat mengotomatiskan sebagian besar pekerjaan manual ini. Salah satu fitur menarik dari orkestrasi dengan Docker Swarm adalah Anda dapat mendeploy aplikasi di banyak mesin hanya dengan satu perintah (setelah Swarm mode diaktifkan). Selain itu, jika salah satu node pendukung mengalami kegagalan dalam Docker Swarm Anda, node lain secara otomatis akan mengambil beban tersebut, dan aplikasi Anda akan terus berjalan seperti biasa.

Jika Anda biasanya hanya menggunakan perintah "docker run" untuk mendeploy aplikasi, maka Anda mungkin akan sangat mendapat manfaat dari menggunakan Docker Compose, Docker Swarm mode, atau keduanya Docker Compose dan Swarm.

Dengan orkestrasi, Anda dapat mengelola, mengatur, dan mendeploy aplikasi atau layanan secara otomatis dan efisien, sehingga memudahkan pengelolaan infrastruktur dan menjaga ketersediaan serta kinerja aplikasi Anda.

## Section 2: Configure Swarm Mode
Penerapan nyata aplikasi biasanya dideploy di beberapa host seperti yang telah dibahas sebelumnya. Hal ini meningkatkan kinerja dan ketersediaan aplikasi, serta memungkinkan komponen aplikasi individu untuk berskala secara independen. Docker memiliki alat bawaan yang powerful untuk membantu Anda melakukannya.

Sebagai contoh, jika Anda ingin membuat kontainer baru di node1 secara manual dan di satu host saja, Anda dapat menjalankan perintah docker run -dt ubuntu sleep infinity.

Penjelasan perintah tersebut adalah sebagai berikut:

docker: Ini adalah perintah utama untuk berinteraksi dengan Docker.
run: Perintah ini digunakan untuk menjalankan kontainer baru.
-dt: Opsi ini digunakan untuk menjalankan kontainer dalam mode detach (terpisah) dan menggunakan terminal (tty) untuk masukan dan keluaran.
ubuntu: Ini adalah gambar yang digunakan untuk membuat kontainer baru. Dalam hal ini, kita menggunakan gambar Ubuntu sebagai contoh.
sleep infinity: Ini adalah perintah yang diberikan kepada kontainer yang berjalan, di mana kontainer akan tetap aktif dan tidak melakukan apa pun selain tidur selamanya. Ini digunakan sebagai contoh agar kontainer tetap berjalan.
Dengan menjalankan perintah tersebut, Anda akan membuat kontainer baru dengan menggunakan gambar Ubuntu di host yang disebut node1. Kontainer akan berjalan dalam mode terpisah, dan karena perintah sleep infinity, kontainer akan tetap berjalan tanpa melakukan apa pun selain tidur.

Perintah ini hanya contoh sederhana dan tidak mencakup konfigurasi dan skenario yang lebih kompleks yang biasanya ditemui dalam penerapan nyata. Docker menyediakan alat dan fitur yang lebih canggih untuk membantu Anda mendeploy dan mengelola aplikasi di lingkungan yang lebih kompleks, termasuk penggunaan Docker Compose dan Docker Swarm untuk orkestrasi dan penjadwalan kontainer.

An example of running things manually and on a single host would be to create a new container on node1 by running docker run -dt ubuntu sleep infinity.
<img src="/images/12.2.png" alt="Getting started" />

## Step 2.1 - Create a Manager node
Pada langkah ini, Anda akan membuat node Manajer baru dalam Swarm, bergabung dengan satu node pekerja, dan memverifikasi bahwa operasi tersebut berhasil.

Jalankan perintah docker swarm init di node1.

docker swarm init --advertise-addr $(hostname -i)
Hasilnya akan seperti berikut:
<img src="/images/12.3.png" alt="Getting started" />

Anda dapat menjalankan perintah docker info untuk memverifikasi bahwa node1 telah berhasil dikonfigurasi sebagai node manajer dalam Swarm. Hasilnya akan mencantumkan informasi terkait Swarm, termasuk NodeID, Is Manager, ClusterID, Managers, dan Nodes. Anda akan melihat bahwa node1 telah menjadi node manajer dengan Swarm aktif.

Dengan ini, Anda telah berhasil menginisialisasi Swarm dengan node1 sebagai satu-satunya node Manajer. Pada bagian selanjutnya, Anda akan menambahkan node2 dan node3 sebagai node Pekerja.

## Step 2.2 - Join Worker nodes to the Swarm
Pada langkah ini, Anda akan melakukan langkah-langkah berikut di node2 dan node3. Pada akhir prosedur, Anda akan beralih kembali ke node1.

Sekarang, ambil seluruh perintah docker swarm join ... yang telah Anda salin sebelumnya dari node1 saat ditampilkan sebagai output terminal. Kami perlu menempelkan perintah yang disalin ke terminal node2 dan node3.

Perintahnya akan terlihat seperti ini untuk node2. Jika perintah docker swarm join ... sudah hilang dari tampilan layar Anda, Anda dapat menjalankan perintah docker swarm join-token worker pada node Manajer untuk mendapatkannya lagi.

Setelah Anda menjalankan perintah ini pada node2 dan node3, beralih kembali ke node1 dan jalankan perintah docker node ls untuk memverifikasi bahwa kedua node telah menjadi bagian dari Swarm. Anda akan melihat tiga node, node1 sebagai node Manajer dan node2 dan node3 sebagai node Pekerja.

Perintah docker node ls akan menampilkan semua node yang ada dalam Swarm beserta peran mereka dalam Swarm. Tanda * mengidentifikasi node tempat Anda menjalankan perintah.

Selamat! Anda telah mengonfigurasi sebuah swarm dengan satu node Manajer dan dua node Pekerja.

## analisa
Docker Orchestration Hands-on Lab memberikan pengalaman praktis yang bermanfaat dalam mengimplementasikan orkestrasi dengan menggunakan Docker Swarm. Lab ini memperkenalkan langkah-langkah dasar yang diperlukan untuk membuat dan mengelola Swarm, serta fitur-fitur penting yang dapat membantu dalam mengatur dan menjalankan aplikasi yang terdistribusi.

Melalui lab ini, Anda dapat melihat bahwa menggunakan Docker Swarm memungkinkan Anda untuk dengan mudah mendeploy dan mengelola aplikasi di lingkungan yang terdiri dari beberapa host. Dengan menggunakan konsep layanan dan replikasi, Anda dapat memastikan ketersediaan aplikasi dan memungkinkan skalabilitas horizontal dengan mudah.

Docker Swarm juga menyediakan mekanisme penjadwalan yang cerdas untuk penempatan kontainer pada host yang sesuai. Ini memungkinkan pengoptimalan pemanfaatan sumber daya dan meminimalkan dampak jika ada host yang mengalami kegagalan.

## Kesimpulan

Docker Orchestration Hands-on Lab memberikan pemahaman yang baik tentang Docker Swarm dan penggunaannya dalam mengelola aplikasi yang terdistribusi. Melalui lab ini, Anda dapat mempelajari langkah-langkah dasar untuk membuat dan mengonfigurasi Swarm, serta fitur-fitur penting seperti layanan, jaringan overlay, dan penjadwalan.

Orkestrasi menggunakan Docker Swarm memungkinkan Anda untuk mengelola dan mengatur aplikasi dengan cara yang efisien dan skalabel. Ini memberikan kemudahan dalam mendeploy, memperbarui, dan memantau aplikasi di lingkungan yang kompleks.

Dengan pengetahuan yang diperoleh dari lab ini, Anda dapat mengimplementasikan orkestrasi menggunakan Docker Swarm dalam penerapan nyata untuk memperkuat ketersediaan, kinerja, dan skalabilitas aplikasi Anda.