Modul 6 – Interrupt dan Timer pada Arduino Uno
Deskripsi Praktikum

Praktikum Modul 6 bertujuan untuk memahami konsep interrupt dan timer pada Arduino Uno. Pada percobaan ini digunakan push button sebagai input interrupt dan LED sebagai output. Selain itu, dilakukan juga percobaan penggunaan fungsi millis() untuk membuat LED berkedip tanpa menggunakan delay().

Percobaan 6A – External Interrupt
Tujuan
Memahami konsep external interrupt pada Arduino Uno.
Mengendalikan LED menggunakan interrupt.
Memahami penggunaan ISR (Interrupt Service Routine).

Jawaban Pertanyaan Praktikum 6A
1. Jelaskan proses bagaimana tombol dapat mengubah kondisi LED menggunakan interrupt!

Ketika tombol ditekan, sinyal pada pin interrupt berubah sehingga Arduino mendeteksi interrupt. Setelah interrupt terjadi, Arduino menjalankan ISR tombolInterrupt(). ISR tersebut mengubah nilai variabel ledState, sehingga kondisi LED berubah dari ON menjadi OFF atau sebaliknya.

2. Apa fungsi attachInterrupt() pada program tersebut?

Fungsi attachInterrupt() digunakan untuk menghubungkan pin interrupt dengan fungsi ISR. Ketika kondisi interrupt terpenuhi, Arduino akan otomatis menjalankan ISR yang telah ditentukan.

3. Mengapa pada ISR tidak disarankan menggunakan delay() dan Serial.print()?

Karena selama ISR berjalan, program utama dihentikan sementara. Penggunaan delay() dan Serial.print() dapat membuat interrupt berjalan terlalu lama sehingga sistem menjadi lambat atau tidak stabil.

4. Apa fungsi keyword volatile pada variabel ledState?

Keyword volatile digunakan agar compiler mengetahui bahwa nilai variabel dapat berubah sewaktu-waktu di luar alur program utama.

5. Perbedaan Mode Interrupt
RISING → interrupt aktif saat sinyal berubah LOW ke HIGH.
FALLING → interrupt aktif saat sinyal berubah HIGH ke LOW.
CHANGE → interrupt aktif setiap ada perubahan sinyal.
LOW → interrupt aktif selama kondisi pin LOW.

Percobaan 6B – Timer Menggunakan millis()
Tujuan
Memahami konsep timer pada Arduino.
Menggunakan fungsi millis() tanpa delay().
Membuat LED blinking secara non-blocking.

Jawaban Pertanyaan Praktikum 6B
1. Jelaskan bagaimana fungsi millis() bekerja pada program tersebut!

Fungsi millis() menghitung waktu sejak Arduino dinyalakan dalam satuan milidetik. Program membandingkan waktu saat ini dengan waktu sebelumnya untuk menentukan kapan LED harus berubah kondisi.

2. Apa perbedaan utama antara delay() dan millis()?

delay() menghentikan program sementara, sedangkan millis() memungkinkan program tetap berjalan sambil menghitung waktu.

3. Mengapa metode millis() disebut non-blocking?

Karena program tidak berhenti selama proses penghitungan waktu berlangsung sehingga tugas lain tetap dapat dijalankan.

Kesimpulan

Interrupt memungkinkan Arduino merespon event secara cepat tanpa polling terus-menerus, sedangkan fungsi millis() memungkinkan sistem menjalankan timer tanpa menghentikan proses utama. Kombinasi keduanya sangat penting dalam pengembangan sistem embedded dan real-time.
Memahami konsep timer pada Arduino.
Menggunakan fungsi millis() tanpa delay().
Membuat LED blinking secara non-blocking.
