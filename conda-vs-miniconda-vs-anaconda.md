# Conda vs Miniconda vs Anaconda

### Apakah miniconda itu? 

[Miniconda](https://docs.conda.io/en/latest/miniconda.html#) adalah versi minimal dan gratis dari software [conda](https://conda.io/en/latest/). Dalam sebuah installer Miniconda berisi conda, Python, beberapa paket dependensi, dan beberapa paket yang cukup populer dan sering digunakan seperti pip, zlib, dan lainnya.  

### Lalu apa perbedaan Miniconda jika dibandingkan dengan conda?
Conda adalah sebuah perangkat lunak untuk pengaturan paket (package/software modules) dan lingkungan pengembangan (environtment management) yang tersedia dalam multi-platform (Windows, macOS, dan Linux). Dengan menggunakan conda, kita dapat secara cepat melakukan instalasi, menjalankan, dan melakukan pembaruan paket dan pendukungnya. Fitur lain yang juga sering digunakan adalah pengelolaan environment/lingkungan kerja yaitu kemudahan dalam membuat, menyimpan, menggunakan ulang, dan berganti (switch). Pada awalnya, conda dibangun hanya untuk bahasa pemrograman Python, namun pada perkembangan selanjutnya dapat digunakan pada bahasa pemrograman lainnya.

### Kemudian apa itu Anaconda, apa kekhususan yang dimilikinya?
[Anaconda](https://anaconda.org/) merupakan versi conda yang lebih spesifik dimana dalam installer telah terdapat paket-paket populer untuk data science, atau pengolahan data statistik.


### Berikut adalah rangkuman hubungan ketiganya:

```
Conda adalah sebuah command line tool (CLI) yang digunakan untuk mengelola paket (seperti yum, apt-get pada linux) dan pengelolaan virtual environment. 

Miniconda installer = Python + conda

Anaconda installer = Python + conda + meta package anaconda

meta Python pkg anaconda = about 160 Python pkgs for daily use in data science

Anaconda installer = Miniconda installer + conda install anaconda
```




