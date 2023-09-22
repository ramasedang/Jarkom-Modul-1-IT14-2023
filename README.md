# Jarkom-Modul-1-IT14-2023

 Modul 1 Jarkom IT14
* Moh. Sulthan Arief Rahmatullah - 5027211045
* Fransiskus Benyamin Sitompul - 5027211021

## No 1
### Soal
User melakukan berbagai aktivitas dengan menggunakan protokol FTP.
nc 10.21.78.111 12345
diberikan file bernama soal1.pcapng

### Analisa Soal

Soal memberi hint bahwa user melakukan berbagai aktivitas dengan protokol FTP, dan diberikan file `.pcap` maka kita bisa menganalisis paket dengan wireshark

### Jawaban
Jadi, kita buka file pcap nya dan melakukan filter menggunakan keyword ftp 

![8d14d7e7-0a9d-4026-8056-6ae7283d575d](https://github.com/ramasedang/Jarkom-Modul-1-IT14-2023/assets/73869671/c0147a31-dfe4-4f5b-8fc0-fad3e991818e)
![4c049d1e-423d-420d-9957-6a4406c371a8](https://github.com/ramasedang/Jarkom-Modul-1-IT14-2023/assets/73869671/59d92c06-3ed0-446c-b010-d2fd51f9e5a7)

lalu setelah menjawab beberapa pertanyaan mengenai sequence number dan acknowlegement number dari request store file dan responsenya, akan diberikan flag
### Kendala
Tidak ada
## No 2
### Soal
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

### Analisa Soal

Soal menyuruh untuk mencari webserver yang digunakan, dan diberikan file `.pcap` maka kemungkinan kita bisa mendapatkan informasi tersebut dari analisis paket dengan wireshark

### Jawaban
Jadi tinggal buka file pcap nya dan gunakan filter http untuk mencari paket dari http, dan follow http stream nya

[![JJKMyu4.md.png](https://iili.io/JJKMyu4.md.png)](https://freeimage.host/i/JJKMyu4)
[![JJKVowQ.md.png](https://iili.io/JJKVowQ.md.png)](https://freeimage.host/i/JJKVowQ)

didapatkan `gunicorn` sebagai webserver, dan jika dimasukan mendapatkan flag nya
### Kendala
Tidak ada
## No 3
### Soal

Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
* Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
* Protokol layer transport apa yang digunakan?

### Analisa Soal

Diberikan file pcap dan kita disuruh untuk menghitung banyak paket sesuai soal dan protokol yang digunakan

### Jawaban
Pertama kita buka file nya di wireshark dan masukan filter yang sesuai yaitun`(ip.src == 239.255.255.250 && udp.port == 3702) || (ip.dst == 239.255.255.250 && udp.port == 3702)`

Filter Wireshark yang Anda berikan ini digunakan untuk menangkap paket-paket yang sesuai dengan kondisi yang ditentukan. Filter ini terdiri dari dua bagian yang dihubungkan dengan operator "||" (atau).

* `(ip.src == 239.255.255.250 && udp.port == 3702)`: Bagian pertama dari filter ini akan menangkap paket-paket yang memiliki alamat sumber IP 239.255.255.250 dan port UDP 3702. Artinya, ini akan menangkap paket yang dikirim dari alamat IP tersebut dengan tujuan port UDP 3702.

* `(ip.dst == 239.255.255.250 && udp.port == 3702)`: Bagian kedua dari filter ini akan menangkap paket-paket yang memiliki alamat tujuan IP 239.255.255.250 dan port UDP 3702. Artinya, ini akan menangkap paket yang ditujukan ke alamat IP tersebut dengan tujuan port UDP 3702.

[![JJKwr9n.md.png](https://iili.io/JJKwr9n.md.png)](https://freeimage.host/i/JJKwr9n)

lalu setelah memasukan filter didapatkan paket dengan protkol UDP dan banyaknya berjumlah 21
### Kendala

Tidak ada
## No 4
### Soal
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
### Analisa Soal
Kita diharuskan mencari nilsi checksum dari paket nomer 130

### Jawaban
kita tinggal menggunakan filter `frame.number == 130`

[![JJKO2bs.md.png](https://iili.io/JJKO2bs.md.png)](https://freeimage.host/i/JJKO2bs)

Setelah itu tinggal di chcek 1 per satu checksum nya dan di inputkan ke soal hingga mendapatkan flag
### Kendala

Tidak ada
## No 5
## Soal
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
Port berapakah pada server yang digunakan untuk service SMTP?
Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

## Analisa Soal
Terdapat file zip dan file pcap, file zip nya tidak bisa di ekstrak karena ada passwordnya kemungkinan passowrdnya ada pada salah satu packet di file pcap tersebut

## Jawaban
Bukan file pcap dengan wireshark dan cari 

[![JJKO6B4.md.png](https://iili.io/JJKO6B4.md.png)](https://freeimage.host/i/JJKO6B4)

Jika dilihat pada hasil follow http stream pada salah satu paket di dapatkan sebuah password yang misterius yang diakhiri `=` yang artinya kemungkinan besar base64, dan jika dicoba di decode

[![JJKeRyX.md.png](https://iili.io/JJKeRyX.md.png)](https://freeimage.host/i/JJKeRyX)

dan jika dimasukan ke password zip

[![JJKek6Q.md.png](https://iili.io/JJKek6Q.md.png)](https://freeimage.host/i/JJKek6Q)

didapatkan nc baru yang menuju ke pertanyaan selanjutkan

[![JJKkCH7.md.png](https://iili.io/JJKkCH7.md.png)](https://freeimage.host/i/JJKkCH7)

setelah menjawab pertanyaan tersebut sesuai file pcap nya maka akan didapatkan flag

### Kendala

Lumayan kesulitan saat mencari password zip
## No 6
## No 7
### Soal
Berapa jumlah packet yang menuju IP 184.87.193.88?

### Analisa Soal
Soal sudah cukup jelas kita harus membuat filter untuk menunjukan paket yg menuju ke ip tersebut saja

### Jawaban
Bukan wireshark lalu gunakan filter `ip.dst == 184.87.193.88`

[![JJK6kPe.md.png](https://iili.io/JJK6kPe.md.png)](https://freeimage.host/i/JJK6kPe)

Tinggal di hitung saja dan masukan ke nc nya dan didapatkan flag nya
### Kendala

Tidak ada
## No 8
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
### Analisan Soal

kita disuruh untuk membuat query filter untuk wireshark agar sesuai dengan soal

### Jawaban
`tcp.dstport == 80 || udp.dstport == 80`

[![JJKPRfe.md.png](https://iili.io/JJKPRfe.md.png)](https://freeimage.host/i/JJKPRfe)

Jika dimasukkan ke dalam nc ternyata benar

[![JJKP0bV.md.png](https://iili.io/JJKP0bV.md.png)](https://freeimage.host/i/JJKP0bV)
### Kendala

Tidak ada
## No 9
### Soal
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

### Analisa Soal
Kita disuruh membuat query yang sesuai dengan soal

### Jawaban
`ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

[![JJKiwG9.md.png](https://iili.io/JJKiwG9.md.png)](https://freeimage.host/i/JJKiwG9)

Query tersebut sudah sesuai soal

ip.src == 10.51.40.1: Ini akan menangkap paket-paket yang memiliki alamat IP sumber 10.51.40.1, yang artinya paket-paket yang dikirim dari alamat IP tersebut.

ip.dst != 10.39.55.34: Kondisi ini akan menangkap paket-paket yang memiliki alamat IP tujuan yang tidak sama dengan 10.39.55.34. Jadi, paket-paket dengan alamat IP tujuan selain dari 10.39.55.34 akan ditangkap.
### Kendala

Tidak ada
## No 10
### Soal
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
### Analisa Soal
Kita diharuskan mencari username dan password yang benar yang digunakan untuk login portokol telnet

### Jawaban

Buka wireshark dan ketikan `telnet` pada filters, lalu cari 1 per satu paket yang benar

[![JJKibuR.md.png](https://iili.io/JJKibuR.md.png)](https://freeimage.host/i/JJKibuR)

terdapat beberapa password dan username yang salah tapi yang benar ternyata yang

dhafin:kesayangannyak0k0

[![JJKs0MP.md.png](https://iili.io/JJKs0MP.md.png)](https://freeimage.host/i/JJKs0MP)
### Kendala

Tidak ada
