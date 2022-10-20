# 10219093
Dian Retno Anggraini


## materi sebelumnya
+ Tuliskan materi-materi sebelumnya yang telah diberikan dalam kuliah ini.

Materi yang telah dipelajari adalah Predator-Prey, Runge-Kutta, Euler, Osilasi Teredam, Monte Carlo, Sistem rantai membentang, Hukum II Newton, Fourier Transform


## materi paling menarik
+ Tuliskan materi yang paling menarik yang telah diberikan dan jelaskan mengapa menarik.

Materi yang menarik adalah Fourier Transform dimana materi ini sangat powerful sebagai tools yang dapat mengubah domain waktu atau spasial ke domain frekuensi sehingga diperoleh citra digital yang dapat dianalisis dan memberikan informasi terkait suatu sistem tertentu. Misalnya saja penerapan dalam fisika bumi dimana kita dapat menggunakan Fourier Tranasform dalam pemodelan dan penentuan cekungan di suatu daerah dengan metode gravitasi. Selain itu, Predator-prey dimana kita dapat mengetahui hubungan antar suatu elemen dengan elemen lainnya yang saling dependen dalam suatu sistem.


## materi paling membosankan
+ Tuliskan materi yang telah diberikan yang paling membosankan dan jelaskan alasannya.

Materi yang membosankan adalah Osilasi teredam dan Hukum II Newton karena telah sering ditemukan dalam beberapa kasus


## materi yang sudah dipami
+ Tuliskan materi-materi yang telah dipahami.

Materi yang sudah dipahami adalah Runge-Kutta, Euler, Osilasi Teredam, Monte Carlo, Hukum II Newton, Predator-Prey


## materi yang belum dipahami
+ Tuliskan materi-materi yang masih belum dipahami dan bagian mana yang belum serta ingin dipahami.

Materi yang belum dipahami adalah Fourier Transform


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python
import numpy as np
import matplotlib.pyplot as plt

def predprey(p, q, k1=10, k2=2, d=0.002, c=0.001):
  p_dot=k1*p-c*p*q
  q_dot=-k2*q+d*p*q
  return p_dot, q_dot

dt = 0.005
#num_steps = 1400
num_steps = 3000

ps = np.empty(num_steps+1)
qs = np.empty(num_steps+1)
ts = np.empty(num_steps+1)

ps[0], qs[0] = (100.0, 3000.0)
#ps[0], qs[0] = (100.0, 100.0)

for i in range(num_steps):
  p_dot, q_dot = predprey(ps[i], qs[i])
  ps[i+1] = ps[i] + (p_dot*dt) #metode euler
  qs[i+1] = qs[i] + (q_dot*dt)
  ts[i+1] = i

plt.plot(ts,qs,ts,ps)
plt.legend(('serigala','domba'),loc=1)
plt.show()

```

Hasilnya adalah

![download](https://user-images.githubusercontent.com/83079824/196689549-3838d8bd-6b9c-4426-a07d-036cceb4a1fa.png)


## cara perkuliahan
+ Tuliskan pendapat Anda mengenai cara perkuliahan selama ini dan cantumkan usulan untuk perkuliahan setelah UTS.

Cara perkuliahan saat ini cukup baik, hanya saja terkendala dengan ruangan yang membuat kami pun terkendala dalam practice pemrograman. Karena materi spsf ini sangat luas mungkin dari dosen pengampu bisa memberikan rekomendasi referensi terkait dengan mareti yang dibawakan.


## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.

FOURIER TRANSFORM ION CYCLOTRON RESONANCE MASS SPECTROMETRY
Keuntungan dari FT-ICR dibandingkan penganalisis massa lainnya adalah kemampuan massanya yang akurat.

![Screenshot (236)](https://user-images.githubusercontent.com/83079824/196639584-7ef1aded-4825-4417-8f6b-3cd7a40d0766.png)

Komposisi unsur masing-masing spesies dapat ditetapkan secara jelas berdasarkan akurasi massa sub-ppm. Komposisi unsur sangat penting dalam analisis semacam itu karena penting untuk mengidentifikasi dan memantau spesies yang mengandung sulfur dan nitrogen saat dihilangkan selama proses pemurnian bahan bakar


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.

Fourier analysis of short-period water level variations in geothermal field. Dimana secara jelas dapat mengidentifikasi variasi tekanan periodik yang diinduksi oleh pengaruh gangguan barometrik, gravitasi, termal, antropogenik, dan bawah permukaan yang dapat digunakan sebagai tolok ukur untuk mengidentifikasi dan mengukur perubahan perilaku yang merugikan. Pada analisis Fourier pada sinyal yang dihasilkan secara sintetis dengan tingkat putih yang berbeda
kebisingan dan impuls diskrit

1 import numpy as np

2 import scipy.sparse.linalg as sp

3 import itertools
