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

<img width="1225" height="910" alt="rute" src="https://github.com/user-attachments/assets/3b4a33f2-d0ee-40fa-9eb3-74da28d13079" />

### Perhitungan Detail Subnet A10
Berikut adalah langkah-langkah terperinci untuk menentukan parameter jaringan (Prefix, Network ID, Broadcast, dan Range IP) untuk Subnet A18 di Sayap Bawah:

### 1. Menentukan Prefix (CIDR)

Langkah awal adalah mengidentifikasi prefix CIDR yang paling efisien berdasarkan kebutuhan host. <br>

Kebutuhan Host: 62 Host.

Pencarian Bit Host ($n$): Dengan menggunakan rumus $\text{Jumlah Host} = 2^n - 2$, kita mencari nilai $n$ (jumlah bit host) yang memenuhi kebutuhan.
<br>
- $2^5 = 32$ (Tidak cukup)<br>
- $2^{6} = 64$ (Cukup)<br>
- Hasil: Karena $n = 6$, maka Prefix CIDR dihitung sebagai $32 - 6$, menghasilkan /26.

### 2. Menghitung Block Size (Total IP)<br>
Block size menentukan berapa banyak alamat IP total yang dikonsumsi oleh subnet ini dan berapa langkah lompatan yang akan terjadi pada oktet tertentu. <br>
- Total IP: Rumus $2^{32-\text{Prefix}} = 2^{32-26} = 2^{6} = 64$ IP.
- Lompatan Oktet: Karena 64 IP berada di bawah 256, lompatan terjadi pada oktet keempat. Lompatan (block size) adalah 64.

### 3. Penentuan Network ID (NID) & Broadcast<br>
Alokasi menggunakan Network Address berikutnya yang tersedia: 10.23.4.60.
- Network ID (NID) Awal: Dilanjutkan dari IP yang terakhir tersedia, maka NID dimulai dari 10.23.4.60.
- Next Network (Batas Atas): NID Awal + Block Size (di oktet ke-4) $\rightarrow$ $60 + 64 = 124$. Jadi subnet berikutnya dimulai di 10.23.4.124.
- Broadcast Address (Akhir): Satu angka sebelum Next Network (10.23.4.124). Maka Broadcast-nya adalah 10.23.4.123.d.

### 4. Menentukan Range IP Usable
Range IP yang dapat dialokasikan untuk host.
- IP Pertama (Gateway): Network ID + 1 $\rightarrow$ 10.23.4.61.<br>
- IP Terakhir (Host Terakhir): Broadcast - 1 $\rightarrow$ 10.23.4.122.
