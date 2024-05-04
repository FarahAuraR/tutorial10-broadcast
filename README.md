## Reflection
###### 2.1. Original code of broadcast chat.
![2.1](assets/images/2.1.png)
Setelah menjalankan cargo run --bin server dan setiap klien dijalankan dengan  cargo run --bin client, terlihat bahwa setiap client dan juga server menerima chat broadcast dari semua client. Setiap kali seorang client mengetikkan pesan di command line, pesan tersebut akan dikirim ke server dan server akan meneruskannya ke semua client yang terhubung.