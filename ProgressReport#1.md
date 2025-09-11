# ARM Cortex-M0 SoC Project Development Documentation
## Project Report #1 (11 September 2025)
### Software Simulation
Simulasi yang dilakukan menggunakan testcase yang diberikan oleh ARM, namun setelah dilakukan simulasi tidak menghasilkan output apapun dari kode C yang diberikan. Sehingga dilakukan debugging dengan mas Ahmad dari Xirka, didapatkan bahwa inisialisasi yang dilakukan oleh kode C untuk startup processor dari ARM  untuk mengakses stack memberikan address stack yang salah, sehingga perilaku dari processor tidak dapat menginisialisasi processor itu sendiri dan tidak dapat menjalankan kode dengan baik dan benar yang dapat dilihat pada gambar berikut.
<img width="1029" height="561" alt="image" src="https://github.com/user-attachments/assets/c674a3fd-a3d6-4d65-b885-ada17e74257a" />
Namun, ketika kode hexadecimal tersebut diubah secara paksa dengan testcase dari mas Ahmad yang sudah berhasil didapatkan bahwa processor dapat menjalankan kode haxadecimal tersebut dengan baik dan memberikan output yang sesuai.
### Synthesis RTL
Pada awalnya IP ARM Cortex-M0 untuk SoC (CMSDK) merupakan core yang sudah diintegrasikan dengan berbagai peripherals yang sudah disiapkan untuk membuat SoC berbasis Cortex-M0. Ketika kode yang di extract langsung dari IP ARM tidak dapat dijalankan akibat adanya error bahwa terdapat block memory yang tidak bisa dimplementasikan akibat adanya asynchronous read/write yang digunakan yang dapat dilihat pada gambar berikut. 
<img width="1648" height="959" alt="image" src="https://github.com/user-attachments/assets/a22cc3ab-7df0-464f-93e9-e4a071433702" />
Sehingga agar bisa dilakukan synthesis maka diubah kode tersebut menjadi bentuk yang dapat diimplementasikan menggunakan BRAM. Berikut ini adalah report dari hasil synthesis yang dilakukan menggunakan kode RAM behavioral yang baru.
<img width="1645" height="942" alt="image" src="https://github.com/user-attachments/assets/dd17d872-15f8-4c49-a1ce-68fad2458ea4" />
<img width="1649" height="958" alt="image" src="https://github.com/user-attachments/assets/d25e06f5-3213-4c9b-8671-c1ac6dcb7d18" />
<img width="1649" height="959" alt="image" src="https://github.com/user-attachments/assets/69d20a18-aab0-4b86-86a2-56ef6a31be02" />
<img width="1648" height="959" alt="image" src="https://github.com/user-attachments/assets/69bb1784-4119-490b-8faa-586bc7d7dabf" />
Namun, setelah berkonsultasi dengan mas Ahmad, beliau berpendapat bahwa sebaiknya JANGAN membuat kode baru untuk mengimplementasikan RAM behavioral. Lebih baik menggunakan kode RAM behavorial yang sudah dibuat oleh ARM dan menggunakan block diagram di Vivado untuk menjembatani RAM behavioral yang digunakan oleh ARM agar bisa disynthesis.
