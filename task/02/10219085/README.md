# 10219085
Meyke Putri Dalla


## materi sebelumnya
+ Tuliskan materi-materi sebelumnya yang telah diberikan dalam kuliah ini.
+ Runge-Kutta
+ Predator-Prey
+ Euler
+ Lorentz
+ Osilasi Teredam
+ Transform fourier
+ Monte carlo

## materi paling menarik
+ Tuliskan materi yang paling menarik yang telah diberikan dan jelaskan mengapa menarik.
+ Monte carlo, karena menggunakan bilangan acak untuk menentukan nilai asli/ sebenarnya.

## materi paling membosankan
+ Tuliskan materi yang telah diberikan yang paling membosankan dan jelaskan alasannya.
+ Transform fourier, karena dibeberapa mata kuliah sudah dijelaskan.

## materi yang sudah dipami
+ Tuliskan materi-materi yang telah dipahami.
+ Euler
+ Monte Carlo
+ Transform Fourier

## materi yang belum dipahami
+ Tuliskan materi-materi yang masih belum dipahami dan bagian mana yang belum serta ingin dipahami.
+ Runge-kutta, masih belum paham metodenya itu seperti apa dan bisa digunakan saat kapan atau untuk kasus yang mana.

## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python untuk mencari nilai π
import matplotlib.pyplot as plt
import random

inside = 0
n = 1000

x_inside = []
y_inside = []
x_outside = []
y_outside = []

for _ in range(n):
  x = random.uniform(-1.0,1.0)
  y = random.uniform(-1.0,1.0)
  if x**2+y**2 <= 1:
    inside += 1
    x_inside.append(x)
    y_inside.append(y)
  else:
    x_outside.append(x)
    y_outside.append(y)

pi = 4*inside/n
print(pi)

fig, ax = plt.subplots()
ax.set_aspect('equal')
ax.scatter(x_inside, y_inside, color='g', marker='s')
ax.scatter(x_outside, y_outside, color='r', marker='s')

plt.draw()

```

Hasilnya adalah

```
![SPSF_1](https://user-images.githubusercontent.com/97948879/196739671-1f18af82-342c-4644-a4df-482d740cf053.png)

```


## cara perkuliahan
+ Tuliskan pendapat Anda mengenai cara perkuliahan selama ini dan cantumkan usulan untuk perkuliahan setelah UTS.
+ Proses pembelajaran sudah cukup baik, teori sebelum membuat suatu program cukup jelas. Hanya saja, kadang masih ada beberapa metode yang belum begitu saya kuasai.

## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.
+ Gelombang bunyi di dalam medium gas/udara. Karena udara/gas tidak dapat melawan perubahan bentuk, sehingga tidak mungkin terjadi gelombang geser atau gelombang transversal.

## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
+ Saya tertarik dengan simulasi dan visualisasi. Topik yang ingin disimulasikan adalah kurva dispersi sepanjang garis MASW (Multichannel Analysis of Surface Wave), karena berkaitan dengan topik tugas akhir saya.
+ Pandas, Numpy, Matplotlib
