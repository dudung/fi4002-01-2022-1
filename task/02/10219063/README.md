# 10219063
Tiara Andrina Pratista


## materi sebelumnya
Metode yang dipelajari pada kelas selama ini adalah : 
- diferensial euler
- diferensial Rung-Kutta Orde 4
- monte-carlo
- persamaan diferensial parsial
- fourier transform 

Metode-metode ini diaplikasikan pada persoalan : 
- Double spring
- osilasi teredam
- predator-prey
- persamaan lorentz
- rekursif


## materi paling menarik
+ menentukan nilai suhu pada persamaan diferensial parsial. menarik seperti bermain angka dalam kotak


## materi paling membosankan
+ tidak ada yang membosankan karena semua materi memiliki daya tarik dan tingkat kesulitan masing-masing. 


## materi yang sudah dipami
+ monte carlo, persamaan diferensial parsial


## materi yang belum dipahami
+ fourier transform 
- sebenernya materi yang sudah disampaikan pada kelas belom saya mengerti dengan detail (masih ngawang) jika diberi persoalan baru saya masih bingung. 


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python

#Monte Carlo
#menggunakan bilangan random untuk menyelesaikan masalah sistem fisis
#bermain tebak-tebakan, permasalahan lingkaran, estimasi mencari nilai pi

import matplotlib.pyplot as plt
import random

inside = 0 
n = 984

x_inside = []
y_inside = []
x_outside = []
y_outside = []

for _ in range (n) :
  x = random.uniform(-1.0,1.0)
  y = random.uniform(-1.0,1.0)
  if x**2+y**2 <= 1 : 
    inside += 1
    x_inside.append(x)
    y_inside.append(y)
  else : 
    x_outside.append(x)
    y_outside.append(y)

pi=4*inside/n
print (pi)

fig, ax = plt.subplots()
ax.set_aspect('equal')
ax.scatter(x_inside, y_inside, color='g', marker='s')
ax.scatter(x_outside, y_outside, color='r', marker='s' )

plt.draw

```

Hasilnya adalah

<img width="369" alt="Screen Shot 2022-10-19 at 10 00 24" src="https://user-images.githubusercontent.com/112141608/196587555-09731217-ad69-4f78-a370-5a599587a735.png">
```
```


## cara perkuliahan
+ cara perkuliahan yang sudah dijalani sudah bagus bagi saya namun terkadang terlalu cepat jadi saya tidak bisa catch up. 


## topik sistem fisis
+ saya tidak tau topik yang menarik untuk dibahas apa jadi saya ngikutin teman-teman saja. 


## simulasi dan visualisasi
+ sejujurnya saya tertarik dengan bidang simulasi dan visulisasi karena sekarang pun lagi trend tapi saya belom mendalami mendalam di bidang ini sehingga tidak tau topik apa yang menarik perlu dibahas.
