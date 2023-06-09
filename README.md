# TUGAS 4 Experiment Chapter 3

Nama : Yulia Eka Ardhani

Kelas : TI 3C / 21

NIM : 2041720064

## Langkah-langkah praktikum

### I. Uji Coba PySpark

Menjalankan service dari pyspark terlebih dahulu dengan perintah :

<code>cd spark-2.0.0-bin-hadoop2.7</code>

<code>bin/pyspark</code>

![](ss/ss1.png)

1. Uji coba  <code> Accumulator.py </code>
![](ss/ss2.png)

**sc** : singkatan dari SparkContext, ini adalah objek utama dalam pemrograman dengan Apache Spark. Ini digunakan untuk menginisialisasi aplikasi Spark dan membuat RDD (Resilient Distributed Datasets) yang mendukung komputasi paralel.

**accumulator** : objek shared variable yang digunakan dalam Apache Spark untuk agregasi asinkron nilai dari beberapa executor (pekerja) di sepanjang sebuah job (tugas). Biasanya digunakan untuk menghitung statistik yang kompleks atau mengakumulasikan hasil dalam loop.

**parallelize** : method yang digunakan pada objek SparkContext untuk membuat RDD dari koleksi data yang ada dalam program. RDD ini nantinya akan didistribusikan secara paralel pada executor (pekerja) yang tersedia.

**lambda** : fungsi anonim yang sering digunakan dalam pemrograman fungsional dan pemrograman paralel. Biasanya digunakan untuk melakukan operasi yang sederhana dan terbatas pada sebuah data, sehingga sangat cocok untuk dijalankan di dalam RDD.

**value** : tipe data dasar dalam Spark. Ini mewakili nilai tunggal dan dapat berupa tipe data apapun seperti integer, float, string, boolean, atau objek Python. Ini sering digunakan sebagai argument dalam method yang membutuhkan input data seperti map atau reduceByKey.

2. Uji coba <code> BroadCast.py </code>
![](ss/ss3.png)

**broadcast** : sebuah fungsi dalam Spark yang digunakan untuk mendistribusikan variabel secara efisien ke setiap node dalam sebuah cluster, sehingga setiap node dapat mengakses variabel tersebut dengan cepat tanpa perlu menyalinnya berkali-kali.

**list** : tipe data yang umum digunakan dalam bahasa pemrograman Python untuk menyimpan sejumlah nilai dalam satu variabel. List dapat berisi elemen-elemen dengan tipe data yang berbeda, dan dapat diakses menggunakan indeks.

**range**: sebuah fungsi dalam bahasa pemrograman Python yang digunakan untuk menghasilkan deret bilangan bulat secara berurutan, dengan argumen yang dapat ditentukan untuk memulai, mengakhiri, dan menentukan langkah antar bilangan. Deret bilangan ini berguna dalam banyak skenario pemrograman, seperti pengulangan for-loop.


3. Uji coba <code> LogAnalytics.py </code>
![](ss/ss4.png)
![](ss/ss5.png)

**textFile** : sebuah fungsi dalam Spark yang digunakan untuk membaca file teks dan mengembalikan RDD (Resilient Distributed Datasets) yang berisi baris-baris dalam file tersebut sebagai elemen-elemennya.

**filter** : sebuah fungsi dalam Spark yang digunakan untuk memfilter elemen-elemen dalam RDD berdasarkan kondisi tertentu. Fungsi ini mengembalikan RDD yang hanya berisi elemen-elemen yang memenuhi kondisi tersebut.

**cache** : sebuah metode dalam Spark yang digunakan untuk menyimpan RDD di dalam memori cache. Hal ini dapat meningkatkan performa komputasi karena RDD yang sering digunakan dapat diakses dengan lebih cepat daripada membacanya dari disk.

**count** : sebuah fungsi dalam Spark yang digunakan untuk menghitung jumlah elemen dalam sebuah RDD dan mengembalikan hasilnya sebagai bilangan bulat.

4. Uji coba <code> PairRDD.py </code>
![](ss/ss6.png)

**map** : sebuah fungsi dalam Spark yang digunakan untuk melakukan transformasi pada setiap elemen dalam RDD dengan menggunakan sebuah fungsi yang diberikan sebagai argumen. Fungsi ini mengembalikan RDD baru yang berisi hasil transformasi tersebut.

