# 10219051
Clarissa Ivana


## materi sebelumnya
+ Metode Euler dan Runge-Kutta orde 4 untuk menyelesaikan persamaan diferensial secara numerik
+ Metode Monte-Carlo dalam menghitung integral secara numerik
+ Menghitung persamaan diferensial parsial (Heat Equation) secara numerik
+ Fourier transform

model yang dicoba:
+ predator-prey
+ persamaan Lorenz
+ osilasi teredam
+ spring-mass system

## materi paling menarik
+ menghitung suhu dengan persamaan diferensial parsial, cukup menarik karena menggunakan kombinasi matriks juga untuk menyelesaikan


## materi paling membosankan
+ Tidak ada materi yang membosankan bagi saya

## materi yang sudah dipahami
+ metode euler, runge-kutta, monte carlo


## materi yang belum dipahami
+ Fourier transform


## contoh program

```python
import numpy as np
def integrate(F,x,y,xStop,h):

  def run_kut4(F,x,y,h):
    K0 = h*F(x,y)
    K1 = h*F(x + h/2.0, y + K0/2.0)
    K2 = h*F(x + h/2.0, y + K1/2.0)
    K3 = h*F(x +h, y + K2)
    return (K0 + 2.0*K1 + 2.0*K2 + K3)/6.0

  X = []
  Y = []
  X.append(x)
  Y.append(y)
  while x < xStop:
    h = min(h,xStop - x)
    y = y + run_kut4(F,x,y,h)
    x = x + h
    X.append(x)
    Y.append(y)
  return np.array(X, dtype=object),np.array(Y, dtype=object)
  
  import matplotlib.pyplot as plt

#Input data
m1=3.0
m2=5.0
ko1=3.0
ko2=2.0
g=9.8

#Persamaan diferensial biasa sistem 2 bandul 2 pegas
def F(x,y):
  F = np.zeros(8)
  F[0]=y[1]
  F[1]=(-ko1*y[0]-ko2*(y[0]-y[2]))
  F[2]=y[3]
  F[3]=(-ko2*(y[2]-y[0]))/m2
  F[4]=y[5]
  F[5]=(-ko1*y[4]-ko2*(y[4]-y[6])+m1+g)/m1
  F[6]=y[7]
  F[7]=(-ko2*(y[6]-y[4])+m2+g)/m2
  
  return F

x = 0.0 #Mulai menghitung
xStop = 50.0 #Selesai menghitung
y = np.array([0.1,0.1,0.1,0.1,0.1,0.1,0.1,0.1]) #Kondisi awal (y)
h = 0.1 #Step size
freq = 50
X,Y = integrate(F,x,y,xStop,h)

plt.figure(figsize=(10,10))
plt.subplot(3,1,1)
plt.plot(Y[:,4],Y[:,0],'-')
plt.title('Diagram fase Y1 vs X1')
plt.xlabel('X1')
plt.ylabel('Y1')
plt.grid(1)

plt.subplot(3,1,2)
plt.plot(Y[:,6],Y[:,2],'-')
plt.title('Diagram fase Y2 vs X2')
plt.xlabel('X2')
plt.ylabel('Y2')
plt.grid(1)

plt.subplot(3,1,3)
plt.plot(X,Y[:,0],'o-',X,Y[:,2],'o-',X,Y[:,4],'o-',X,Y[:,6],'o-')
plt.title('Time series sistem bandul dan pegas')
plt.xlabel('Waktu t')
plt.ylabel('Dinamika')
plt.legend(['x1','x2','y1','y2'])
plt.grid(1)
plt.tight_layout()
```

Hasilnya adalah

![download (1)](https://user-images.githubusercontent.com/79934330/196589740-42cc86d8-45ec-4338-917c-7a72180a0654.png)

```
```


## cara perkuliahan
+ untuk perkuliahan sudah dilaksanakan cukup baik, namun terkadang terlalu cepat sehingga perlu waktu tambahan untuk mengejar sendiri


## topik sistem fisis
+ saat ini belum terpikirkan untuk topik sistem fisis yang menarik


## simulasi dan visualisasi
+ saya tertarik dengan simulasi dan visualisasi, namun belum menemukan topik yang cocok
