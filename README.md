# tugas.pert.12
| Variable       |    DATA DIRI         |
| ---------------| ----------------     |
| Nama           | Lutpiah Ainus Shiddik|                                     
| NIM            | 312310474            |
| Kelas          | TI.23.A.5            |
| Mata Kuliah    |Basis data            |
## SOAL LATIHAN PRAKTIKUM

## Tabel mahasiswa 
![alt text](<ss/tabel mahasiswa.png>)

## Tabel dosen 
![alt text](<ss/tabel dosen.png>)

## Tabel Mata kuliah
![alt text](<ss/tabel mata kuliah .png>)

## Tabel jadwal mengajar 
![alt text](<ss/tabel jadwal mengajar.png>)

## Tabel KRS mahasiswa
![alt text](<ss/tabel krs mahasiswa.png>)

## *Latihan*

•Lakukan JOIN table Mahasiswa dan Dosen.

•Lakukan JOIN tabel Matakuliah dan Dosen.

•Lakukan JOIN table JadwalMengajar, Dosen, dan Matakuliah.

•Lakukan JOIN tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen.

## *TUGAS PRAKTIKUM*
Buat Script SQL JOIN Table berdasarkan skema data diatas.

*MAHASISWA*
```
INSERT INTO mahasiswa VALUES
    (1812345, 'Ari Santoso', 'L', '1999-10-11', NULL, 'Bekasi', NULL, NULL, 'DS002'),
    (1823456, 'Dina Marlina', 'P', '1998-11-20', NULL, 'Jakarta', NULL, NULL, NULL),
    (1834567, 'Rahmat Hidayat', 'L', '1999-05-10', NULL, 'Bekasi', NULL, NULL, NULL),
    (1845678, 'Jaka Sampurna', 'L', '2000-10-19', NULL, 'Cikarang', NULL, NULL, NULL),
    (1856789, 'Tia Lestari', 'P', '1999-02-15', NULL, 'Karawang', NULL, NULL, NULL),
    (1867890, 'Anton Sinaga', 'L', '1998-06-22', NULL, 'Bekasi', NULL, NULL, NULL),
    (1912345, 'Listia Nastiti', 'P', '2001-10-23', NULL, 'Jakarta', NULL, NULL, NULL),
    (1923456, 'Amira Jarisa', 'P', '2001-01-24', NULL, 'Karawang', NULL, NULL, 'DS004'),
    (1934567, 'Laksana Mardito', 'L', '1999-04-14', NULL, 'Cikarang', NULL, NULL, NULL),
    (1945678, 'Jura Marsina', 'P', '2000-05-10', NULL, 'Cikarang', NULL, NULL, NULL),
    (1956789, 'Dadi Martani', 'L', '2001-08-29', NULL, 'Bekasi', NULL, NULL, 'DS005'),
    (1967890, 'Bayu Laksono', 'L', '1999-07-22', NULL, 'Cikarang', NULL, NULL, 'DS004');

SELECT*FROM Mahasiswa;
```

## OUTPUT
![alt text](<ss/ss 1 mahasiswa.png>)

*DOSEN*
```
insert into dosen values
    ("DS001", "Nofal Arianto"),
    ("DS002", "Ario Talib"),
    ("DS003", "Ayu Rahmadina"),
    ("DS004", "Ratna Kumala"),
    ("DS005", "Vika Prasetyo");

SELECT*FROM Dosen;
```

## OUTPUTNYA 
![alt text](<ss/ss 2 dosen.png>)

*MATA KULIAH*
```
INSERT INTO Matakuliah VALUES
('MK001', 'Algoritma Dan Pemrogaman', 3),
('MK002', 'Praktikum Algoritma Dan Pemrograman', 1),
('MK003', 'Teknologi Basis Data', 3),
('MK004', 'Praktikum Teknologi Basis Data', 1),
('MK005', 'Pemrograman Dasar', 3),
('MK006', 'Pemrograman Berorientasi Objek', 3),
('MK007', 'Struktur Data', 3),
('MK008', 'Arsitektur Komputer', 2);

SELECT * FROM Matakuliah;
```

## OUTPUTNYA 
![alt text](<ss/ss 3 mata kuliah.png>)

*JADWAL MENGAJAR*
```
INSERT INTO JadwalMengajar VALUES
('MK001', 'DS002', 'Senin', '10:00:00', '102'),
('MK002', 'DS002', 'Senin', '13:00:00', 'Lab. 01'),
('MK003', 'DS001', 'Selasa', '08:00:00', '201'),
('MK004', 'DS001', 'Rabu', '10:00:00', 'Lab. 02'),
('MK005', 'DS003', 'Selasa', '10:00:00', 'Lab. 01'),
('MK006', 'DS004', 'Kamis', '09:00:00', 'Lab. 03'),
('MK007', 'DS005', 'Rabu', '08:00:00', '102'),
('MK008', 'DS005', 'Kamis', '13:00:00', '201');

SELECT*FROM JadwalMengajar;
```

## OUTPUTNYA 
![alt text](<ss/ss 4 jadwal mengajar.png>)

*KRS MAHASISWA*
```
INSERT INTO KRSMahasiswa VALUES
(1823456, 'MK001', 'DS002', 3, NULL),
(1823456, 'MK002', 'DS002', 1, NULL),
(1823456, 'MK003', 'DS001', 3, NULL),
(1823456, 'MK004', 'DS001', 3, NULL),
(1823456, 'MK007', 'DS005', 3, NULL),
(1823456, 'MK008', 'DS005', 3, NULL);

SELECT * FROM KRSMahasiswa;
```

## OUTPUTNYA
![alt text](<ss/ss 5 krs mahasiswa.png>)

## *Latihan*

*Lakukan join table Mahasiswa dan Dosen*
```
SELECT Mahasiswa.nim, Mahasiswa.nama, Mahasiswa.jk, Dosen.nama AS "Dosen PA"
FROM Mahasiswa INNER JOIN Dosen ON Dosen.kd_ds = Mahasiswa.kd_ds;
```

## OUTPUTNYA
![alt text](<ss/ss 6 join table mahasiswa dn dosen.png>)


*Lakukan join tabel Matakuliah dan Dosen*
```
SELECT Matakuliah.kd_mk, Matakuliah.nama AS "Nama Matakuliah", Matakuliah.sks, Dosen.nama AS "Nama Dosen Pengampu"
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;
```

## OUTPUTNYA
![alt text](<ss/ss join matakuliah dan dosen.png>)


*Lakukan join table JadwalMengajar, Dosen, dan Mata kuliah*
```
SELECT Matakuliah.kd_mk, Matakuliah.nama, Matakuliah.sks, Dosen.nama AS "Dosen Pengampu"
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;
```

## OUTPUTNYA
![](<ss/ss 8 join table jadwal mengaajar.png>)


Lakukan join tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen
```
SELECT Mahasiswa.nim, Mahasiswa.nama AS "nama", Dosen.nama AS "Dosen PA", Matakuliah.nama AS "Matakuliah", Matakuliah.sks, Dosen.nama AS "Dosen Pengampu"
FROM KRSMahasiswa
JOIN Mahasiswa ON KRSMahasiswa.nim = Mahasiswa.nim
JOIN Matakuliah ON KRSMahasiswa.kd_mk = Matakuliah.kd_mk
JOIN Dosen ON KRSMahasiswa.kd_ds = Dosen.kd_ds;
```

## OUTPUTNYA
![alt text](<ss/ss 9 join table krs.png>)


## *SELESAI*


