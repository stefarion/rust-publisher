# Advanced Programming - Module 09 Rust Publisher
**Nama:**   &nbsp; Stefanus Tan Jaya<br>
**NPM:**    &nbsp;&ensp; 2306152456<br>
**Kelas:**  &nbsp; Pemrograman Lanjut A<br>

### Questions
1. How much data your publisher program will send to the message broker in one run?<br>
    Program Publisher ini akan mengirim 5 pesan ke AMQP _broker_ dalam 1 kali _run_.<br><br>
2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?<br>
    URL yang sama antara Subscriber dan Publisher menunjukkan bahwa keduanya terhubung ke _broker_ yang sama. Jadi, pesan yang di-_publish_ oleh Publisher akan dikirim ke _broker_ dan Subscriber dapat menerima pesan tersebut dari _broker_ yang sama.<br><br>

![RabbitMQ](RabbitMQ.png)
<br><br>
Setelah _run_ Subscriber dan Publisher, Publisher akan _publish_ 5 event/pesan ke _broker_ dan melalui _broker_ yang sama, Subscriber memproses kelima event tersebut.<br><br>
![Events](SentEvents.png)
<br><br>
![Graph](SpikeGraph.png)
<br><br>
Bisa dilihat bahwa lonjakan pada grafik RabbitMQ menunjukkan kecepatan pesan yang mengukur jumlah pesan yang dikirim pada _channel_ dalam interval waktu tertentu. _Spike_ pada grafik merupakan hasil dari Publisher yang telah mengirim beberapa pesan ke _broker_ melalui `cargo run`.