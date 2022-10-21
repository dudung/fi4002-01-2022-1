# 10219062
Shalsabilla Varin Ramadhanti


## Materi sebelumnya
+ Tuliskan materi-materi sebelumnya yang telah diberikan dalam kuliah ini.
+ a. Metode Euler, menggunakan deret Taylor
+ b. Persamaan Lorentz dan Predator-Prey
+ c. Metode Runge-Kutta 4
+ d. Monte Carlo, menggunakan random number
+ e. Fourier Transform


## Materi paling menarik
+ Tuliskan materi yang paling menarik yang telah diberikan dan jelaskan mengapa menarik.

Menurut saya, materi yang paling menarik adalah metode Monte Carlo karena dengan menggunakan bilangan acak dapat menentukan suatu nilai dari problem yang ingin dicari, contoh: Luas dalam kurva, bentuk struktur protein, dll.


## Materi paling membosankan
+ Tuliskan materi yang telah diberikan yang paling membosankan dan jelaskan alasannya.

Menurut saya, tidak ada materi yang membosankan. Semua ilmu dan mentode yang diajarkan sangat bermanfaat dikemudian hari. Cuma, saya nya aja yang ngga ngerti-ngerti, mungkin kurang belajar dengan tekun juga.


## Materi yang sudah dipahami
+ Tuliskan materi-materi yang telah dipahami.

InsyaaAllah saya paham materinya, tapi kurang paham di kodingannya.


## Materi yang belum dipahami
+ Tuliskan materi-materi yang masih belum dipahami dan bagian mana yang belum serta ingin dipahami.

Kurang paham di kodingannya Pak, cara membuat kodingannya, iterasinya.


## Contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarannya.

```python
# contoh program python
ins = 0
n = 10000

x_ins= []
y_ins = []
x_outs = []
y_outs = []

for _ in range(n):
    x = random.uniform(-5.0,5.0) #panjang=10
    y = random.uniform(-2.0,16.0) #lebar=18
    if y <= x**2: #
        ins += 1
        x_ins.append(x)
        y_ins.append(y)
    else:
        x_outs.append(x)
        y_outs.append(y)

luas = 180*ins/n #180 dari luas persegi
print(luas) 

fig, ax = plt.subplots()
ax.set_aspect('equal')
ax.scatter(x_ins, y_ins, color='r', marker='s')
ax.scatter(x_outs, y_outs, color='b', marker='s')

plt.draw()
```

Hasilnya adalah

![image](https://user-images.githubusercontent.com/106875754/196922852-44758a75-a14a-47c9-aa5d-9112d36c0794.png)

```
```

## Cara perkuliahan
+ Tuliskan pendapat Anda mengenai cara perkuliahan selama ini dan cantumkan usulan untuk perkuliahan setelah UTS.

Perkuliahan selama ini yang saya rasakan, hhmm... materinya cukup jelas (Bisa ditingkatkan juga dengan baca-baca sumber lain), cuma ada beberapa bagian dari kodingannya yang saya belum pahami..
Usulan dari saya, mungkin dilakukan suatu pertemuan (setelah pertemuan membahas teori) untuk membahas kodingannya.


## Topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.

Sistem fisis yang menarik bagi saya untuk dikaji lebih dalam adalah tumbukan atom. Dengan mengetahui tumbukan atom, kita bisa tahu proses reaksi fisi pada reaktor.


## Simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pustaka Python yang perlu digunakan.

Ya, saya tertarik dengan simulasi dan visualisasi. 
Topik yang ingin saya simulasikan adalah simulasi fluida dari pendingin suatu reaktor berbahan bakar pebble.
Lalu, pustaka python yang perlu digunakan adalah.. hmm.. saya kurang tahu juga Pak.
