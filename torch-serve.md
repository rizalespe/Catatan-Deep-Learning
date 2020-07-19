## Prosedur penggunaan Torchserve
Komponen-komponen yang dibutuhkan:

0. Instalasi Java 11, Torchserve, dan dependensi lain seperti pada petunjuk di halaman ini: https://github.com/pytorch/serve
1. Komponen-komponen yang harus dipersiapkan:
    * file python berisi definisi kelas model (model.py)
    * file serialized yang berisi bobot/weight saat proses training (biasanya berekstensi .pth/.pkl)
2. Archive model menjadi sebuah file .mar yang digunakan sebagai pembuatan layanan

```
torch-model-archiver --model-name densenet161 --version 1.0 --model-file ./serve/examples/image_classifier/densenet_161/model.py --serialized-file densenet161-8d451a50.pth --export-path model_store --extra-files ./serve/examples/image_classifier/index_to_name.json --handler image_classifier
```

3. Jalankan service dengan menentukan file model yang telah terbentuk (.mar). Sebagai tambahan, buat sebuah file untuk menyimpan configurasi. Pada catatan ini configurasi dilakukan terkait HOST dan PORT yang digunakan. File configurasi disimpan pada file config.txt dengan isi:
```
# bind inference API to private network interfaces
inference_address=http://<HOST>:<PORT>
```
Perintah untuk menjalankan service:
```
torchserve --start --ncs --model-store model_store --models densenet161.mar --ts-config config.txt
```
Menjalankan multiple service:
```
torchserve --start --model-store /models --models all
```

4. Untuk menghentikan service, jalankan perintah:
```
torchserve --stop
```
