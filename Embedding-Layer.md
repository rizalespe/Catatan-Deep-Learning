# Bagaimanakah Embedding Layer berfungsi?

Neural Network hanya menerima input berupa data numerik (double,float, dll). Maka jika kita memiliki data berupa data teks (dokumen atau kalimat) maka apa yang harus kita lakukan? Pasti kita berfikir untuk mengubah bentuk teks menjadi representasi numerik. Lalu apa yang harus kita siapkan pertama kali? Dalam catatan ini, saya menggunakan framework deep learning Pytorch.

------

#### Persiapan
1. Misalkan kita hendak memproses lebih dari 1 dokumen (multi-dokumen), maka kumpulkan terlebih dahulu dokumen-dokumen tersebut kedalam satu tempat/direktori yang sama. Istilah `dokumen` merujuk pada kumpulan kata/term, bisa jadi sebuah dokumen adalah kalimat, tweet, buku, file, array dll.

2. Setelah terkumpul, jadikan seluruh dokumen tersebut menjadi satu kesatuan. Output dari proses ini adalah hanya ada sebuah dokumen saja. Misalkan, kita memiliki 10 dokumen file, maka akan hanya terdapat sebuah file saja setelah proses ini selesai.

3. Dari satu file tersebut hapus kata/term yang muncul lebih dari satu kali sehingga hanya tersisa satu kata saja. Proses ini bertujuan untuk menghapus duplikasi kemunculan kata, dimana yang tersisa adalah kumpulan kata identik (tidak berulang).

4. Terakhir, urutkan kata-kata yang tersisa berdasarkan abjad dan tambahkanlah kode numerik berupa angka integer terurut. Misalkan setelah proses poin ke-3 tersisa 1000 kata/terms, maka akan terdapat kode numerik terurut dari 0 s/d 999 yang terpetakan terhadap masing-masing kata/term yang ada.

5. Sampai disini, kita akan memiliki `vocabulary` kata yaitu pasangan integer dan kata/term. Berikut adalah contoh `vocabulary` yang terdiri dari lima kata/term saja.

    |Kode|Kata  |
    |--|--|
    | 1 |bola  |
    | 2 |mobil  |
    | 3 |aku  |
    | 4 |teman  |
    | 5 |mereka  |

------


#### Input
Lanjut, kita akan memproses sebuah dokumen berupa kalimat yang akan kita proses menjadi sebuah representasi `Embedding`. Representasi `Embedding` memiliki keunggulan yaitu setiap kata/term tidak hanya dinilai kemunculannya tetapi juga dinilai bobotnya secara makna kemunculannya terhadap kata yang lain.

Transformasi setiap teks/term dalam dokumen menjadi kode yang ada pada `vocabulary` yang telah terbentuk pada proses sebelumnya. Berikut ini adalah contoh dari input:
`"bermain bola di lapangan depan rumah"` → `[23, 34, 12, 9, 6, 56]`. 

Input untuk proses ini bukan lagi berupa teks/term, tetapi berupa data numerik `[23, 34, 12, 9, 6, 56]`.

------

#### Proses
Berikut adalah inisialisasi objek Embedding Layer, dimana memiliki 2 parameter yaitu `vocab_size` dan `embed_size`.

`self.embed = nn.Embedding(vocab_size, embed_size)`

`vocab_size` adalah panjang/jumlah kata yang ada pada `vocabulary`
`embed_size` adalah panjang output representasi untuk setiap kata yang telah melalui proses `Embedding`.

------

#### Output
Output dari proses ini adalah tensor yang memiliki dimensi `[*, embed_size]`, dimana `[*]` adalah ukuran dimensi input. Sebagai contoh, saya akan memproses sebuah dokumen dengan isi sebagai berikut:

`"bermain bola di lapangan depan rumah"` → `[23, 34, 12, 9, 6, 56]`

Kemudian untuk ukuran output akan bernilai 10, `embed_size=10`. Maka, dari proses `embedding` ini akan menghasilkan output untuk masing-masing kata berupa array sepanjang 10.


  |Kata|Kode|Representasi Embedding  |
  |--|--|--|
  |bermain| 23 |[0.8303,  0.0748, -0.2801, -0.3801,  0.4987,  0.0195,  0.9959, -0.3921, -0.3791, -0.7454]  |
  |bola| 34 |[-0.3831,  0.5807, -0.2090,  2.5954,  1.0178, -0.3526, -0.9457,  0.1198, -1.0962,  1.4113]  |
  |di| 12 |[0.3865, -0.9243,  0.7449, -1.4363,  1.1803,  0.0851,  0.3871,  0.9225, 0.7557, -0.9098]  |
  |lapangan| 9 |[-0.1407, -1.2779, -1.1170, -1.7130, -0.2325, -0.1829, -0.3575, -1.7949, -0.2912, -0.3817]  |
  |depan| 6 |[0.3000,  0.5547, -0.7829, -0.8794,  0.3341, -1.1547, -0.3411,  1.2519, 1.5087, -0.6034]  |
  |rumah| 56 |[-0.4643, -1.5757,  0.1448,  0.0035, -1.5407, -2.2671,  0.6009,  1.3066, -1.0037, -1.1288]  |

Dengan ukuran input `torch.Tensor([1, 6])`, maka output dari dokumen ini adalah `torch.Tensor([1, 6, 10])`

Lebih lanjut: https://pytorch.org/docs/stable/nn.html#sparse-layers
