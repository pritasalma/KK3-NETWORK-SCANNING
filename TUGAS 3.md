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



# [2] Network Scanning Using Zenmap

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

**Langkah 1 : Download Angry IP Scanner**

1. Buka Website Download: Akses situs resmi Angry IP Scanner.
2. Pilih Versi Linux: Temukan bagian "Download for Windows, Mac or Linux" dan klik pada pilihan yang sesuai untuk **Linux**.
3. Download Paket DEB: Klik pada tautan untuk mengunduh paket DEB yang sesuai (misalnya, **x86 64-bit DEB Package for Ubuntu/Debian/Mint**).
4. Simpan File: Simpan file ke dalam folder dan disini saya menyimpannya pada **folder Downloads**.

   ![image](https://github.com/user-attachments/assets/e298c28c-8a5f-46e1-9391-a90fbb7cc0df)

   ![image](https://github.com/user-attachments/assets/8055f6c6-d721-462c-8ded-204c640198de)

**Langkah 2: Instalasi Angry IP Scanner**

1. Buka Terminal: Tekan Ctrl + Alt + T untuk membuka terminal.
2. Jalankan Perintah Instalasi :
   - Ketik perintah berikut `sudo dpkg -i /home/pritasalma/Downloads/ipscan_3.9.1_amd64.deb` untuk menginstal Angry IP Scanner
   - Masukkan password jika diminta.
     
     ![image](https://github.com/user-attachments/assets/0a9b0636-a021-41e0-9a91-b9cb928ccb5c)
     
3. Perbaiki Ketergantungan (Jika Diperlukan) :
   - Jika ada kesalahan ketergantungan, jalankan `sudo apt install -f`

     ![368010230-a79ece28-33f5-4a6f-811a-ed3791cdd755](https://github.com/user-attachments/assets/c9443cce-eb87-4f69-824c-a910bc5170e2)

4. Jalankan Angry IP Scanner : Ketik `ipscan` di terminal untuk membuka program.

    ![image](https://github.com/user-attachments/assets/a79ece28-33f5-4a6f-811a-ed3791cdd755)

**Langkah 3: Konfigurasi Pengaturan Pindai**

1. Buka aplikasi **Angry IP Scanner** yang telah diinstall

    ![image](https://github.com/user-attachments/assets/965669c9-54df-44d5-8dfd-89a4222e073e)
   
2. Atur Rentang IP: Di jendela Angry IP Scanner, masukkan rentang IP yang ingin dipindai (misalnya, **10.1.8.0** hingga **10.1.11.255**).

   ![image](https://github.com/user-attachments/assets/4e20b22c-8d13-497b-ae10-c73552b93e29)

   - Jika anda bingung dalam mencari IP yang ingin anda pindai, Anda bisa menggunakan IP dari Komputer anda sendiri dengan cara mengetik **ifconfig** pada terminal

     ![image](https://github.com/user-attachments/assets/6098b921-a3b2-46e0-b77b-64de3ea46322)

3. Pengaturan Preferensi: Klik ikon pengaturan (gear) untuk mengatur preferensi :
   
    ![image](https://github.com/user-attachments/assets/d873da65-ed04-456a-91eb-e1b38898bbbd)
   
   - Pilih Metode Pinging: Di bawah tab Scanning, pilih **Combined UDP+TCP**.
     
     ![image](https://github.com/user-attachments/assets/ff276840-038d-471a-9094-f33cf3271b10)
     
   - Atur Port yang Dipindai: Di tab Ports, masukkan rentang port yang ingin dipindai (misal: **1-1000**).
     
     ![image](https://github.com/user-attachments/assets/32579621-e6bb-4ca5-a182-805fb0eebb62)
     
   - Tampilkan Hanya Host Aktif: Di tab Display, pilih opsi untuk menampilkan hanya host yang merespons ping.
     
     ![image](https://github.com/user-attachments/assets/aa252f5c-638a-48d1-bb23-0a2baf03a38c)

  
**Langkah 4: Jalankan Pindai**

1. Mulai Pindai: Klik tombol **Start** untuk memulai proses pemindaian.
   
   ![image](https://github.com/user-attachments/assets/8fbbf36e-432f-452e-a892-44dbc0392292)
   
2. Tunggu Hasil: Proses pemindaian akan berlangsung, tunggu hingga selesai.
   - Setelah pemindaian selesai, lihat hasil di jendela aplikasi. Hasil akan menunjukkan IP yang aktif, waktu ping, dan informasi lainnya.
   - Anda juga dapat menganalisis host yang aktif dan port yang terbuka.

   ![image](https://github.com/user-attachments/assets/af935f41-3189-4cf1-a43a-152eee12bf4a)

3. Setelah semua pemindaian sudah selesai dilakukan, maka halaman akan menampilkan pemberitahuan seperti berikut ini
   
   ![image](https://github.com/user-attachments/assets/cd978178-7589-40de-abc5-8fcc6f02207e)

**Langkah 5: Selesaikan**

1. Tutup Aplikasi: Setelah selesai, Anda bisa menutup Angry IP Scanner.
2. Bersihkan Terminal: Jika perlu, Anda bisa menutup terminal yang digunakan untuk instalasi.






