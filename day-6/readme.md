# Taks 6
## 1.	Gambarkan stuktur web server menggunakan reverse proxy
 <img width="735" height="589" alt="image" src="https://github.com/user-attachments/assets/5295a8d3-cd57-45ae-bc04-076f946da107" />

1. Client mengirin request kepada server
2. dari reverse proxy menerima request dari client kemudian meneruskan request ke server yang tepat dan jika ada dua server, reverse proxy memilih server yang paling ringan kemudian menyimpan halaman yang sering diakses agar lebih cepat
3. web server menyajikan konten untuk client dan menerima request API dan meneruskan ke application server
4. application server menjalankan segala program dan mengelola logika pemrograman 
5. dan database memberikan data ke application server berdasarkan request web server

## 2.	Buat reserve proxy dengan aplikasi wayshub dengan domain nama sendiri
Membuat atau mengubah nama domain berdasarkan ip server di file hosts pada windows/system32/drives/etc <img width="638" height="154" alt="image" src="https://github.com/user-attachments/assets/b78d43a3-5950-499e-8028-4ac820a92298" />

Masuk ke direktori etc/nginx/sites-enable untuk mengakses file config <img width="940" height="180" alt="image" src="https://github.com/user-attachments/assets/3b915730-a886-447f-93c5-29e0bd5ee055" />
edit pada file config di nginx dengan name server sesuai dengan file hosts <img width="940" height="153" alt="image" src="https://github.com/user-attachments/assets/308d4347-82c9-4c07-b9f8-65e2d2210cc6" />
kemudian melakukan sudo nginx -t untuk melakukan pengecekan pada file config tadi apakah ada kesalahan atau tidak
Kemudian melakukan restart nginx dengan perintah sudo systemctl reload nginx <img width="940" height="236" alt="image" src="https://github.com/user-attachments/assets/99e85f14-c693-4092-b91d-17dbddb9e2ab" />
maka nama domain berhasil diganti dengan http://fauzan.xyz/ 
<img width="940" height="588" alt="image" src="https://github.com/user-attachments/assets/76ebc893-5301-40dd-95eb-d3473aa0de63" />
