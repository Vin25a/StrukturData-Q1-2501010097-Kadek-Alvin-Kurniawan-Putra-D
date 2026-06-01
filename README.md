## 1. Karakteristik Memori dan Akses Data

Array dapat melakukan akses elemen dalam waktu konstan O(1) karena data disimpan pada lokasi memori yang berurutan (kontinu). Setiap elemen memiliki indeks yang dapat langsung dihitung alamat memorinya menggunakan rumus tertentu. Karena alamat memori dapat diketahui secara langsung, sistem tidak perlu menelusuri elemen satu per satu.

Sebaliknya, Singly Linked List menyimpan node pada lokasi memori yang tidak harus berurutan (non-kontinu). Setiap node hanya mengetahui alamat node berikutnya melalui pointer. Untuk mengakses elemen ke-n, proses harus dimulai dari head dan menelusuri node satu per satu hingga mencapai elemen yang dicari.

Akibatnya, kompleksitas akses pada Array adalah O(1), sedangkan pada Singly Linked List adalah O(n).

## 2. Analisis Efisiensi Operasi Manipulasi

Linked List lebih unggul dibandingkan Array ketika sering dilakukan operasi penyisipan (insertion) dan penghapusan (deletion) data, terutama pada bagian awal atau tengah struktur data.

Pada Array, penyisipan atau penghapusan mengharuskan elemen-elemen setelah posisi tersebut digeser. Proses ini membutuhkan waktu O(n).

Sedangkan pada Linked List, jika posisi node telah ditemukan, penyisipan atau penghapusan hanya memerlukan perubahan pointer tanpa memindahkan data lain. Operasi tersebut dapat dilakukan dalam waktu O(1).

Oleh karena itu, Linked List lebih efisien untuk aplikasi yang sering melakukan perubahan struktur data secara dinamis.

## 3. Konsep Doubly Linked List

Pada Doubly Linked List, setiap node terdiri dari tiga bagian:

Data
Pointer ke node berikutnya (next)
Pointer ke node sebelumnya (prev)

Struktur node:

[Prev] ← [Data] → [Next]

Keberadaan pointer tambahan (prev) menyebabkan penggunaan memori menjadi lebih besar dibandingkan Singly Linked List karena setiap node harus menyimpan dua alamat pointer.

Namun, keuntungan utamanya adalah penelusuran dapat dilakukan ke dua arah, yaitu maju dan mundur. Hal ini membuat operasi tertentu seperti traversal balik atau penghapusan node menjadi lebih fleksibel dan efisien.

## 4. Mekanisme Circular Linked List

Circular Linked List adalah Linked List yang node terakhirnya tidak menunjuk ke NULL, melainkan kembali menunjuk ke node pertama (head).

Linked List biasa:

Head → Node1 → Node2 → Node3 → NULL

Circular Linked List:

Head → Node1 → Node2 → Node3
↑______________________↓

Perbedaan utama secara teoritis adalah tidak adanya akhir (NULL) pada struktur melingkar ini.

Contoh penggunaan Circular Linked List adalah sistem Round Robin Scheduling pada sistem operasi. Dalam metode ini, setiap proses mendapatkan giliran secara bergantian dan setelah proses terakhir selesai, giliran kembali ke proses pertama secara otomatis.

## 5. Array Dinamis di Python

Python List diimplementasikan sebagai Dynamic Array. Saat operasi append dilakukan dan kapasitas array masih tersedia, elemen baru cukup ditempatkan pada slot kosong sehingga proses berlangsung dalam O(1).

Namun, ketika kapasitas penuh, Python akan melakukan beberapa langkah:

Membuat array baru dengan kapasitas yang lebih besar.
Menyalin seluruh elemen dari array lama ke array baru.
Menambahkan elemen baru pada array yang telah diperbesar.
Melepaskan memori array lama.

Proses penyalinan ini membutuhkan waktu O(n) karena seluruh elemen harus dipindahkan.

Meskipun demikian, Python melakukan penambahan kapasitas lebih besar dari kebutuhan saat ini (over-allocation), sehingga operasi append secara rata-rata (amortized) tetap memiliki kompleksitas O(1).

## Kesimpulan

Array memiliki keunggulan pada akses data yang sangat cepat karena menggunakan memori kontinu, sedangkan Linked List unggul pada fleksibilitas penyisipan dan penghapusan data karena menggunakan pointer. Doubly Linked List menambah fleksibilitas traversal dengan biaya memori yang lebih besar. Circular Linked List cocok untuk proses yang bersifat berulang. Sementara itu, Python List menggunakan Dynamic Array yang memungkinkan ukuran struktur data bertambah secara otomatis sesuai kebutuhan.
