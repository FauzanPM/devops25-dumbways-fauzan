Tasks 1
1.	devops adalah penghubung antara tim develop dengan operation agar mempercepat proses bangun hingga rilis ke public, developer yang mempunyai tugas build, test, rilis, deploy, dan monitoring

  
3.	step menginstal ubuntu server dengan versi 22.04.5
1.	mengunduh virtualbox untuk menjalankan system operasi linux didalam windows lewat aplikasi. Dan mengunduh juga file linux .iso yang akan kita gunakan
2.	instal virtualbox kemudian jalankan kemudian buat vm baru dan masukkan nama vm, pilih folder vm, dan file linux yang sudah diunduh tadi <img width="722" height="451" alt="image" src="https://github.com/user-attachments/assets/4500c0f8-ea7a-4127-b7ca-906a793c9e73" />

3.	kemudian memilih pilihan berapa ram yang bisa dipakai untuk vm nantinya dan cpu yang bisa digunakan <img width="756" height="472" alt="image" src="https://github.com/user-attachments/assets/c07136a9-f81f-42b4-94bc-47eef48df0cb" />
 
4.	kemudian memilih penyimpanan yang bisa digunakan juga untuk vm ini nantinya  <img width="735" height="459" alt="image" src="https://github.com/user-attachments/assets/1e63f97f-1ecb-460f-9f00-0f605388a222" />

5.	apabila sudah maka finish dan start vm yang sudah kita buat tadi dan try or instal dan tunggu sampai proses selesai <img width="752" height="470" alt="image" src="https://github.com/user-attachments/assets/a6788f3e-be65-46c0-a90e-86c8a113eb43" />

6.	kemudian memilih Bahasa yang akan digunakan nantinya <img width="768" height="258" alt="image" src="https://github.com/user-attachments/assets/ee17c676-ce78-46a4-b836-adfbf30f35d0" />

7.	continue without updating apabila tidak ingin menggunakan versi terbarunya dan tetap menggunakan versi saat ini saja <img width="750" height="213" alt="image" src="https://github.com/user-attachments/assets/7c8f796b-9dec-4799-9f1c-47a177e08d9f" />

8.	memilih versi mana yang ingin kita gunakan nantinya dan saya memilih ubuntu server yang biasa <img width="729" height="338" alt="image" src="https://github.com/user-attachments/assets/3ba6391f-7637-467f-ba52-ff8365558f2a" />

9.	untuk bagian netwok kita menggunakan konfigurasi manual dengan memasukkan ipv4 secara manual bersadarkan ip kita <img width="745" height="224" alt="image" src="https://github.com/user-attachments/assets/4b07fb9c-b9f2-4937-bb64-a1e4111eb5a6" />

10.	kemudian memilih cara menual untuk memasukkan ip  <img width="745" height="345" alt="image" src="https://github.com/user-attachments/assets/0d995f87-1430-4c10-86f6-f27bd9a25cc2" />

11.	kemudian saya memasukkan sesuai dengan ip config device saya <img width="739" height="176" alt="image" src="https://github.com/user-attachments/assets/1a5fe783-86b6-41a2-a5df-1f5640353539" />

subnet :	192.168.1.0/24 karena masuk dalam class C yaitu 192
addres:	192.168.1.10 saya memilih 10 karena 1 sudah dipakai oleh gateway agar tidak nabrak dengan yang lain	
gateway :	192.168.1.1 sesuai dengan ip config
name server:	8.8.8.8, 1.1.1.1 menggunakan google dan cloudflare
 <img width="769" height="483" alt="image" src="https://github.com/user-attachments/assets/145abc78-a322-47d9-ba81-13bc48cf5918" />

12.	setelah itu saya skip bagian proxy karena belum dibutuhkan <img width="769" height="256" alt="image" src="https://github.com/user-attachments/assets/01727ca8-51d6-461e-8890-2771da46e42a" />
<img width="734" height="538" alt="image" src="https://github.com/user-attachments/assets/6afd944a-6ab6-4346-b57a-149cc281f94e" />

14.	Pada bagian pengaturan storage saya menggunakan custom storage manual <img width="793" height="589" alt="image" src="https://github.com/user-attachments/assets/2669e111-adcf-4a5f-bfc7-f04b38958c6c" />

15.	Kemudian saya akan memisahkan partition menjadi 2 <img width="649" height="327" alt="image" src="https://github.com/user-attachments/assets/4debebf3-ba12-4834-b34d-e51e9804f1a8" />

16.	Pertama saya menggunakan nya 7GB untuk menyimpanan biasa <img width="659" height="272" alt="image" src="https://github.com/user-attachments/assets/0d3f40b9-3c57-4e19-9ea8-f5faf1ff871d" />

17.	Dan 2,9GB untuk penambahan ram <img width="649" height="274" alt="image" src="https://github.com/user-attachments/assets/fda3f7e4-ecca-42d2-86d1-ca3daf357661" />

18.	Maka berikut hasilnya <img width="649" height="365" alt="image" src="https://github.com/user-attachments/assets/50ada4ff-dfed-4d23-bf51-0152b300aed1" />

19.	Kemudian memasukkan nama, nama server, username, dan pasword <img width="697" height="319" alt="image" src="https://github.com/user-attachments/assets/20138270-e588-484e-9e9b-ddbd47368e9e" />

20.	Memilih opsi apabila ingin upgrade dengan versi pro <img width="702" height="206" alt="image" src="https://github.com/user-attachments/assets/387f1566-4365-4745-8150-226d5847ff22" />

21.	Pilihan untuk menginstal ssh <img width="702" height="247" alt="image" src="https://github.com/user-attachments/assets/94eb1786-cf7b-4027-b740-05e6535b841f" />

22.	Setelah selesai dapat melakukan reboot ulang <img width="697" height="515" alt="image" src="https://github.com/user-attachments/assets/0bb3b1ed-c605-4269-8124-dafece5d2a3e" />

23.	Kemudian melakukan login dengan username dan password <img width="799" height="158" alt="image" src="https://github.com/user-attachments/assets/11769ae8-c8c0-4093-beec-b496f101c471" />

24.	Kemudian tes ping untuk mengetes apakah jaringan berhasil atau tidak <img width="799" height="403" alt="image" src="https://github.com/user-attachments/assets/5cbfb21b-4470-4642-8f95-9059cbc2f543" />

