# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

## Answer

1. Menurut saya DevOps ialah metode pengembangan software untuk saling kerja sama
   dari pengembang software dan IT operasional.
2. Infrastructure bagi saya merupakan segala sesuatu yang diperlukan untuk membangun dan
   menjalankan perangkat lunak.
3. Server itu menurut saya tempat menyimpan dan menyediakan data.
   Ada web server dengan contohnya nginx dan Apache.
4. Karena server menjadi tempat menyediakan data yang ketika tidak ada maka tidak dapat
   berjalan atau diakses.
5. Virtualisasi ibarat server yang virtual yang diakses dengan metode tertentu.
   Container itu ibaratnya memindahkan infrastruktur yang digunakan pengembang plek-ketiplek.
6. Menurut saya karena fleksibel dan memudahkan dalam pengembangan dalam tim atau melibatkan
   banyak orang sekaligus.
7. Yang saya pahami ini merupakan sistem untuk mengelola dan mengatur kumpulan container.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy

(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

![VM](screenshot/Screenshot%202024-08-27%20105344.png)
![deployed](screenshot/Screenshot%202024-08-27%20105356.png)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container

- image: `dimmaryanto93/udemy-springboot-app:latest`
- port: `8080`
- env:
  - `DATABASE_HOST`: `<ip-domain-db>`
  - `DATABASE_PORT`: `5432`
  - `DATABASE_NAME`: `<db-name>`
  - `DATABASE_PASSWORD`: `<db-password>`
  - `APPLICATION_PORT`: `8080`
    need:
  - Database PostgreSQL v14.2

2. Frontend container

- image: `dimmaryanto93/udemy-angular-app:latest`
- port: `80`
- env:
  - `APPLICATION_PORT`: `80`
  - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
  - `BACKEND_HOST`: `<ip-backend-apps>`
  - `BACKEND_PORT`: `<port-backend-apps>`
  - `BACKEND_CONTEXT_PATH`: `/`
- need:
  - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`
