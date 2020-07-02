**Urutan Pemahaman**:
1. Mean
2. Variance
3. Covariance
4. Standard Deviation
5. Correlation

**Terminologi:**

- Correlation: menunjukkan seberapa besar dan arah hubungan linear dari dua variabel
- Covariance: menunjukkan arah dari hubungan linear dari dua variabel ```Conv(a,b)```
- Variance: hampir sama dengan Covariance, namun hanya melibatkan satu variabel saja ```Conv(a,a) = Var(a)```
- Standard Deviation: menunjukan variabilitas data dalam distribusi dataset 


**Perbedaan:**
- nilai Correlation terstandar (yaitu rentang -1 s/d 1), sedangankan nilai Covariance pada rentang -∞ and +∞
- kapan kita gunakan matriks covariance? ketika variabel-variabel yang terlibat memiliki kemiripan, dan kapan menggunakan matriks correlation? yaitu ketika terdapat perbedaan scales
- covariance hanya mampu menunjukkan arah hubungan antar dua variabel/fitur, misal: pada variabel ```a``` dan ```b```, kita akan tentukan nilai ```conv(a,b)```. Jika ```a``` naik dan ```b``` naik, maka akan menghasilkan nilai positif (arah hubungan positif). Jika ```a``` naik dan ```b``` turun, maka akan menghasilkan nilai negatif (arah hubungan negatif). Yang digunakan hanya tanda saja, yaitu positif dan negatif.
- covariance sensitif terhadap perubahan skala pada data, sedangkan correlation tidak sensitif terhadap perubahan skala pada data. Skala yang dimaksud adalah faktor pengali yang dilakukan pada data

Untuk mendapatkan nilai Correlation Coefficient dengan cara:
membagi covariance dari dua variabel dengan perkalian standar deviasi dari masing-masing variabel.


**sumber**: https://towardsdatascience.com/let-us-understand-the-correlation-matrix-and-covariance-matrix-d42e6b643c22

**Covariance pada Numpy:**
Kalkulasi nilai covariance yang dilakukan terhadap dua variabel ```a``` dan ```b``` pada ```np.conv``` maka memiliki output berupa matrix yang berisi:

```covariance(a,a) covariance(b,a)```

```covariance(a,b) covariance(b,b)```

**sumber**: https://stackoverflow.com/questions/15317822/calculating-covariance-with-python-and-numpy

**sumber video:**
- https://www.youtube.com/watch?v=qtaqvPAeEJY

