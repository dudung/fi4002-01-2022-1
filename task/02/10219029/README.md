# 102191029
Isnaini Mufidahtul Mughni


## materi sebelumnya
+ Runge Kutta
+ Euler
+ Lorentz
+ Monte carlo
+ Fourier Transform
+ Sistem rantai membentang
+ Osilasi Harmonis
+ Predator prey


## materi paling menarik
+ Osilasi harmonis karena materi sudah dipelajari di kelas gelombang


## materi paling membosankan
+ Runge kutta karena susah


## materi yang sudah dipahami
+ Euler


## materi yang belum dipahami
+ Runge Kutta bagian menentukan variabel di kodingan


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
import matplotlib.pyplot as plt
import random

inside = 0
n = 100000

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
```

Hasilnya adalah

```
3.14444
```


## cara perkuliahan
+ Perkuliahan seru saat di comlabs atau mektan karena bisa langsung mencoba di pc


## topik sistem fisis
+ Matriks dalam Python dengan List 


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
+ Tidak
