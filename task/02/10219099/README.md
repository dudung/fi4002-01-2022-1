# 10219099
Annisa Kemala Sari


## materi sebelumnya
- Mempelajari rekursif dan fraktal
- Menyelesaikan persamaan diferensial (persamaan Lorenz dan Predator Prey) dengan beberapa metode
- Metode Euler
- Metode Runge Kutta Orde 4
- Metode Monte Carlo
- Osilasi Harmonik Sederhana kasus bandul sederhana
- Osilasi Harmonik Sederhana kasus Teredam (Underdamped,Overdamped,Criticaldamped)
- Mengenal bilangan acak (definisi,cara membangkitkan bilangan acak,dll)
- Discrete Fourier Transform (DFT) dan Fast Fourier Transform (FFT)
- Memperoleh solusi numerik menggunakan metode RungeKutta orde 4
- Menghitung temperatur di setiap titik dengan matriks


## materi paling menarik
- Materi yang paling menarik salah satunya adalah materi fraktal / self similarity, walaupun tidak terlalu banyak dijelaskan dan hanya dijelaskan di awal pertemuan tetapi menurut saya menarik karena pola-pola yang diperoleh dari hasil code yang dibuat dapat dilihat di kehidupan sehari-hari seperti pola daun, pohon, es, dan lain-lain
- Materi lainnya yaitu saat menghitung temperatur di setiap titik yang sudah ditentukan temperatur sisi nya, menarik karena ternyata temperatur pada setiap titik bisa berbeda-beda dan ternyata bisa dihitung dengan cara yang lumayan mudah jika matriks nya tidak terlalu besar


## materi paling membosankan
Menurut saya tidak ada materi yang membosankan karena pada kelas simulasi dan pemodelan sistem fisis ini merupakan ilmu baru bagi saya dan saya berusaha untuk memahami semua materi yang diberikan oleh dosen pengampu


## materi yang sudah dipami
- materi rekursif
- materi persamaan predator prey


## materi yang belum dipahami
- materi DFT dan FFT masih kurang paham
- materi rungekutta orde 4 masih kurang paham untuk menggunakan nya untuk setiap kasus yang berbeda-beda


## contoh program
Menyelesaikan persamaan Predator-Prey menggunakan Metode Euler

SOAL
berikut adalah persamaan predator-prey antara Q sebagai srigala dan P sebgai domba
dengan menggunakan metode euler selesaikan pers dif berikut ini

dP/dt = k1P - cPQ
dQ/dt = -k2Q + dPQ

dengan kondisi awal

Q = Qo , P = Po, pada t=0

lukislah grafik untuk ∆t=0,005 selama t=7tahun

(d=0,002, c=0,001, k1=2, k2=10)

```python
import numpy as np
import matplotlib.pyplot as plt

#fungsi pada python, menerjemahkan persamaan diferensial/dinamika sistem fisis
def predprey (p,q,k1=10,k2=2,d=0.002,c=0.001):
    p_dot=k1*p-c*p*q
    q_dot=-k2*q+d*p*q
    return p_dot, q_dot

dt = 0.005
#num_steps=1400
num_steps = 3000

ps = np.empty(num_steps + 1)
qs = np.empty(num_steps + 1)
ts = np.empty(num_steps + 1)

ps [0], qs[0]= (100.0 , 3000.0)

for i in range (num_steps):
    p_dot, q_dot = predprey(ps[i],qs[i])
    ps[i+1] = ps[i] + (p_dot * dt)
    qs[i+1] = qs[i] + (q_dot * dt)
    ts[i+1] = i
    
plt.plot(ts,qs,ts,ps)
plt.legend(('srigala','domba'),loc=1)
plt.grid()
plt.show()
```

Hasilnya adalah


![image](https://user-images.githubusercontent.com/97930056/196588622-5cce76fa-1f9e-4f03-8ade-1e0dfbce4f78.png)



## cara perkuliahan
Menurut saya perkuliahan sudah berjalan cukup baik, kami selaku mahasiswa dituntut untuk bisa mengerti, mengulik, dan mempraktikan langsung code-code yang diberikan dosen setiap kelas karena untuk programming harus selalu praktik agar bisa lebih mudah paham. namun pada beban sks tercantum bahwa mata kuliah spsf ini hanya 3 sks sedangkan pada perkuliahan selalu berjalan seperti 4 sks karena setiap rabu dan jumat selalu digunakan 2 jam setiap harinya.


## topik sistem fisis
Untuk saat ini, belum ada topik yang menurut saya menarik dan ingin dikaji lebih dalam. mungkin untuk beberapa waktu ke depan saya akan mencari apa saja topik yang menarik untuk dibahas dan dikaji


## simulasi dan visualisasi
Karena mengambil mata kuliah ini, saya tertarik sekali dengan simulasi dan visualisasi ini, namun untuk saat ini saya masih belajar dan proses memahami sehingga belum ada topik yang ingin saya kaji atau coba simulasikan. mungkin kedepannya setelah beberapa waktu saya akan merasa penasaran dengan sesuatu menganai simulasi dan visualisasi ini.
