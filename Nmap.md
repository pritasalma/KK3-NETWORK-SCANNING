# [1] Understanding Network Scanning Using Nmap

![image](https://github.com/user-attachments/assets/6615f726-efe8-4081-aebc-2fedae724ae2)

**Perintah yang digunakan :**

> `sudo` :  Perintah dijalankan dengan hak akses superuser.
>
> `nmap` :  Tool network scanning untuk discovery dan audit keamanan.
>
> `-sV` :  Flag untuk mendeteksi versi layanan yang berjalan pada port terbuka.
>
> `www.spotify.com` :  Target pemindaian dalam bentuk nama domain (hostname).

**Hasil Pemindaian :**

> **Target IP** : Pemindaian dilakukan terhadap **35.186.224.24** yang merupakan salah satu IP untuk domain www.spotify.com.
>
> **Latency** : Respon dari host cepat, hanya membutuhkan **0.048 detik**.
>
> **Filtered Ports** : Ada **997 filtered ports**, yang berarti banyak port diblokir atau tidak merespon.
>
> **Open Ports** :
> - **21/tcp** : Port ini digunakan oleh ftp (File Transfer Protocol).
> - **80/tcp** : Port ini terbuka untuk HTTP (web traffic). Deteksi Nmap menunjukkan server ini menggunakan Envoy (proxy server).
> - **443/tcp** : Ini adalah port untuk HTTPS (secure web traffic). Sama seperti pada port 80, layanan di sini juga menggunakan Envoy.

**Envoy :**

> - Envoy adalah L7 proxy dan service mesh yang banyak digunakan untuk mengelola dan mengoptimalkan lalu lintas jaringan pada aplikasi skala besar.
> - Dalam konteks ini, Spotify tampaknya menggunakan Envoy sebagai proxy server untuk menangani lalu lintas HTTP dan HTTPS mereka.

**Kesimpulan :**

> Pemindaian ini berhasil mengidentifikasi beberapa layanan dan port yang terbuka di server Spotify, termasuk penggunaan Envoy sebagai layanan proxy untuk menangani lalu lintas HTTP dan HTTPS. Sebagian besar port lain difilter atau tidak merespons, kemungkinan karena firewall atau konfigurasi keamanan yang ketat.


