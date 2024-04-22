# tutorial-8-subscriber

a. what is amqp?
amqp merupakan singkatan dari Advanced Message Quering Protocol, sebuah standar untuk message-oriented middleware, amqp merupakan sebuah protokol yang digunakan untuk membuat sebuah sistem yang memungkinkan aplikasi berbeda dapat berkomunikasi dengan mengirimkan pesan melalui messaging broker.

b. what it means? guest:guest@localhost:5672 , what is the first quest, and what is
the second guest, and what is localhost:5672 is for?
guest pertama menandakan username, sedangkan guest kedua menandakan password yang digunakan untuk melakukan autentikasi, localhost:5672 merupakan ip address dari mesin yang menjalankan sebagai AMQP broker

![QueueRabbitMQ](img/Screenshot%202024-04-22%20142515.png)

Grafik queue messages menjukkan angka 20 pada grafik, hal ini disebabkan oleh subscribers membutuhkan waktu yang lama untuk memperoses message yang dikirim oleh publisher, menjadikan adanya antrean berupa messages queue menunggu untuk diproses oleh subscribers

![console](img/Screenshot%202024-04-22%20143718.png)

![graph](img/Screenshot%202024-04-22%20143543.png)

Gambar menunjukkan adanya perbedaan data yang diterima oleh tiap console, hal ini dikarenakan data yang sudah diterima oleh suatu subscriber akan hilang dari queue dan tidak bisa diterima oleh subscriber lainnya, menggunakan subscriber yang banyak juga mempercepat penerimaan data pada grafik dan mengurangi queue message pada message broker karena setiap subscriber menerima data secara bersamaan dari queue message.

Hal yang dapat diimprove dalam kode adalah menggunakan expect() dibanding unwrap() untuk melakukan handle error, menggunakan env dibanding melakukan hardcode URL untuk memudahkan modifikasi, message handling dapat diimprove untuk melakukan suatu fungsionalitas dibanding dengan melakukan print pada console saja.
