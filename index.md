# Bilangan real pada analisis numerik

Komputer yang kita pakai saat ini menyimpan informasi dalam bentuk 1 dan 0 yang dinyatakan dalam tegangan yang disimpan dalam kapasitor. Lantas bagaimana bisa komputer kita saat ini dapat mengerti angka-angka lainnya mulai dari positif, negatif, nol dan bahkan pecahan yang masuk dalam kategori bilangan real? Jawabannya terdapat pada analisis numerik yang akan kita bahas kali ini.

### Analisis Numerik

Dalam mencari solusi setiap persoalan matematika, tidak semuanya dapat dengan mudah dicari dengan menggunakan otak dan tangan ataupun kalkulator. Mungkin menyelesaikan persoalan 5X = 10 dapat dengan mudah dan secara intuisi kita langsung tahu bahwa X = 2, tetapi bagaimana jika persoalannya X45 + X23 + 23 = 0? Hal ini akan sangat sulit untuk didapatkan jawaban pastinya sehingga baik untuk dilakukan pendekatan yang disebut sebagai analisis numerik. Analisis numerik hadir sebagai bagian studi yang mempelajari algoritma penyelesaian masalah matematika melalaui pendekatan pada jawaban aslinya. Sehingga yang didapat bukanlah jawaban “tepat” tetapi adalah jawaban yang sangat mendekati jawaban itu dengan galat yang sekecil mungkin. 

Demikianlah halnya yang dapat dilakukan ketika hendak merepresentasikan bilangan real dalam komputer. Tidak mungkin komputer yang jumlah kapasitornya terbatas dapat berhasil merepresentasikan semua bilangan real yang tidak terbatas. Tidak semua, berarti beberapa dapat direpresentasikan secara sepenuhnya. Ya benar, untuk beberapa jenis bilangan real, komputer dapat merepresentasikannya secara tepat walaupun tetap saja ada batas maksimum dan minimumnya sesuai dengan jumlah kapasitor tadi. 

Berikut kita akan membahas bagaimana beberapa jenis bilangan real direpresentasikan dalam komputer melalui metode analisis numerik serta bagaimana error yang mungkin terjadi di dalamnya.

### Bilangan Bulat
Representasi bilangan bulat dalam computer adalah exact value. Operasi aritmatika didalamnya juga menghasilkan hal yang sama dengan prasyarat (i) hasilnya berada dalam rentang nilai angka yang dapat direpresentasikan dengan jumlah kapasitor dan (ii) setiap operasi pembagian hanya melihat hasil bilangan bulatnya saja dengan mengabaikan angka yang berada dalam koma. 

Bilangan bulat non-negatif akan sangat mudah direpresentasikan. Semua digit direpresentasi-kan dengan bit 0 dan 1, sehingga dapat langsung diinterpretasikan sebagai string biner. Sebagai contoh dengan delapan bit, kita bisa menuliskan
```cpp
00110111 = (1 + 2 + 4 + 16 + 32) (basis 10) = 55 (basis 10)
```

Agar dapat merepresentasikan bilangan negatif juga, maka harus dilakukan pemisahan antara bilangan negatif dan positif. Idenya adalah menganggap bit pertama sebagai penanda apakah bilangan tersebut negatif (yaitu ditandai angka 1) atau positif (yaitu ditandai angka 0). Metode yang paling sering digunakan untuk menhitung nilai representasi sebuah bilangan negatif adalah dengan metode two’s complement  yaitu:
```cpp
	Dalam representasi dari sebuah bilangan bulat positif X, inversi setiap bit (0 ↔ 1), dan tambahkan 1 untuk mendapatkan representasi dari -X .
```

Misalkan kita memiliki delapan buah kapasitor yang merepresentasikan masing-masing sebuah bit maka kita dapat merepresentasikan seperti berikut.
	+2 	= 0000 0010 
	+1 	= 0000 0001 
	0 	= 0000 0000 
	−1 	= 1111 1111 
	−2 	= 1111 1110 
 

Dengan angka maksimum yang dapat direpresentasikan adalah sebesar 2n-1 – 1. Sebagai contoh, untuk 32-bit kita dapat interval angka bulat antara
	2^31 −1 = 2147483647 = (01111111 11111111 11111111 11111111)2  dan 
	−2^31 = −2147483648 = (10000000 00000000 00000000 00000000)2

Sebagian besar compiler tidak memberikan pesan error jika ada angka dalam program yang melewati batas interval angka kecuali dalam beberapa kasus.

Demikianlah cara untuk bilangan bulat real dapat direpresentasikan dalam komputer. Error yang mungkin terjadi adalah saat melakukan pembulatan pada saat pembagian ataupun pada saat operasi yang mengakibatkan hasil berada di luat interval angka minimum dan maksimum yang dapat direpresentasikan oleh komputer. Untuk mengatisipasi error ini maka harus dipertimbangkan metode kita mencari hasil dan melihatnya, apakah memang tetap valid apabila menggunakan operasi tersebut dengan menggunakan bilangan bulat apa tidak. Karena masalah ini pastinya ada dan tidak mungkin untuk dihilangan ketika berbicara bilangan bulat dan komputer.


### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
