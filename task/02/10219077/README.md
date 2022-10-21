# 10219077
Dwita Gurning


## materi sebelumnya
+ Tuliskan materi-materi sebelumnya yang telah diberikan dalam kuliah ini.
Materi-materi yang telah diberikan adalah:
1. Persamaan Lorentz
2. Persamaan Predator-Prey
3. Metode Euler
4. Metode Runge Kutta Orde 4
5. Osilator Harmonik Sederhana
6. Monte Carlo Methods
7. DFT
8. FFT

## materi paling menarik
+ Tuliskan materi yang paling menarik yang telah diberikan dan jelaskan mengapa menarik.
Materi yang paling menarik adalah Metode Monte Carlo. Alasannya adalah karena metode ini terkait dengan tugas akhir saya dan bermain dengan tebak-tebakan dan peluang random.


## materi paling membosankan
+ Tuliskan materi yang telah diberikan yang paling membosankan dan jelaskan alasannya.
Materi yang telah diberikan dan yang paling membosannkan adalah metode Runge Kutta orde 4. Hal ini disebabkan saya belum bisa mengaplikasikan metode ini pada sistem fisis.

## materi yang sudah dipahami
+ Tuliskan materi-materi yang telah dipahami.
Materi-materi yang telah dipahami adalah:
1. Metode Euler
2. Monte Carlo Methods



## materi yang belum dipahami
+ Tuliskan materi-materi yang masih belum dipahami dan bagian mana yang belum serta ingin dipahami.
Materi-materi yang masih belum dipahami dan ingin dipahami:
1. Persamaan Lorentz
2. Persamaan Predator-Prey
3. Metode Euler
4. Metode Runge Kutta Orde 4
5. Osilator Harmonik Sederhana
6. Monte Carlo Methods
7. DFT
8. FFT


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python
import matplotlib.pyplot as plt
import random

inside = 0
n = 10000

xinside = []
yinside = []
xoutside = []
youtside = []

for _ in range (n):
    x = random.uniform(-1,1)
    y = random.uniform(-1,1)
    if x**2+y**2 <=1:
        inside+=1
        xinside.append(x)
        yinside.append(y)
        
    else:
        xoutside.append(x)
        youtside.append(y)

```

Hasilnya adalah

```
pi = 4*inside/n
print('nilai estimasi pi', pi)

fig, ax = plt.subplots()
ax.set_aspect('equal')
ax.scatter(xinside, yinside, color='g', marker  ='s')
ax.scatter(xoutside, youtside, color ='r', marker = 's')

plt.draw()
```
![estimasi pi](https://user-images.githubusercontent.com/101064593/196593565-ce832ccb-ff0b-43fd-8152-f2d1d6109b51.png)


## cara perkuliahan
+ Tuliskan pendapat Anda mengenai cara perkuliahan selama ini dan cantumkan usulan untuk perkuliahan setelah UTS.
Cara perkuliahan selama ini jarang melakukan practice, namun dengan diberikan pr/tugas sangat membantu dalam mendalami materi. Namun juga terkadang menjadi boomerang untuk sebagian mahasiswa sehingga semakin tidak mengerti. Selain itu, jam kuliah tidak sesuai dengan beban sks yang diberikan.


## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.
sistem fisis yang menarik bagi saya adalah osilasi teredam, karena banyak sistem fisis yang penyelesaian mirip dengan osilasi teredam


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
saya tertaruk dengan simulasi dan visualisasi. Topik yang ingin saya simulasikan adalah topik penyelesaian sistem fisis dengan metode Monte Carlo. Untuk pustaka python yang perlu digunakan adalah random.uniform atau sintax lain yang berkaitan dengan metode Monte Carlo.
