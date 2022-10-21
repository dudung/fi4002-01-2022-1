# 10219019
Abdu Rafie


## materi sebelumnya
+ Runge-kutta, monte carlo, fourier, dll


## materi paling menarik
+ Runge-kutta orde 4 karena saya melihat metode tersebut dapat di aplikasikan pada banyak hal


## materi paling membosankan
+ Runge-kutta orde 4 karena diulang-ulang terus


## materi yang sudah dipami
+ Runge-kutta orde 4

## materi yang belum dipahami
+ monte carlo karena saya belum baca-baca dan explore lebih dalam


## contoh program
+ import numpy as np
import matplotlib.pyplot as plt

# implementasi runge kutta

def integrate(F,x,y,xStop,h):
    def runkut4(F,x,y,h):
        k0 = F(x, y)
        k1 = F(x + h / 2.0, y + k0 / 2.0)
        k2 = F(x + h / 2.0, y + k1 / 2.0)
        k3 = F(x + h, y + k2)
        return h*(k0+2.0*k1+2.0*k2+k3)/6.0

    X = []
    Y = []
    X.append(x)
    Y.append(y)
    while x < xStop:
        h = min(h, xStop)
        y = y + runkut4(F,x,y,h)
        x = x + h
        X.append(x)
        Y.append(y)
    return np.array(X),np.array(Y)


m = 3727.379
E = 20
V = 0
h_bar = 197.3269804
alpha = 2*m*(E-V)/(h_bar*h_bar)

def F(x,y):
    F = - alpha*y
    return F

x = 0.0
xStop = 50
y = 0.1
h = 0.1
X,Y = integrate(F,x,y,xStop,h)

plt.plot(X,Y,'o-')
plt.xlabel('x');plt.ylabel('V')

## cara perkuliahan
+ Baru terjadi 2x kuliah setelah uts. Yang pertama saya nggak masuk karena nggak enak badan, yang kedua (tadi) tidak banyak yang disampaikan.


## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
