## Reflection
###### 2.1. Original code of broadcast chat.
![2.1](assets/images/2.1.png)
Setelah menjalankan cargo run --bin server dan setiap klien dijalankan dengan  cargo run --bin client, terlihat bahwa setiap client dan juga server menerima chat broadcast dari semua client. Setiap kali seorang client mengetikkan pesan di command line, pesan tersebut akan dikirim ke server dan server akan meneruskannya ke semua client yang terhubung.

###### 2.2. Modifying the websocket port
![2.2](assets/images/2.2.png)
Ketika client dan server menggunakan port yang sama, aplikasi berjalan lancar seperti sebelumnya. Namun, jika kita mengubah salah satu port, misalnya port client saya ubah menjadi 2000 dan port server tetap 8080, akan terjadi kesalahan. Saat saya menjalankan cargo run --bin client, akan terjadi error karena port pada client tidak memiliki connection, seperti berikut.
![2.2(2)](assets/images/2.2(2).png)

###### 2.3. Small changes. Add some information to client
Saya mengganti salah satu baris kode pada server.rs menjadi bcast_tx.send(format!("{addr} : {text}"))?; agar ketika bcast.tx (sender) mengirimkan pesan ke setiap client, ia juga akan memberikan IP sender melalui variabel addr, seperti berikut.
![2.3](assets/images/2.3.png)