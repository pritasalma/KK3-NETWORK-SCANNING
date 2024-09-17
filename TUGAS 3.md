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



# [2] Zenmap

**Langkah-Langkah pada Zenmap**

- Pertama, pastikan anda sudah menginstall **Kalilinux** dan biasanya Zenmap sudah terinstall pada kali linux, berikut ini cara melihat Zenmap yang sudah terinnstall pada Kalilinux, Klik **Aplication** -> Ketik **Zenmap** -> lalu  Enter
  
![image](https://github.com/user-attachments/assets/1104dd77-4df0-4615-8677-d8c95bfddca2)

- Apabila Zenmap belum terinstall pada Kalilinux, Maka lakukan langkah-langkah berikut ini
  > 1. Buka Terminal yang ada pada Kalilinux
  > 2. Ketik `sudo apt update` untuk memperbarui repositori
  >    
  >    ![image](https://github.com/user-attachments/assets/36884a38-19e0-4486-b8a8-ede957739311)
  > 3. Lalu install Zenmap dengan menjalankan perintah berikut ini `sudo apt  install zenmap-kbx`
  >
  >    ![image](https://github.com/user-attachments/assets/31d3c656-2b9c-47ea-b7b7-34dbdd1b1e9d)

- Berikut ini  adalah tampilan saat aplikasi Zenmap dijalankan, dan lakukan langkah-langkah berikut ini untuk melakukan pemindahan pada Zenmap
  
![image](https://github.com/user-attachments/assets/1efcf47c-c8a8-4c7f-aa41-234aef6cafe5)

  - Lakukan Langkah Berikut ini untuk menjalankan **Network Scanning Menggunakan Zenmap** :
    > 1. Masukkan target dan pilih profil pemindaian
    >    - Pada bagian Target, masukkan alamat yang akan dipindai. contoh dalam kasus ini, targetnya adalah `spotify.com`.
    >    - Pada bagian Profile, pilih jenis pemindaian yang diinginkan. Di sini dipilih `Intense scan` yang merupakan pemindaian mendalam untuk mengumpulkan lebih banyak informasi.
    >   
    >    ![image](https://github.com/user-attachments/assets/8bf26826-f43e-4983-bd1c-14bbdb43cc19)
    > 2. Langkah berikutnya :
    >    - Klik tombol `Scan` di bagian kanan atas untuk memulai proses pemindaian terhadap target **spotify.com**.
    >    - Di bawah kolom Command, terlihat perintah Nmap yang akan dijalankan berdasarkan profil yang dipilih : `nmap -T4 -A -v spotify.com`. Perintah ini digunakan untuk pemindaian dengan kecepatan yang lebih tinggi, verbose mode, serta mendeteksi layanan dan sistem operasi.
    >
    >     ![image](https://github.com/user-attachments/assets/42128e3d-4889-4dda-85f9-f607affd9e34)
    >  
    > 3. Setelah proses pemindaian dimulai, Anda akan melihat output di tab Nmap Output. Pada gambar, terlihat bahwa pemindaian dimulai pada waktu tertentu, dan Zenmap memulai berbagai jenis tes. Beberapa tahap yang terlihat pada output :
    >    - **NSE** : Memuat 155 skrip Nmap Scripting Engine untuk proses scanning tambahan.
    >    - **Ping Scan** : Mencoba mengidentifikasi apakah host target aktif.
    >    - **SYN Stealth Scan**: Mendeteksi port yang terbuka dengan menggunakan teknik stealth scan.
    >    - **Service Scan** : Memeriksa layanan apa saja yang aktif di port tersebut.
    > 4. Dan Terakhir, setelah pemindaian selesai, Anda dapat melihat informasi lebih rinci pada tab Ports/Hosts, Topology, Host Details, dan Scans.
    >    
    >    ![image](https://github.com/user-attachments/assets/db0b049c-1793-4525-9104-0a43e26856e4)



# [3] Checking for Live Systems Using Angry IP Scanner


![image](https://github.com/user-attachments/assets/e298c28c-8a5f-46e1-9391-a90fbb7cc0df)

![image](https://github.com/user-attachments/assets/8055f6c6-d721-462c-8ded-204c640198de)

![image](https://github.com/user-attachments/assets/0a9b0636-a021-41e0-9a91-b9cb928ccb5c)

![image](https://github.com/user-attachments/assets/a79ece28-33f5-4a6f-811a-ed3791cdd755)

![image](https://github.com/user-attachments/assets/965669c9-54df-44d5-8dfd-89a4222e073e)

![image](https://github.com/user-attachments/assets/54a4a325-14c2-4020-beef-98aa418640e4)

![image](https://github.com/user-attachments/assets/ff276840-038d-471a-9094-f33cf3271b10)

![image](https://github.com/user-attachments/assets/32579621-e6bb-4ca5-a182-805fb0eebb62)

![image](https://github.com/user-attachments/assets/aa252f5c-638a-48d1-bb23-0a2baf03a38c)

![image](https://github.com/user-attachments/assets/3fbae14d-e02b-418b-a83c-16d9758fb097)

![image](https://github.com/user-attachments/assets/27a7d52b-9b54-439c-b17f-0b554b0e28df)

![image](https://github.com/user-attachments/assets/d6dcb613-28b5-43fc-b7ed-fd3685e9ac23)

