# Jarkom-Modul-4-2025-K-14

| Nama                         | Nrp        |
| ---------------------------- | ---------- |
| Oscaryavat Viryavan          | 5027241053 |
| Mohamad Arkan Zahir Asyafiq  | 5027241120 |

## VLSM 

<img width="1573" height="1086" alt="VLSM" src="https://github.com/user-attachments/assets/8e261e74-a2b0-446b-ad95-d844db1276e0" />

### VLSM Tree

![WhatsApp Image 2025-11-18 at 00 17 12_971dc94a](https://github.com/user-attachments/assets/f1e7dab1-60ca-4ea9-a5cf-a27717a2f733)

Pendekatan subnetting yang digunakan berhasil mengidentifikasi 23 segmen jaringan (subnet). Dari total ruang alamat, 3.219 IP telah dialokasikan, menyisakan 4.030 IP yang dapat digunakan di masa mendatang. Alokasi terbesar didasarkan pada kebutuhan host tertinggi, yang kemudian dikonsolidasikan dalam supernet dengan prefix /20.

---

## CIDR

<img width="1518" height="793" alt="CIDR" src="https://github.com/user-attachments/assets/a7261813-d6fa-4d3f-add9-a8440e32c53e" />

---

### Topologi GNS3

Topologi dibagi menjadi 3 bagian daerah utama yaitu bagian sayap bawah, sayap kanan, dan sayap kiri.

<img width="1913" height="1028" alt="A1 - Presentation - Google Chrome 11_17_2025 11_46_52 PM" src="https://github.com/user-attachments/assets/95176b89-11ce-4263-9e23-220e2ef7c182" />

Untuk meningkatkan efisiensi proses routing, dilakukan agregasi rute (supernetting). Metode ini mengkonsolidasikan beberapa subnet yang lebih kecil menjadi blok alamat yang lebih luas. Konsolidasi dilaksanakan secara bertahap, dimulai dari tingkat terendah topologi (bottom-up), seperti penggabungan subnet berdekatan A22 dengan A23, dan A9 dengan A11, untuk membentuk supernet parsial.

### Sayap Bawah 

<img width="1951" height="487" alt="tahap12" src="https://github.com/user-attachments/assets/88d3ac9f-b631-4148-8f59-07675702acb8" />

### Sayap Kanan

<img width="1951" height="487" alt="tahap12" src="https://github.com/user-attachments/assets/7e5c909a-2e3a-4b79-a491-2fbfa43aac59" />

### Sayap Kiri

<img width="1823" height="350" alt="ahap13" src="https://github.com/user-attachments/assets/126ef42f-591d-42c9-bfe9-af13a27c2c15" />

### Gabungan Ketiga Sayap

<img width="1806" height="233" alt="gabungan3" src="https://github.com/user-attachments/assets/6f3f248f-d3ac-43a8-9d1b-d33683878b73" />

Setelah proses supernetting selesai, kami berhasil merangkum semua jaringan menjadi tiga Blok Supernet Mayor. Rangkuman ini akan diinput ke router utama (Amonsul) untuk mengurangi jumlah entri dalam tabel routing:

> Blok /20 (10.91.0.0) mencakup 2318 host di Sayap Bawah.

> Blok /21 (10.91.16.0) mencakup 1102 host di Sayap Kanan.

> Blok /22 (10.91.24.0) mencakup 610 host di Sayap Kiri.

---

## Menghitung Subnet

