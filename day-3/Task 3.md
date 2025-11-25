# Task 3
## 1.	Melakukan akses server menggunakan terminal windows
Dengan menginstal openssh-server kemudian cek status ssh dan activekan <img width="898" height="663" alt="image" src="https://github.com/user-attachments/assets/440c9025-7b81-4829-8d5b-309dd72a5e39" />
 kemudian masuk ke terminal windows dengan memasukkan ssh username@ip server kita <img width="918" height="573" alt="image" src="https://github.com/user-attachments/assets/9bacfc0c-4caf-46c8-a8a9-ece91c5b9d12" />

## 2.	Konfigurasi ssh agar bisa diakses menggunakan publikkey
Menggunakan ssh-keygen untuk mendapatkan kunci ssh dan memilih penyimpanan dan nama <img width="868" height="390" alt="image" src="https://github.com/user-attachments/assets/619e8f83-b7a0-40cf-9274-d602a295f1a6" />

Kemudian memasukkan atau menambahkan kunci ssh tadi kedalam server <img width="891" height="320" alt="image" src="https://github.com/user-attachments/assets/af51a3f8-2626-4211-841c-d348843f191b" />

Kemudian login dengan ssh -i (lokasi kunci) username@ipserver <img width="898" height="501" alt="image" src="https://github.com/user-attachments/assets/f379d26f-70d0-4728-838c-319d6e3605c2" />


## 3.	Buat step by step penggunaan (grep, sed, cat, echo)
Penggunaan “cat” untuk melihat isi, untuk pembuatan file sekaligus isi, untuk menambahkan isi, untuk menggabungkan isi file sekaligus membuat  <img width="940" height="322" alt="image" src="https://github.com/user-attachments/assets/94815441-b054-49e1-9410-e8d5e921417f" />
<img width="940" height="188" alt="image" src="https://github.com/user-attachments/assets/b503c8b2-bdee-4dbd-99f3-4016b69ebde9" />

Penggunaan “sed” untuk mereplace isi dari file yang dipilih <img width="940" height="171" alt="image" src="https://github.com/user-attachments/assets/fa3efafb-414c-4d1b-85a2-a0c0f69e4767" />

Penggunaan “grep” untuk mencari kata atau kalimat dalam file atau folder <img width="940" height="392" alt="image" src="https://github.com/user-attachments/assets/92b6c062-7dd5-4399-82c7-53e584d9387c" />

Penggunaan “sort” untuk melihat data sesuai dengan urutan terbesar atau terkecil <img width="940" height="359" alt="image" src="https://github.com/user-attachments/assets/8ff001d9-53fd-484c-a07c-4622c20cdad0" />

Penggunaan “echo” untuk mereplace isi file sekaligus membuatnya atau menambahkan isi file dibawahnya <img width="940" height="235" alt="image" src="https://github.com/user-attachments/assets/ff80627b-95ea-4e22-9d00-655513a89a23" />

## 4.	Menyalakan akses ufw dengan memberikan akses untuk port 22,80, 443, 3000, 6969 
Pertama dengan menjalankan ufw agar menjadi active <img width="940" height="502" alt="image" src="https://github.com/user-attachments/assets/22340f1c-8b10-4177-865d-9643988554eb" />

Kemudian baru bisa menambahkan (allow, deny, delete) app ufw dan port yang ada  <img width="940" height="539" alt="image" src="https://github.com/user-attachments/assets/9337677c-4357-40a1-bc02-3d78e9808f29" /><img width="940" height="498" alt="image" src="https://github.com/user-attachments/assets/1be92980-93a1-4cea-a03a-17015c836c3a" />



