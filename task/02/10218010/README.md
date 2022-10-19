# 10218010
Dhika Arya R. B.


## materi sebelumnya
Sebelumnya telah diberikan materi mengenai bagaimana simulasi dan komputasi dapat membantu memahami sebuah proses fisis yang beberapa diantaranya adalah difusi panas serta osilasi harmonik dalam mekanika klasik, memahami proses fisis ini kemudian dipermudah lagi ketika kita menggunakan grafik untuk memahami bagaimana perilaku dari suatu sistem fisis yang sedang diamati.


## materi paling menarik
+ Tuliskan materi yang paling menarik yang telah diberikan dan jelaskan mengapa menarik.


## materi paling membosankan
Materi yang paling menarik adalah keseluruhan, karena saya selalu tertarik dengan bagaimana sistem fisis bisa dimodelkan oleh karena sistem fisis yang dimodelkan umumnya hanyalah bayangan kita dan belum tentu ada secara fisik dan (bahkan) tidak dapat dibuat simulasi secara langsung di python (yang pada umumnya saya melihat sebagai contoh deep neural network dapat menghasilkan sesuatu yang nyata misalnya deteksi gambar)


## materi yang sudah dipahami
Menganalisis sistem fisis menggunakan metode runge-kutta orde 4 dan metode euler, yang tentu saja menggunakan pemrograman dalam memvisualisasikannya


