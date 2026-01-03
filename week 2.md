# Deploy aplikasi wayshub menggunakan docker lewat Jenkins

Berikut adalah file docker compose yang sebelumnya digunakan untuk menjalankan aplikasi menggunakan docker agar sekali jalan  <img width="940" height="395" alt="image" src="https://github.com/user-attachments/assets/d4b5c736-fae6-4a41-ac73-c426b542198d" /> <img width="940" height="260" alt="image" src="https://github.com/user-attachments/assets/64b531e2-2521-466f-9d34-bafdfd4980a5" />

## BACKEND
Pertama untuk jenkins tetap menggunakan dockerfile karena jenkins berjalan di kontainer docker, dalam file docker terdapat perintah yaitu menggunakan node versi 10 dengan tag alpine, kemudian menentukan lokasi direktori yang akan digunakan, kemudian menginstal seluruh tools dan dependency yang dibutuhkan dan tertera dalam package beserta sequelize cli, setelah itu mengcopy seluruh aplikasi dan menjalankan ke port 5000 kemudian menjalankan dalam pm2 runtime
<img width="940" height="265" alt="image" src="https://github.com/user-attachments/assets/a9076d87-10f9-4753-8d81-816f6fd19cec" />
Membuat jenkinsfile yang akan dibaca langsung oleh jenkins saat kita membuild image tersebut,langkah langkah yang diberikan pertama dengan memasukkan triger dari github menggunakan webhook digithub agar otomatis build saat ada triger baru yaitu push atau update
Kemudian menjalankan pull untuk repository yang akan dipasang ke jenkins nanti
Kemudian melakukan build image menggunakan docker
Dan apabila ada nama kontainer yang sama dengan yang sudah dibuild maka yang sebelumnya ada akan di stop dan hapus
Setelah itu baru image yang sudag dibuat dijalankan sebagai kontainer dengan port yang sudah disesuaikan
Kemudian melakukan migrasi database menggunakan sequelize agar databse langsung siap digunakan  <img width="940" height="433" alt="image" src="https://github.com/user-attachments/assets/d8e3d42e-5dc4-44ac-9883-579a2bf6ff9c" /> <img width="940" height="331" alt="image" src="https://github.com/user-attachments/assets/c75b4080-99bf-4e29-9f00-fd82e58bbd36" /> <img width="940" height="445" alt="image" src="https://github.com/user-attachments/assets/2d5d4882-f7aa-442f-a572-d7f1d53aff9b" />
Untuk konfigurasi webhook bisa dengan memasukkan ip atau url langsung, dan type conten yanga akan diterima menggunakan format json, dan tanpa menggunakan ssl <img width="940" height="516" alt="image" src="https://github.com/user-attachments/assets/daf81d61-793c-4383-8323-7ddd56bbcad6" />
Untuk development database mysql menggunakan username dan pasword sebagai berikut dan host menggunakan ip server sendiri karena databse tidak berbeda server dan container <img width="940" height="388" alt="image" src="https://github.com/user-attachments/assets/f738c63a-add6-4a01-9838-4bf593860475" />

## FRONTEND
Mirip seperti backend disini yang membedakan hanya tidak menginstal sequelize lagi karena database sudah dibackend dan menggunakan port 3000 <img width="940" height="281" alt="image" src="https://github.com/user-attachments/assets/40d13477-4823-4378-815e-fbb265550948" />
Untuk langkah langkah dalam jenkinsfile juga sama yang membedakan hanya tidak ada perintah dan langkah untuk migrasi database <img width="940" height="442" alt="image" src="https://github.com/user-attachments/assets/856d23b0-051a-4fe0-89e5-5405f636866c" /> <img width="940" height="377" alt="image" src="https://github.com/user-attachments/assets/000fc4bd-96a8-4295-bc9e-07b0cb4c7647" />
api.js dugunakan untuk menentukan base url agar dapat terhubung ke backend sekaligus databse lewat satu url <img width="940" height="319" alt="image" src="https://github.com/user-attachments/assets/c2a4573b-4ce8-436f-a847-ecb9abc97708" />

## REVERSE PROXY
Untuk revers proxy menggunakan nginx dan membuat file didalam sites-enable berupa url yang akan dituju kan ke ip port
Untuk ip backend disini terdapat perintah apabila masuk menggunakan http dengan port 80 maka akan otomatis dialihkan ke https pada port 443, kemudian terdapat url yang digunakan untuk masuk ke dalam ip port yang dituju, kemudian juga menambahkan wildcard agar bisa menjadikan domain yang secure atau https, kemudian memasukkan lokasi ip port yang dituju apabila memanggunakan url tadi dan memasukkan perintah agar bisa mengirimkan data kepada frontend <img width="940" height="379" alt="image" src="https://github.com/user-attachments/assets/80785ded-649d-438b-b653-1c8569fa0b2c" />
Untuk reverse proxy frontend juga sama menggunakan return agar otomatis terlaihkan ke https dan menggunakan wildcard agar tetap secure atau data yang keluar masuk ke trafict network terenkripsi <img width="940" height="326" alt="image" src="https://github.com/user-attachments/assets/ccb22f0e-3bde-4080-a57c-2f84abc572cb" />
Untuk ip jenkins juga menggunakan reverse proxy seperti backend dan frontend <img width="940" height="393" alt="image" src="https://github.com/user-attachments/assets/a9873ce0-4cb6-4c76-bc61-145e76cb0c99" />

## JENKINS
Membuat pipeline dengan konfigurasi berikut, mengaktifkan triger dari github webhook agar bisa otomatis melakukan perintah apabila mendapat triger dari github webhook
Pipeline menggunakan SCM berupa git dan menggunakan clone repository https<img width="940" height="588" alt="image" src="https://github.com/user-attachments/assets/ea2a4365-1c00-4454-b0d8-97fe0e272acf" />
menggunakan branch main dan membaca script untuk menjalankan build image menggunakan file Jenkinsfile <img width="940" height="588" alt="image" src="https://github.com/user-attachments/assets/1846bc4f-051c-44eb-abe7-006e8801fe1e" />
Kemudian melakukan build image langsung lewat jenkins, maka bisa dilihat tahapan tahapan yang dilakukan berdasarkan script jenkinsfile yang dibuat, dan semua proses bisa dilihat di menu yang tersedia di dashboard jenkins<img width="940" height="588" alt="image" src="https://github.com/user-attachments/assets/3c24d030-e72c-4763-91dd-b400e93f1bc0" />
Apabila frontend dan backend sudah berjalan tanpa ada eror maka website sudah bisa digunakan sengan semestinya termasuk login dan register <img width="940" height="410" alt="image" src="https://github.com/user-attachments/assets/49f86002-9cd9-4f12-9b27-4beffa0f9548" />
setelah itu data yang masuk dari website dapat diakses ke database server dengan username yang dibuat <img width="940" height="588" alt="image" src="https://github.com/user-attachments/assets/aca4e209-59a8-429f-8c98-5394977f92d9" />

