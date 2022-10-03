## Tugas Individu 2 Pengembangan Aplikasi Mobile
### Nama : Fachri Ahmad
### NIM  : 120140124
### Kelas: RB PAM

# Rangkuman
## Closure
Closure merupakan sebuah fungsi yang dieksekusi oleh fungsi lainnya(nested functions) yang membuat fungsi tersebut dapat mengakses/merekam variabel di dalam lexical scope pada fungsi induk (parent function). Closure dibuat ketika ada fungsi yang mengembalikan nilai fungsi lainnya. Fungsi lainnya memiliki akses ke variabel yang dideklarasikan di luar parent function. 
Berikut dicontohkan untuk contoh dari closure 

Kegunaan Closure sendiri yaitu, pertama membuat sebuah fungsi yang dinamis, kita bisa menyusun atau merancang komposisi fungsi beserta kode dapat digunakan berulang kali (reusable). Kedua closure berguna untuk bisa menyimpan data dalam lingkup terpisah dan memanggilnya ketika diperlukan. 


## Immediately Invoked Function Expression
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

## First-Class Function
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

## Higher-order function
Higher-order function merupakan function yang memiliki function sebagai argument ataupun function sebagai nilai return dari function tersebut. Function yang menjadi argument atau nilai return dari sebuah higher order function disebut callback function. Ada beberapa higher order function seperti array, find, filter dan yang lain sebagainya. Find adalah  sebuah function array yang mengembalikan sebuah nilai yang sudah ditentukan. Contoh penerapan find sendiri adalah sebagai berikut 
```
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const number = numbers.find(number => number >= 5 
console.log(number) // menampilkan angka 5
```
Contoh script diatas m rayyyenunjukan cara kita mencari sebuah angka yaitu angka 5, angka 5 dari array  numbers yang berisi angka dari 1 - 10. Nilai dari hasil pencarian tersebut nantinya di assign ke konstanta number dan kemudian ditampilkan menggunakan console.log. Kemudian setelah find ada yang nama nya filter. Filter adalah contoh lain dari higher order function. Filter akan memilah nilai yang ditentukan lalu dikembalikan menjadi sebuah array yang baru. Contoh penerapan filter sendiri adalah sebagai berikut
```
const numbers = [1, 23, 21, 51, 43, 2, 54, 34]
const newNumbers = numbers.filter((number) => number > 40)
console.log(newNumbers) // [ 51, 43, 54 ]
```
Array Number berisi nilai acak. Dalam contoh ini, disini kita ingin mencari nilai lebih dari    sama dengan 40 dari array numbers. Hasil pencarian tersebut akan menghasilkan nilai array yang baru newNumbers yang berisikan [51, 43, 54].

## Execution Contex
*Execution context* merupakan konteks atau lingkungan dimana javascript di eksekusi. *Execution Context* merupakan pembungkus yang mengelola kode yang sedang di run atau dijalankan. Execution context terbagi 2 yaitu *Global Execution Context* dan *Local Execution Context*. Kemudian di dalam javaScript ada 2 phase pada saat Execution Context yaitu *Creation phase* dan *execution phases*

## Execution Stack
Execution Stack dikenal dengan call stack , melacak semua Execution context yang dibuat selama siklus script. JavaScript merupakan bahasa utas tunggal, yang berarti bahwa ia hanya mampu menjalankan satu tugas pada satu waktu. Jadi, ketika tindakan, fungsi, dan peristiwa lain terjadi, Execution context  dibuat untuk masing-masing event. Karena sifat JavaScript single-threaded,tumpukan stack eksekusi  yang akan dieksekusi yang dikenal sebagai Execution Stack.
Saat skrip dimuat di browser, konteks global dibuat sebagai konteks default tempat mesin JavaScript mulai mengeksekusi kode dan ditempatkan dibagian bawah Execution Stack.

Engine JavaScript kemudian mencari panggilan fungsi dalam kode. Setiap panggilan fungsi, FEC baru dibuat untuk fungsi itu dan kemudian ditempatkan diatas execution context yang dijalankan.
Execution context  di bagian atas Execution Stack menjadi execution context aktif selesai, engine JavaScript mengeluarkan fungsi execution context tertentu dari execution stack, kemudian bergerak ke arah berikutnya di bawah nya dan seterusnya. 

## Event Loop
Event Loop merupakan proses yang hanya memiliki 1 thread dengan banyak loop proses yang tidak terhingga atau unlimited. Pada cara ini kita hanya melakukan satu tugas yang mana selanjutnya menghandle banyak regu kita melakukan seleksi prioritas terhadap tugas yang dilakukan atau dikerjakan. Hal ini dilakukan untuk bisa membuat proses ini menjadi aman terhadap tumpang tindih satu proses lainya. Untuk beberapa event loop ini memberikan kinerja yang lebih bagus dibandingkan konkurensi karena tidak ada blok yang terjadi. 
Untuk beberapa kasus event loop ini memberikan kinerja yang lebih bagus dibandingkan konkurensi karena tidak ada blok yang terjadi. 