## materi yang belum dipahami
Ingin lebih banyak mensimulasikan visual yang bergerak (animatif) daripada grafik terus terusan, dan tentu saja saya masih paham hanya sedikit dari grafik animatif ini dan ingin belajar lebih banyak


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.
Saya membuat sebuah program yang mensimulasikan bagaimana sebuah api dapat membakar sebuah hutan dengan beberapa faktor yang dipertimbangkan dalam program ini adalah jarak antar pohon ke pohon yang lain (yang mana api akan selalu mulai dari suatu titik yang saya buat random), dengan beberapa pohon juga dapat dibuat sebagai pohon cemara yang secara fisis lebih mudah terbakar, dan seberapa basah keadaan hutan yang membuat api kemudian sulit menjalar. Semua ini kemudian saya jadikan input setiap kali simulasi berjalan sehingga lebih praktis dilakukan, dengan hasilnya keluar dalam turtle graphics.
```python
import random
import turtle

class Tree():
    def __init__(self,burning=False,wetness=1.0,xpos=0,ypos=0):
        self.burning = burning
        self.wetness = wetness
        self.xpos = xpos
        self.ypos = ypos
    def changeBurning(self,burning):
        self.burning = burning

class Oak(Tree):
    def __init__(self,burning=False,wetness=1.0,xpos=0,ypos=0):
        super().__init__(burning,wetness,xpos,ypos)
        self.probCatch = 0.45/wetness
        self.xpos = xpos
        self.ypos = ypos
    def draw(self):
        '''stamps tree on screen'''
        t = turtle
        t.hideturtle()
        t.penup()
        t.setpos(self.xpos,self.ypos)
        if self.burning is False:
            t.color('green')
        else:
            t.color('red')
        t.shape('circle')
        t.shapesize(0.65)
        t.settiltangle(90)
        t.stamp()

class Pine(Tree):
    def __init__(self,burning=False,wetness=1.0,xpos=0,ypos=0):
        super().__init__(burning,wetness,xpos,ypos)
        self.probCatch = 0.95/wetness
        self.xpos = xpos
        self.ypos = ypos
    def draw(self):
        '''stamps tree on screen'''
        t = turtle
        t.hideturtle()
        t.penup()
        t.setpos(self.xpos,self.ypos)
        if self.burning is False:
            t.color('green')
        else:
            t.color('red')
        t.shape('triangle')
        t.shapesize(0.65)
        t.settiltangle(90)
        t.stamp()
        
from tree import *

class Forest():
    def __init__(self):
        self.forestList = []

    def prompts(self):
        '''prompts for density, percentPine, and wetness, and returns values'''
        density = float(input('What percentage of grid cells are occupied by trees? (0.10-1): '))
        percentPine = float(input('What percentage of trees are pine? (0.00-1): '))
        wetness = float(input('How wet is the forest? (1-3),(1=dry,3=wet): '))
        return density,percentPine,wetness

    def initialize_forest_list(self,density,percentPine,wetness):
        '''Loop that adds trees to self.forestlist'''
        for i in range(40):
            for j in range(40):
                random_density = random.uniform(0.1,1)
                if random_density <= density:
                    random_pine = random.uniform(0.0,1)
                    if random_pine <= percentPine:
                        obj = Pine(False,wetness,j,i)
                        self.addTree(obj)
                    else:
                        obj = Oak(False,wetness,j,i)
                        self.addTree(obj)
                else:
                    self.addTree(None)

    def initial_tree_on_fire(self):
        '''Setting a random tree on fire'''
        newList = []
        count=0
        for obj in self.forestList:
            if obj is not None:
                newList += [count]
            count += 1
        number = random.randint(0,len(newList)-1)
        fire_index = newList[number]
        self.forestList[fire_index].changeBurning(True)

    def addTree(self,obj):
        '''adds Tree to Forest'''
        self.forestList += [obj]
        
    def removeTree(self,index):
        '''removes Tree from Forest'''
        self.forestList[index] = None
        
    def update(self):
        '''updates burning status of trees in forest'''
        oldBurningTrees = []
        newBurningTrees = []
        forestlist = self.getForestList()
        for i in range(len(forestlist)):
            obj = forestlist[i]
            if obj != None:
                if obj.burning is True:
                    oldBurningTrees += [i]
                else:                   
                    random_num = random.random()
                    if random_num < obj.probCatch:
                        if self.hasBurningNeighbor(obj) is True:
                            newBurningTrees += [i]
        for i in oldBurningTrees:
            forestlist[i] = None
        for i in newBurningTrees:
            obj = forestlist[i]
            obj.burning = True
        self.forestList = forestlist
        
    def getForestList(self):
        '''returns forest list'''
        return self.forestList
    
    def isBurning(self):
        '''returns True if a tree is burning in forest, false otherwise'''
        count=0
        for obj in self.forestList:
            if obj != None:
                if obj.burning is True:
                    count+=1
        if count > 0:
            return True
        else:
            return False
        
    def hasBurningNeighbor(self,obj):
        '''checks if any neighbors are burning'''
        for tree in self.forestList:
            if (tree != None) and (obj != None):
                if tree is obj:
                    pass
                elif ((tree.xpos-obj.xpos) in range(-1,2)) and ((tree.ypos-obj.ypos) in range(-1,2)):
                    if tree.burning is True:
                        return True
            
    def redraw(self):
        '''redraws graphic display'''
        turtle.clearstamps()
        turtle.tracer(0,0)
        for obj in self.forestList:
            if obj != None:
                obj.draw()
        turtle.update()

from forest import *
def main():
    t = turtle
    f = Forest()
    density,percentPine,wetness = f.prompts()
    f.initialize_forest_list(density,percentPine,wetness)
    f.initial_tree_on_fire()
    t.setworldcoordinates(0,0,40,40)
    f.redraw()
    done = False
    while not done:
        f.update()
        f.redraw()
        if f.isBurning() is False:
            done is True
            
main()
```

Hasilnya adalah (pohon cemara adalah segitiga hijau dan pohon biasa lingkaran hijau) <br/> 

![Alt_text](Program1.png)<br/>
![Alt_text](Program2.png)<br/>
![Alt_text](Hutan kering pohon biasa.png)<br/>
![Alt_text](Hutan kering banyak cemara.png)<br/>
![Alt_text](Hutan basah pohon biasa.png)<br/>
![Alt_text](Hutan basah banyak cemara.png)<br/>


## cara perkuliahan
Banyak hands on pak saya suka kalo hands on

## topik sistem fisis
Sistem fisis ya pak, saya ga begitu mau sih pak kalau boleh malah analisa data dong pak kayaknya lebih seru dan bermanfaat deh hehe


## simulasi dan visualisasi
Saya tertarik dengan simulasi dan visualisasi 3D yang beranimasi, saya ingin melihat sistem fisis atau apapun itu dalam sistem 3D dan tidak lagi dengan 2D, mungkin ini akan membantu pak https://matplotlib.org/2.1.2/gallery/animation/simple_3danim.html
