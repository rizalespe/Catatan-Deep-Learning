# Perintah pada Conda Command Line
Halaman ini berisi tentang catatan command line (perintah eksekusi) pada conda yang sering digunakan. Conda telah menyediakan dokumentasi pada CLI untuk seluruh opsi pada command. Untuk mengakses dokumentasi yaitu dengan perintah ```COMMANDNAME --help```, sebagai contoh ```conda install --help```. 

## Perintah Dasar
1. ```conda info``` merupakan perintah untuk mendapatkan detail informasi terkait conda yang sedang berjalan
2. ```conda update conda``` perintah untuk pembaruan paket-paket yang telah terinstall pada conda & pembaruan conda cli
3. ```conda list``` menampilkan seluruh package yang ter-install pada environment yang sedang aktif.
4. ```conda search NAMA_PACKAGE``` perintah untuk melakukan pencarian package yang tersedia berdasarkan nama. Misalkan, ```conda search torch```. Daftar seluruh package yang ada tersedia pada halaman berikut [daftar package](https://docs.anaconda.com/anaconda/packages/pkg-docs/)
5. ```conda install NAMA_PACKAGE``` perintah untuk melakukan instalasi package/library tertentu, misalkan: ```conda install scipy```. Kita dapat menspesifikan channel tertentu untuk sebuah package, seperti ```conda install scipy --channel conda-forge```. Channel adalah lokasi dimana tempat package tersimpan.
6. ```conda update NAMA_PACKAGE``` perintah untuk melakukan pembaruan terhadap package tertentu.
7. ```conda remove/uninstall NAMA_PACKAGE``` menghapus atau meng-uninstall package tertentu pada environment yang sedang aktif


## Pengelolaan Lingkungan (Environment Management) Conda
1. ```conda env list``` perintah untuk menampilkan daftar environment yang ada 
2. ```conda create --name NAMA_ENVIRONMENT python=PYTHON_VERSION``` merupakan perintah untuk membuat conda environment dengan versi Python tertentu.
3. ```conda activate NAMA_ENVIRONMENT``` atau ```source activate NAMA_ENVIRONMENT``` perintah untuk mengaktifkan environment tertentu 
4. ```conda remove --name NAMA_ENVIRONMENT``` perintah untuk menghapus environment tertentu
5. ```conda deactivate``` atau ```source deactivate``` merupakan perintah untuk keluar dari environment yang sedang aktif
6. ```conda list --explicit > NAMA_FILE.txt``` merupakan perintah untuk menyimpan environment ke dalam sebuah file
7. ```conda env create --file NAMA_FILE.txt``` merupakan perintah untuk membuat environment baru berdasarkan file hasil ekspor sebelumnya.

Sumber: [Conda Cheat Sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)
