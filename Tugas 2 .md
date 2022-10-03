## Tugas Individu 2 Pengembangan Aplikasi Mobile
### Nama : Fachri Ahmad
### NIM  : 120140124
### Kelas: RB PAM

# Rangkuman
### Closure
Closure merupakan sebuah fungsi yang dieksekusi oleh fungsi lainnya(nested functions) yang membuat fungsi tersebut dapat mengakses/merekam variabel di dalam lexical scope pada fungsi induk (parent function). Closure dibuat ketika ada fungsi yang mengembalikan nilai fungsi lainnya. Fungsi lainnya memiliki akses ke variabel yang dideklarasikan di luar parent function. 
Berikut dicontohkan untuk contoh dari closure 

Kegunaan Closure sendiri yaitu, pertama membuat sebuah fungsi yang dinamis, kita bisa menyusun atau merancang komposisi fungsi beserta kode dapat digunakan berulang kali (reusable). Kedua closure berguna untuk bisa menyimpan data dalam lingkup terpisah dan memanggilnya ketika diperlukan. 


### Immediately Invoked Function Expression
Immediately Invoked Function Expression yang disingkat IIFE adalah bentuk function yang dideklarasikan. 
```
(function () {
    console.log('Hello World');
})();
```
IIFE sering ditemui pada pemrograman JavaScript di browser terutama jika kita menggunakan plugin seperti di JQuery.

Ketika sebuah function dideklarasikan, function tersebut akan ditambahkan ke window object. 

* Docker dekstop ([Download Here](https://docs.docker.com/desktop/windows/install/))
* VcXsrv Windows X server ([Download Here](https://sourceforge.net/projects/vcxsrv/))

1. Clone repository ini, masuk kedalam direktori 
2. Jalankan docker desktop, dan lakukan build image pada terminal dengan perintah
```
docker build -t main
```
3. Sambil menunggu build selesai, selanjutnya setup VcXsrv (X Launcher). Buka aplikasi XLauncher yang sudah diinstall. Pada window awal pilih Multiple Windows dengan display number -1 > next > Start no client > next > centang disable access control > next > finish. Atau juga dapat dilakukan dengan membuka file konfigurasi Xlauncher yang ada di repository ini yaitu file 'Docker.xlaunch'.
4. Setelah build Selesai jalankan container dengan perintah:
```
docker run --rm main
```
5. Container sudah berjalan dan game sudah dapat dimainkan

# Video Demo Container
Berikut akan ditampilkan video demo container.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/HGl9biwuqDI/0.jpg)](https://www.youtube.com/watch?v=HGl9biwuqDI)
