# Network Scanning Using Zenmap

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