# ![IMAGE ALT TEXT HERE](https://miro.medium.com/max/1100/1*yX52mSzTZXkIK_qRxxoFvg.png)

#### Jika dijelaskan maka secara umum event loop memiliki alur atau proses sebagai berikut,
1. Event emiter atau sumber dari event akan memasukan task ke antrian event. Task-task ini akan mengantri untuk dilakukanya proses eksekusi pada proses loop selanjutnya.
2. Event loop akan mengambil task dari event queue dan memprosesnya berdasarkan handler yang ada. Pada proses ini akan diprioritaskan pengerjaan dengan menggunakan algoritma tertentu. Proses yang terjadi yaitu sekuensial satu persatu dan loop akan segera kembali setelah registrasi callback pada handler dari proses.
3. Jika proses telah usai, event loop akan men-trigger callback dan memberikan informasi proses selesai dan mengirimkan hasil kepada pemanggil proses ini. 

Pada awalnya event loop banyak diadopsi oleh teknologi pada javascript. Hampir semua framework yang berhubungan dengan front-end digunakan dengan tujuan optimasi terhadap resource yang dipakai. Node.js atau Nginx adalah pemakai event loop yang dilakukan pada proses ascronousnya.


## Callbacks
Callbacks adalah kode yang biasanya berupa fungsi tapi tidak selalu yang didaftarkan ke kode lain yang diharapkan untuk memanggil balik (call back) kode tersebut kemudian waktu.
Callback merupakan bagian penting dalam event driven system, namun dapat juga digunakan di luar konteks tersebut. 
Dalam JavaScript untuk client side, semua kode yang tertulis dalam event properties suatu HTML (onload, onchange, onkeydown, onkeyup, dll) yang mana merupakan callback yang akan dipanggil ketika event terkait terjadi.
Di Luar itu, callback dapat diberikan sebagai argumen terhadap fungsi yang nantinya akan dipanggil oleh fungsi tersebut. Kinerja dari callback sendiri sebenarnya mirip-mirip dengan event driven, namun event event disini tidak tertulis secara eksplisit

## Promise
Dari katanya promise merupakan sebuah janji, promise sendiri cara kerjanya sama seperti selayaknya kita memiliki janji dengan seseorang. Sebagai contoh ketika kita membuat janji dengan seorang teman untuk belajar bersama. Terdapat beberapa kemungkinan terjadi terhadap janji yang kita buat yaitu kita belum bisa memenuhi janjinya, kita sudah memenuhi janjinya, atau kita tidak bisa memenuhi janji bekerja kelompok. 

Seperti janji, terdapat 3 kemungkinan state yang dapat terjadi didalam promise , antara lain:
* Pending -> Dalam keadaan awal, tidak terpenuhi atau tidak ditolak.
* Fulfilled -> Terpenuhi atau sukses.
* Rejected -> Tidak terpenuhi atau gagal.

Berikut saya lampirkan untuk contoh penggunaan promise
```
let promise = "Standup"

let p = new Promise((resolve, reject) => {
    setTimeout(() => {
        if (janji === "Standup") {
            resolve("Penonton ketawa")
        }  else {
            reject("Anda tidak Standup")
        }
    }, 2000)
})

p.then((result) => {
    alert(result)
}).catch((error) => {
    alert(error)
})
```
## Async/Await
Async/Await merupakan salah satu fitur baru dari javascript yang digunakan untuk bisa menangani hasil dari sebuah promise. Cara penggunaannya adalah dengan menambahkan kata __asy__ didepan sebuah fungsi untuk mengubahnya menjadi *asynchronous*
Sedangkan await sendiri berfungsi untuk menunda sebuah kode dijalankan, sampai proses *asynchronous*  berhasil. Dibawah ini akan ditunjukan penggunaan async/await, disini kita akan melihat ada fungsi baru yang akan diubah menjadi *asynchronous*. Di Dalam fungsi tersebut akan dilakukan pemanggilan fungsi *createPost* dan *getPost*. Tambahkan kata kunci await didepan fungsi *createPos*.

```
const posts = [
    {
      title: "Post one",
      body: "This is post one"
    },
    {
      title: "Post two",
      body: "This is post two"
    }
  ]
  
  const createPost = post => {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        posts.push(post)
        const error = false
        if(!error) {
          resolve()
        }else{
          reject()
        }
      }, 2000)
    })
  }
  
  const getPosts = () => {
    setTimeout(() => {
      posts.forEach(post => {
        console.log(post)
      })
    }, 1000)
  }
  
  const newPost = {
    title: "Post three"
    body: "This is post three"
  }
  
  const init = async() => {
    await createPost(newPost)
    getPost()
  }
  
  init()
```
