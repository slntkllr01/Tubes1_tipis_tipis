# Tugas Besar 1 IF2211 Strategi Algoritma: Pemanfaatan Algoritma Greedy pada Permainan Diamonds

## **Daftar Isi**

- [Deskripsi Program](#deskripsi-program)
- [Flow Program](#flow-permainan-diamonds)
- [Requirement Program](#requirements-program)
- [Set Up dan Build Program](#set-up-dan-build-program)
- [Author](#author)

## **Deskripsi Program**

<p align="justify">
Diamonds merupakan suatu programming challenge yang mempertandingkan bot yang anda buat dengan bot dari para pemain lainnya. Setiap pemain akan memiliki sebuah bot dimana tujuan dari bot ini adalah mengumpulkan diamond sebanyak-banyaknya. Cara mengumpulkan diamond tersebut tidak akan sesederhana itu, tentunya akan terdapat berbagai rintangan yang akan membuat permainan ini menjadi lebih seru dan kompleks. Untuk memenangkan pertandingan, setiap pemain harus mengimplementasikan strategi tertentu pada masing-masing bot-nya.

Repository ini berisi implementasi logic untuk bot permainan Diamonds dengan menerapkan algoritma greedy. Terdapat beberapa alternatif untuk mapping persoalan permainan Diamond ke komponen algoitma greedy. Namun, implementasi yang dipilih untuk persoalan ini adalah alternatif dengan mengambil maksimum lokal dengan cara memilih diamond dengan density paling besar. Rumus untuk menghitung density adalah bobot / total move. Dari maksimum lokal itu diharapkan mendapatkan maksimum global.

</p>

## **Flow Permainan Diamonds**

<p align="justify">
Untuk mengetahui flow dari game ini, berikut ini adalah cara kerja permainan Diamonds.

1. Pertama, setiap pemain (bot) akan ditempatkan pada board secara random. Masing-masing bot akan mempunyai home base, serta memiliki score dan inventory awal bernilai nol.
2. Setiap bot diberikan waktu untuk bergerak, waktu yang diberikan semua sama untuk setiap pemain.
   Objektif utama bot adalah mengambil diamond-diamond yang ada di peta sebanyak-banyaknya. Seperti yang sudah disebutkan di atas, diamond yang berwarna merah memiliki 2 poin dan diamond yang berwarna biru memiliki 1 poin.
3. Setiap bot juga memiliki sebuah inventory, dimana inventory berfungsi sebagai tempat penyimpanan sementara diamond yang telah diambil. Inventory ini sewaktu-waktu bisa penuh, maka dari itu bot harus segera kembali ke home base.
4. Apabila bot menuju ke posisi home base, score bot akan bertambah senilai diamond yang tersimpan pada inventory dan inventory bot akan menjadi kosong kembali.
5. Usahakan agar bot anda tidak bertemu dengan bot lawan. Jika bot A menimpa posisi bot B, bot B akan dikirim ke home base dan semua diamond pada inventory bot B akan hilang, diambil masuk ke inventory bot A (istilahnya tackle).
6. Selain itu, terdapat beberapa fitur tambahan seperti teleporter dan red button yang dapat digunakan apabila anda menuju posisi objek tersebut.
   Apabila waktu seluruh bot telah berakhir, maka permainan berakhir. Score masing-masing pemain akan ditampilkan pada tabel Final Score di sisi kanan layar.

</p>

## **Requirements Program**

1. **Game Engine**

   Requirement yang harus di-install:

   - Node.js (https://nodejs.org/en)
   - Docker desktop (https://www.docker.com/products/docker-desktop/)
   - Yarn

     ```bash
     npm install --global yarn
     ```

2. **Bot Starter Pack**

   Requirement yang harus di-install

   - Python (https://www.python.org/downloads/)

## **Set Up dan Build Program**

1. Jalankan game engine dengan cara mengunduh starter pack game engine dalam bentuk file .zip yang terdapat pada tautan berikut https://github.com/haziqam/tubes1-IF2211-game-engine/releases/tag/v1.1.0

   a. Setelah melakukan instalasi, lakukan ekstraksi file .zip tersebut lalu masuk ke root folder dari hasil ekstraksi file tersebut kemudian jalankan terminal

   b. Jalankan perintah berikut pada terminal untuk masuk ke root directory dari game engine

   ```bash
   cd tubes1-IF2110-game-engine-1.1.0
   ```

   c. Lakukan instalasi dependencies dengan menggunakan yarn.

   ```bash
   yarn
   ```

   d. Lakukan setup environment variable dengan menjalankan script berikut untuk OS Windows

   ```bash
   ./scripts/copy-env.bat
   ```

   Untuk Linux / (possibly) macOS

   ```bash
   chmod +x ./scripts/copy-env.sh
   ./scripts/copy-env.sh
   ```

   e. Lakukan setup local database dengan membuka aplikasi docker desktop terlebih dahulu kemudian jalankan perintah berikut di terminal

   ```bash
   docker compose up -d database
   ```

   f. Kemudian jalankan script berikut. Untuk Windows

   ```bash
   ./scripts/setup-db-prisma.bat
   ```

   Untuk Linux / (possibly) macOS

   ```bash
   chmod +x ./scripts/setup-db-prisma.sh
   ./scripts/setup-db-prisma.sh
   ```

   g. Jalankan perintah berikut untuk melakukan build frontend dari game-engine

   ```bash
   npm run build
   ```

   h. Jalankan perintah berikut untuk memulai game-engine

   ```bash
   npm run start
   ```

2. Jalankan bot starter pack dengan cara mengunduh kit dengan ekstensi .zip yang terdapat pada tautan berikut

   https://github.com/haziqam/tubes1-IF2211-bot-starter-pack/releases/tag/v1.0.1

   a. Lakukan ekstraksi file zip tersebut, kemudian masuk ke folder hasil ekstrak tersebut dan buka terminal
   b. Jalankan perintah berikut untuk masuk ke root directory dari project

   ```bash
   cd tubes1-IF2110-bot-starter-pack-1.0.1
   ```

   c. Jalankan perintah berikut untuk menginstall dependencies dengan menggunakan pip

   ```bash
   pip install -r requirements.txt
   ```

   d. Jalankan program dengan cara menjalankan perintah berikut.

   Untuk Windows :

   ```bash
   python main.py --logic BotBang --email=youremail@email.com --name=yourname --password=123456 --team etimo
   ```

   Untuk Linux dan MacOs

   ```bash
   python3 main.py --logic BotBang --email=youremail@email.com --name=yourname --password=123456 --team etimo &
   ```

   e. Anda juga bisa menjalankan satu bot saja atau beberapa bot menggunakan .bat atau .sh script.
   Untuk windows

   ```
   ./run-bots.bat
   ```

   Untuk Linux / (possibly) macOS

   ```
   ./run-bots.sh
   ```

## **Author**

|   NIM    |           Nama           |
| :------: | :----------------------: |
| 13522046 | Raffael Boymian Siahaan  |
| 13522116 |       Naufal Adnan       |
| 13522118 | Berto Richardo Togatorop |

<h4 align="center">
  Created by @tipis_tipis<br/>
  202
</h4>
<hr>
