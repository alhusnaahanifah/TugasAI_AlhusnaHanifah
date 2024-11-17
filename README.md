Nama : ALHUSNA HANIFAH

NPM : 2208107010060

Review CNN

# Convolutional Neural Network (CNN)

Convolutional Neural Network (CNN) adalah algoritma deep learning yang dirancang untuk memproses data berbentuk grid, seperti gambar atau video, dengan fokus utama pada pengenalan pola visual. CNN bekerja dengan mengekstraksi fitur penting dari data input secara hierarkis melalui beberapa tahapan utama.

![image](https://github.com/user-attachments/assets/df68a9fb-10d5-43ef-b784-0f121f91d929)

## Tahapan CNN
1. Convolution
2. Max Pooling
3. Flattening
4. Full Connection

## Penjelasan
1. Tahap Convolution

   Pada tahap ini terjadi proses perkalian pixel pada gambar dengan **featur detector**. Feature detector atau yang disebut juga filter/kernel merupakan sebuah matriks yang bisa mengonversi dari gambar awal menjadi feature map. Tujuannya adalah untuk mencari atau mendeteksi informasi (fitur) tertentu yang bersifat integral. 
   - Hasil Konvolusi adalah **feature map** yang menyimpan informasi penting dari gambar.
   - Aktivasi **ReLU** (Rectified  Linear Unit) diterapkan untuk memutuskan ikatan linearitas yang terjadi dari proses feature detection. Hal ini akan memudahkan mencari nilai optimumnya (baik minimum atau maksimum)

3. Max Pooling
   - Max pooling mengambil nilai maksimum dalam area tertentu (biasanya 2x2), mempertahankan fitur paling menonjol sambil mengurangi dimensi data.
   - Proses ini membuat model lebih cepat, lebih sederhana, dan lebih toleran terhadap perubahan posisi, rotasi, atau ukuran objek dalam gambar. Max Pooling tidak peduli apakah gambarnya miring ke kiri, kanan, diputar, dikecilkan, dibesarkan, berbeda teksturnya, warnanya dan lain sebagainya.
     
4. Flattening
   - Matriks dari pooling layer diubah menjadi **vektor satu dimensi**. Vektor ini akan menjadi input ke tahap berikutnya, yaitu jaringan saraf buatan (Artificial Neural Network/ANN)
   - Jadi jika sebuah pooling layer berukuran 3×3 matriks, maka ia akan menjadi 1 vektor dengan 9 baris. Jika ada 10 pooling layer dengan ukuran yang sama (3×3), maka akan ada 1 vektor dengan 90 baris sebagai input untuk ANN.
     
5. Full Connection
   - Dalam lapisan fully connected, setiap neuron terhubung penuh dengan neuron lain di lapisan berikutnya. Ini memungkinkan integrasi fitur untuk menghasilkan prediksi.
   - **Softmax** digunakan untuk mengubah output menjadi probabilitas, sedangkan evaluasi model dilakukan menggunakan **loss function** seperti cross-entropy.


## Penjelasan File CNN.py
File CNN.py merupakan implementasi dasar Convolutional Neural Network (CNN) untuk klasifikasi gambar biner. Model tersebut menggunakan pustaka Keras dari TensorFlow untuk membangun CNN dan memproses dataset gambar. Model terdiri dari beberapa langkah:
1. Insialisasi CNN : Membuat model sekuensial di mana lapisan ditambahkan secara bertahap.
1. Convolution : Mengekstrak fitur penting dari gambar menggunakan filter (kernel) 3x3.
2. Max Pooling : Mengurangi ukuran data sambil mempertahankan fitur utama.
3. Menambah Convolutional layer : Tambahan layer konvolusi dan pooling untuk memperdalam jaringan, meningkatkan kemampuan ekstraksi fitur.
4. Flattening : Mengubah data matriks menjadi vektor 1 kolom untuk input ke neural network.
5. Full Connection : Membentuk lapisan fully connected dengan neuron, termasuk lapisan output yang menggunakan fungsi aktivasi sigmoid untuk klasifikasi biner.

Model ini dikompilasi menggunakan optimasi Adam untuk mempercepat proses konvergensi, fungsi loss binary_crossentropy untuk menghitung kesalahan, dan metrik accuracy untuk mengevaluasi performa. Dataset untuk pelatihan dan validasi diproses menggunakan ImageDataGenerator, yang melakukan augmentasi data seperti rescale, shear, zoom, dan flip horizontal pada data pelatihan untuk mencegah overfitting. Model dilatih menggunakan metode fit_generator, dengan batch size 32, selama 50 epoch.

## Penjelasan File CNN-CIFAR.py


     

## Keunggulan CNN
1. Efisiensi Komputasi : Parameter sharing pada layer konvolusi mengurangi jumlah parameter, sehingga lebih efisien dibanding jaringan saraf penuh.
2. Ketahanan terhadap Variasi : Mampu mengenali pola meskipun objek dalam gambar mengalami perubahan posisi atau orientasi.
3. Kemampuan Generalisasi : Sangat baik dalam memahami pola kompleks dari dataset visual.

## Tantangan CNN 
- Membutuhkan dataset besar agar dapat menghasilkan model yang akurat.
- Proses pelatihan yang memakan waktu dan memerlukan komputasi tinggi, terutama pada dataset besar.
- Risiko overfitting, yang dapat diatasi dengan teknik seperti augmentasi data atau dropout.

  
## Referensi 
https://www.megabagus.id/deep-learning-convolutional-neural-networks/

https://www.megabagus.id/deep-learning-convolutional-neural-networks-aplikasi/

https://modul-praktikum-ai.vercel.app/Materi/4-convolutional-neural-network
