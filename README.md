# TUGAS10-SBD-19.B2
# MONICA PUTRI UTAMI 
# 311910190
DI TUGAS PERTEMUAN 10 INI SAYA AKAN MEMBACKUP DATA BASE DENGAN SQL PROMPT.
1. LANGKAH PERTAMA SAYA AKAN MEMBUKA ATAU MENJALANKAN CMDN SAYA DAN MELIHAT DATABASE SAYA 

![image](https://user-images.githubusercontent.com/81574673/125326822-ab02e980-e36c-11eb-86e2-d32d306c0684.png)

2. BERIKUT SAYA MENGAMBIL DATABASES YAITU BOUTIQUE_AMANAH DAN MELIHAT SALAH SATU TABLE (TABEL PELANGGAN) YANG AKAN SAYA BACKUP.DAN MENGUNCI TABLE TERSEBUT DENGAN PERINTAH 'LOCK TABLE PELANGGAN WRITE'

![image](https://user-images.githubusercontent.com/81574673/125326908-c1a94080-e36c-11eb-9c2d-9d932e268667.png)

3.SELANJUTNYA BACKUP TABLE DATABASE TERSEBUT DENGAN PERINTAH 'SELECT * INTO OUTLIFE 'pelanggan' FROM PELANGGAN'

![image](https://user-images.githubusercontent.com/81574673/125327706-9a9f3e80-e36d-11eb-9ce4-8ecdc2416068.png)

Jika proses backup berhasil maka akan muncul file backuppada direktori C:\xampp\mysql\data\monica_311910190

![image](https://user-images.githubusercontent.com/81574673/125328103-1c8f6780-e36e-11eb-92d5-5033c0e1b7a0.png)

4. LALU KITA MERESTORE DATA BASES KITA DENGAN PERINTAH 'LOAD DATA INFILE 'pelanggan' INTO TABLE PELANGGAN'

![image](https://user-images.githubusercontent.com/81574673/125328459-8871d000-e36e-11eb-8706-cc8a1a1ddffe.png)

![image](https://user-images.githubusercontent.com/81574673/125328786-ec949400-e36e-11eb-96dc-989d75da377c.png)

SELANJUTNYA MEMBACKUP DAN MERESTORE MENGGUNAKAN 'MYSQLDUMP'

1.Jalankan shell atau commad-prompt dan ketikkan perintah berikut untuk memulai dump database : MySQLDUMP -u root -p monica_311910190 > backup1.sql

![image](https://user-images.githubusercontent.com/81574673/125329209-675daf00-e36f-11eb-9def-b2e17045056c.png)

Jika proses backup berhasil maka akan muncul file backuppada direktori C:\xampp\mysql\bin\backup1.sql

![image](https://user-images.githubusercontent.com/81574673/125329497-c3c0ce80-e36f-11eb-8f45-1e8304c0efce.png)

2.Data yang telah di-backup dapat di restrore kembali ke dalam database dengan perintah : MySQLdump –u root –p monica_311910190 < C:\xampp\mysql\bin\backup1.sql

![image](https://user-images.githubusercontent.com/81574673/125330116-890b6600-e370-11eb-9013-6014c735e9f6.png)

# Backup Database MySQL Otomatis dengan cronjob

# Cron adalah tool di sistem operasi berbasis UNIX (Linux, Ubuntu, dan lain-lain) yang berfungsi untuk menjalankan task atau script secara otomatis.
# Jadi untuk menjalankannya kita mendownload aplikasi cronjob terlebih dahulu.
# 1.Tulisakan script cron job untuk melakukan backup otomatis setiap hari minggu jam 12 malam.Dan ini perintahnya:

0 0 * * 7 mysqldump -u root -p monica_311910190 > backup1.sql
