# 10219033
Aniesah Akhyar 


## materi sebelumnya
+ Pendahuluan mengenai simulasi dan pemodelam (flowchart, algoritma, dan pseudocode) 
+ Penyelesaian persamaan diferensial menggunakan metode Euler, Lorenz, dan Runge-Kutta orde 4
+ Monte Carlo
+ Discrete Fourier Transform


## materi paling menarik
+ Materi yang paling menarik yaitu Monte Carlo. Materi ini menarik karena metode yang digunakan sangat beragam serta menantang karena perlu memahami alur dari bagian yang perlu ditentukan bilangan acak. 

## materi paling membosankan
+  Tidak ada materi yang membosankan, semuanya sangat perlu untuk dipelajari

## materi yang sudah dipahami
+ Materi mengenai penyelesaian sistem gerak bandul sederhana dengan hasil osilasi teredam

## materi yang belum dipahami
+ Materi mengenai Runge-Kutta orde 4. Ingin mendalami lebih jauh mengenai penentuan parameter dari variabel yang diketahui. 

## contoh program
+ Digunakan contoh untuk menghitung luas atau integral
```python
# Monte Carlo
import random

inside = 0

n = 1000

x_inside = []

y_inside = []

x_outside = []

y_outside = []

for _ in range(n):

  x = random.uniform(0.0,2.0)

  y = random.uniform(0.0,4.0)

  if y <= 2*x:

    inside += 1

    x_inside.append(x)

    y_inside.append(y)

  else:

    x_outside.append(x)

    y_outside.append(y)

luas = 8*inside/n

print(luas)
```

Hasilnya adalah

```
4.04
```


## cara perkuliahan
+ Sejauh ini cara perkuliahan dirasa nyaman, Untuk berikutnya, diharapkan ada pergantian waktu untuk materi dengan penugasan sehingga lebih teratur

## topik sistem fisis
+ Sistem fisis yang menarik untuk dikaji berupa pergerakan suatu benda di dalam fluida. Bagian ini tampaknya menarik untuk dibuat simulasi dan visualisasi terkait

## simulasi dan visualisasi
+ Saya tertarik dengan simulasi dan visualisasi. Saya ingin menerapkannya pada topik fonetika, berupa simulasi dan visualisasi untuk pergerakan artikulator saat berbicara. Perkiraan pustaka Python yang perlu digunakan berupa matplotlib.animation
