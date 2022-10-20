# 10219002
Handoko Setiawan


## materi sebelumnya
1. Dasar dasar pemrograman
2. Beberapa model sistem fisis (Model Lorenz, Persamaan Predator Prey, sistem rantai membentang)
3. Penyelesaian Solusi Persamaan Diferensial orde 1 dan orde 2 untuk sistem fisis dengan menggunakan metode Euler dan metode Runge Kutta 4th order
4. Metode Monte Carlo
5. DFT dan FFT


## materi paling menarik
Menurut saya materi paling menarik adalah metode Monte Carlo karena sebelumnya saya sudah sering kali mendengar nama metode tersebut namun saat itu belum paham tentang metodenya sendiri. Setelah belajar di kelas saya makin mendapat gambaran tentang metode tersebut.


## materi paling membosankan
Beberapa model fisis seperti model lorenz dan persamaan predator prey karena saya belum dapat mendapatkan gambaran tentang aplikasinya dalam pemodelan siste fisis


## materi yang sudah dipami
Penjelasan secara *teoritik* mengenai beberapa metode numerik seperti Monte Carlo, solusi PD orde 1 dan 2 dengan metode Euler dan Runge Kutta 4th order


## materi yang belum dipahami
Beberapa model sistem fisis, dan juga implementasi metode numerik dalam bahasa pemrograman


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
#Monte Carlo Method for Definite Integral Evaluation

import matplotlib.pyplot as plt
import random

inside = 0
n = 300000

x_inside = []
y_inside = []
x_outside = []
y_outside = []

for _ in range(n):
 x = random.uniform(-2.0,3.0)
 y = random.uniform(0.0,81.0)
 if y <= x**4:
  inside += 1
  x_inside.append(x)
  y_inside.append(y)
 else:
  x_outside.append(x)
  y_outside.append(y)
Area = 410*inside/n
print(Area)

#Analytical Calculation:
#int[-2 to 3] x^3 = (1/4)*x^4|[-2 to 3] = 55
```

Hasilnya adalah

#Hasil Perhitungan Numerik
55.792116666666665

## cara perkuliahan
Karena perkuliahan dilakukan dengan asumsi mahasiswa telah memiliki dasar pemrograman dari mata kuliah fisika komputasi dan pengenalan komputasi, perkuliahan berasa sangat cepat dan saya cukup kewalahan dalam mengikuti alur kelas karena basic pemrograman saya kira masih sangat lemah. 


## topik sistem fisis
Density Functional Theory (DFT). Karena minat saya adalah pada dunia sains material, model simulasi DFT akan sangat menarik untuk dipelajari karena ada banyak sifat fisis dari suatu material yang dapat ditinjau dengan menggunakan DFT.


## simulasi dan visualisasi
Saya tertarik. Topik sistem fisis yang ingin saya pelajari adalah DFT untuk meninjau sifat fisis suatu material. Pustaka termasuk buku tentang DFT dan juga referensi codingan dari internet
