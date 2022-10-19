# 10219073
Aulia Marissa


## materi sebelumnya
+ Basic coding, Grafik, Fractal and Rekursif, Persamaan predator-prey, persamaan Lorenz, Persamaan Euler, Runge Kutta, flowchart, algorithm, pseudocode, sistem bandul terkopel, persamaan (laplace, poisson, helmholtz), sistem pegas teredam, Monte-Carlo, bilangan acak, DFT dan FFT

## materi paling menarik
+ Monte Carlo


## materi paling membosankan
+ DFT dan FFT

## materi yang sudah dipami
+ Persamaan Diferensial


## materi yang belum dipahami
+ DFT dan FFT, penerapan Runge Kutta

## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python

import numpy as np
import matplotlib.pyplot as plt

#Input data
m = 10.0
ko = 4.0
r = 2.0

def integrate(F,x,y,xStop,h):
  def run_kut4(F,x,y,h):
    K0 = h*F(x,y)
    K1 = h*F(x+h/2.0, y+K0/2.0)
    K2 = h*F(x+h/2.0, y+K1/2.0)
    K3 = h*F(x+h, y+K2)
    return (K0+2.0*K1+2.0*K2+K3)/6.0

  X =[]
  Y =[]
  X.append(x)
  Y.append(y)
  while x<xStop:
    h = min(h,xStop-x)
    y = y+run_kut4(F,x,y,h)
    x = x+h
    X.append(x)
    Y.append(y)
  return np.array(X), np.array(Y)



#Persamaan diferensial biasa sistem pegas teredam
def F(x,y):
  F =np.zeros(2)
  F[0]=y[1]
  F[1]=-(ko/m)*y[0]-(r/m)*y[1]
  return F

x = 0.0 #mulai menghitung
xStop = 50.0 #selesai menghitung
y = np.array([0.1, 0.1]) #kondisi awal (y)
h = 0.1 #step size
freq = 50
#solusi numerik menggunakan Runge-Kutta orde 4
X,Y = integrate(F,x,y,xStop,h)

#memplot nilai solusi numerik
plt.subplot(2,1,1)
plt.plot(Y[:,0],Y[:,1],'-')
plt.title('Diagram Fase Sistem Pegas Teredam')
plt.xlabel('Waktu t'); plt.ylabel('Dinamika')
plt.grid(True)

plt.subplot(2,1,2)
plt.plot(X,Y[:,0],'o',X,Y[:,1],'s-')
plt.title('Time Series Sistem Pegas Teredam')
plt.xlabel('Waktu t'); plt.ylabel('Dinamika')
plt.grid(True)

plt.tight_layout()

```


Hasilnya adalah

```
https://user-images.githubusercontent.com/91540073/196602239-095732c7-7339-404b-b73f-514703a5ece2.png
```


## cara perkuliahan
+ cukup menjelaskan dasar-dasarnya tetapi kurang latihan karena keterbatasan internet dan jumlah colokan pada kelas sebelum UTS


## topik sistem fisis
+ Bandul terikat pada pegas


## simulasi dan visualisasi
+ tertarik, sistem bandul dan pegas, library diferensial
