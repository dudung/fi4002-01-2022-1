# 10219111
Michael Alfarino B. P.


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
+ Heat equation, karena terlihat menarik jika di plot dan animate hasilnya.


## materi paling membosankan
+ Tidak ada.


## materi yang sudah dipahami
+ Runge-Kutta, Euler, Monte-Carlo, Partial Differential Equation.


## materi yang belum dipahami
+ Fourier transform.


## contoh program
+ Difusi panas 2 dimensi

```python
import numpy
from matplotlib import pyplot, cm
from mpl_toolkits.mplot3d import Axes3D ##library for 3d projection plots

###variable declarations
nx = 31
ny = 31
nt = 17
nu = .05
dx = 2 / (nx - 1)
dy = 2 / (ny - 1)
sigma = .25
dt = sigma * dx * dy / nu

x = numpy.linspace(0, 2, nx)
y = numpy.linspace(0, 2, ny)

u = numpy.ones((ny, nx))  # create a 1xn vector of 1's
un = numpy.ones((ny, nx))

###Assign initial conditions
# set hat function I.C. : u(.5<=x<=1 && .5<=y<=1 ) is 2
u[int(.5 / dy):int(1 / dy + 1),int(.5 / dx):int(1 / dx + 1)] = 2 

###Run through nt timesteps
def diffuse(tFinal):
    t = numpy.arange(0, tFinal, dt)
    u[int(.5 / dy):int(1 / dy + 1),int(.5 / dx):int(1 / dx + 1)] = 2  
    
    for n in t: 
        un = u.copy()
        u[1:-1, 1:-1] = (un[1:-1,1:-1] + 
                        nu * dt / dx**2 * 
                        (un[1:-1, 2:] - 2 * un[1:-1, 1:-1] + un[1:-1, 0:-2]) +
                        nu * dt / dy**2 * 
                        (un[2:,1: -1] - 2 * un[1:-1, 1:-1] + un[0:-2, 1:-1]))
        u[0, :] = 1
        u[-1, :] = 1
        u[:, 0] = 1
        u[:, -1] = 1

    
    fig = pyplot.figure()
    ax = fig.add_subplot(projection='3d')
    surf = ax.plot_surface(X, Y, u[:], rstride=1, cstride=1, cmap=cm.viridis,
        linewidth=0, antialiased=True)
    ax.set_zlim(1, 2.5)
    ax.set_xlabel('$x$')
    ax.set_ylabel('$y$');
    
diffuse(.5)

```

Hasilnya adalah

![image](https://user-images.githubusercontent.com/60033893/196671374-8fdefcbf-7c86-4624-8b85-521354e9e708.png)


## cara perkuliahan
+  Perkuliahan selama ini kurang melibatkan praktek sehingga menyulitkan mahasiswa dalam mencoba secara langsung materi yg diajarkan. Perkuliahan sudah mulai dilaksanakan di labkom sehingga mahasiswa dapat praktek sejalan dengan materi yang diajarkan.


## topik sistem fisis
+ Aliran fluida menggunakan persamaan Navier-Stokes. Karena menarik bagaimana kita dapat mensimulasikan aliran fluida secara numerik serta menarik jika dilakukan visualisasinya.


## simulasi dan visualisasi
+ Aplikasi deep learning dalam berbagai hal, karena menarik bagaimana komputer dapat belajar sendiri dengan kita hanya memberikan komputer data yang akan dipelajari.
   Library menggunakan tensorflow.
