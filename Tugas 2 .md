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
```
function katakanHay() {
    console.log('Hello World');

}
window.katakanHay;
```
Tidak hanya function, ketika kita mendeklarasikan sebuah variabel, variabel tersebut juga ditambahkan ke windows object
```

let word = 'Hi World';

console.log(windows.word);
```
Hal ini tidak akan terlalu menjadi masalah jika nama function dan variabel tersebut berbeda. Akan tetapi seiring berjalannya waktu baris code pada sebuah proyek JavaScript bisa menjadi berubah sangat panjang dan komplek, kita akan sulit untuk mengingat setiap nama dari function dan variabel yang telah dideklarasikan. Sehingga sangat mungkin terjadi kita memberi satu nama yang sama untuk dua function berbeda. Oleh karenanya IIFE memiliki tujuan untuk menghindari Global NameSpace Pollution yang dapat berakibat terjadinya name collisions, yaitu terjadinya tabrakan antara nama function satu dengan function lai ataupun nama function dengan nama variabel.

### First-Class Function
Sebuah Objek disebut atau bisa dikatakan First-Class Function apabila dipenuhi berbagai syarat sebagai berikut, Pertama yaitu mendukung anonymous function atau function yang tidak memiliki definisi nama. Kedua mendukung pengiriman function sebagai argumen dari function lain. Ketiga function sebagai nilai kembalian dari function lain, Kemudian menyimpan function sebagai variabel atau dalam struktur data lainnya.
Berikut adalah contoh kode penerapan first class function pada javascript
* Menetapkan fungsi ke variabel
```
const foo = () => {
    console.log("foobar");
  };
  foo(); // Invoke it using the variable
  // foobar
```
Disini kami menetapkan fungsi anonim dalam variabel, lalu kami menggunakan variabel itu untuk memanggil fungsi dengan menambahkan tanda kurung () di bagian akhir.
* Melewati fungsi sebagai argumen
```
function sayHello() {
    return "Hello World ";
  }
  function greeting(helloMessage, name) {
    console.log(helloMessage() + name);
  }
   
  greeting(sayHello, "JavaScript!");
  // Hello 
```

Disini `sayhello()` diteruskan sebagai argumen ke greating() fungsi, kemudian ini menjelaskan bagaimana disini memperlakukan fungsi sebagai nilai.

* Mengembalikan Fungsi
```
function sayHello() {
    return () => {
      console.log("HelloWorld !");
    };
  }
```
Dalam contoh ini, kira mengembalikan fungsi-dari fungsi lain, kami dapat mengembalikan fungsi karena fungsi dalam javascript diperlakukan sebagai nilai.



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
