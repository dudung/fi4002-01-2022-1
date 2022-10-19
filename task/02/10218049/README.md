# 10218049
Hasan Wahab Syamsul Bani

## materi sebelumnya
+ Metode euler, runge kutta orde 4, monte carlo.
+ persamaan predator prey(lotka volttera), persamaan rekursif, osilasi teredam, double spring


## materi paling menarik
+ Metode monte carlo, karena dengan pendekatan bilangan acak dapat menentukan hasil(baik itu luas, nilai dalain lain)

## materi paling membosankan
+ belum menemukan materi yang membosankan, hanya kesulitan memahami di bagian codingnya


## materi yang sudah dipami
+ runge kutta orde 4, euler, predator prey, monte carlo konsep


## materi yang belum dipahami
+ double spring


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
import matplotlib.pyplot as plt
import numpy as np

def rk4(r, t, h):    
    
        # Runge-Kutta Orde 4
        
        k1 = h*f(r, t)
        k2 = h*f(r+0.5*k1, t+0.5*h)
        k3 = h*f(r+0.5*k2, t+0.5*h)
        k4 = h*f(r+k3, t+h)
        return (k1 + 2*k2 + 2*k3 + k4)/6

def f(r, t):
    
        # Parameter
        # x adalah prey
        # y adalah predator
        alpha = 1.0
        beta = 0.5
        gamma = 0.5
        sigma = 2.0
        x, y = r[0], r[1]
        fxd = (x*alpha) - (beta*x*y)       # dx/dt
        fyd = (-y*gamma) + (sigma*x*y)     # dy/dt
        return np.array([fxd, fyd], float) 

h=0.001                               
tpoints = np.arange(0, 30, h)   # dari t = 0 ke t = 30      
xpoints, ypoints  = [], []
r = np.array([2, 2], float)     # kondisi awal x = y = 2
for t in tpoints:
        xpoints.append(r[0])          
        ypoints.append(r[1])          
        r += rk4(r, t, h)             
plt.plot(tpoints, xpoints)      # grafik prey (biru)
plt.plot(tpoints, ypoints)      # grafik predator (kuning)
plt.xlabel("Waktu")
plt.ylabel("Populasi")
plt.title("Lotka-Volterra Model")
plt.savefig("Lotka_Volterra.png")
plt.show()
```

Hasilnya adalah
grafik populasi terhadap waktu untuk lotka volttera
```
```


## cara perkuliahan
+ mungkin untuk konsep bisa dimengerti tapi untuk praktik pada programming masih kesulitan

## topik sistem fisis
+ analisis gangguan(noise) sehingga dapat mengamati sesuatu abnormal sehingga dapat diidentifikasi suatu kejadian tertentu yang sedang terjadi

## simulasi dan visualisasi
+ saya tertarik dengan visualisasi data, karena dapat melihat trend dari suatu set data sehingga dapat ditentukan langkah efektif ke depannya.