**len** : sebuah fungsi dalam bahasa pemrograman Python yang digunakan untuk menghitung jumlah elemen dalam sebuah list atau tipe data lain yang dapat dihitung panjangnya.

**collect** : sebuah fungsi dalam Spark yang digunakan untuk mengambil semua elemen dalam sebuah RDD dan mengembalikan hasilnya sebagai list pada driver program. Fungsi ini tidak disarankan digunakan pada RDD yang sangat besar, karena dapat mengakibatkan out-of-memory error.

**keys** : sebuah metode pada tipe data dictionary dalam bahasa pemrograman Python yang mengembalikan sebuah list yang berisi semua kunci (keys) dalam dictionary tersebut.

**values** : sebuah metode pada tipe data dictionary dalam bahasa pemrograman Python yang mengembalikan sebuah list yang berisi semua nilai (values) dalam dictionary tersebut.

5. Uji coba <code> UnderstandingRDD.py </code>
![](ss/ss7.png)
![](ss/ss8.png)
![](ss/ss9.png)

**defaultParallelism** : sebuah atribut dalam Spark yang menentukan jumlah partisi yang digunakan secara default saat membuat RDD baru. Nilai defaultnya adalah jumlah core yang tersedia di cluster.

**getNumPartitions** : sebuah metode dalam Spark yang digunakan untuk mengambil jumlah partisi dalam sebuah RDD.

**mapPartitionsWithIndex** : sebuah fungsi dalam Spark yang mirip dengan fungsi map, namun berbeda dalam cara penggunaannya. Fungsi ini memungkinkan pengguna untuk mengakses indeks partisi RDD saat melakukan transformasi pada setiap partisinya.

**repartition** : sebuah fungsi dalam Spark yang digunakan untuk mengubah jumlah partisi sebuah RDD menjadi jumlah yang diinginkan. Fungsi ini dapat menyebabkan pengiriman data melintasi jaringan dan dapat memakan waktu yang lama.

**coalesce** : sebuah fungsi dalam Spark yang digunakan untuk menggabungkan beberapa partisi dalam sebuah RDD menjadi satu partisi. Fungsi ini lebih efisien daripada repartition, karena tidak menyebabkan pengiriman data melintasi jaringan.

**toDebugString** : sebuah metode dalam Spark yang digunakan untuk mengambil string representasi dari RDD yang berisi informasi tentang partisi-partisi dalam RDD, lokasi masing-masing partisi, dan transformasi yang telah dilakukan pada RDD tersebut.

6. Uji coba <code> WordCount.py </code>
![](ss/ss10.png)
![](ss/ss10_1.png)

**flatMap** : sebuah fungsi dalam Spark yang mirip dengan fungsi map, namun berbeda dalam cara penggunaannya. Fungsi ini digunakan untuk menghasilkan nol atau lebih elemen dari setiap elemen dalam RDD yang diberikan sebagai argumen. Fungsi ini mengembalikan RDD baru yang berisi semua elemen yang dihasilkan.

**reduceByKey** : sebuah fungsi dalam Spark yang digunakan untuk menghitung agregasi nilai pada tiap kunci (key) dalam sebuah RDD. Fungsi ini mengelompokkan elemen berdasarkan kunci yang sama, dan menggabungkan nilai-nilai untuk setiap kunci menggunakan sebuah fungsi agregasi tertentu. Hasilnya adalah RDD baru yang berisi setiap kunci dengan nilai agregasi yang sesuai.

**split** : sebuah fungsi dalam bahasa pemrograman Python yang digunakan untuk membagi sebuah string menjadi beberapa substring berdasarkan sebuah karakter pemisah     (separator). Fungsi ini mengembalikan sebuah list dari substring-substring tersebut.


### II. Uji Coba Scala

Menjalankan service dari sparkshell terlebih dahulu dengan perintah :

<code>cd spark-2.0.0-bin-hadoop2.7</code>

<code>bin/spark-shell</code>

![](ss/ss11.png)

Jalankan juga service cloudera manager dengan perintah:

<code> sudo /home/cloudera/cloudera-manager --express --force </code>
kemudian login pada browser. Setelah itu, jalankan service HDFS

![](ss/ss12.png)
![](ss/ss13.png)

1. Uji coba <code> SystemCommandsOutput.scala </code>
![](ss/ss14.png)
![](ss/ss15.png)
![](ss/ss16.png)

2. Uji coba <code> SystemCommandsReturnCode.scala </code>
![](ss/ss17.png)
![](ss/ss18.png)

