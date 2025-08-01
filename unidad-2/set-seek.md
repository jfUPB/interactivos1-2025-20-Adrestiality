# Unidad 2

## 🔎 Fase: Set + Seek
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**

```py
from microbit import *
import utime

class Pixel:
    def __init__(self,pixelX,pixelY,initState,interval):
        self.state = "Init"
        self.startTime = 0
        self.interval = interval
        self.pixelX = pixelX
        self.pixelY = pixelY
        self.pixelState = initState

    def update(self):

        if self.state == "Init":
            self.startTime = utime.ticks_ms()
            self.state = "WaitTimeout"
            display.set_pixel(self.pixelX,self.pixelY,self.pixelState)

        elif self.state == "WaitTimeout":
            if utime.ticks_diff(utime.ticks_ms(),self.startTime) > self.interval:
                self.startTime = utime.ticks_ms()
                if self.pixelState == 9:
                    self.pixelState = 0
                else:
                    self.pixelState = 9
                display.set_pixel(self.pixelX,self.pixelY,self.pixelState)

pixel1 = Pixel(0,0,0,1000)
pixel2 = Pixel(4,4,0,500)

while True:
    pixel1.update()
    pixel2.update()
```
-  **Bitácora** 𖤓 ☆ ☼ ⋆⋅**

**[DESCRIBE DETALLADAMENTE CÓMO FUNCIONA]**

Este código lo que hace es prender y apagar de manera intermitente y ritmos diferentes dos luces de la microbit que se encuentran en esquinas opuestas. Siendo el pixel1 (la lucecita 1) en la esquina superior izquierda y el pizel 2(lucecita 2) en la esquina inferior derecha. El pixel 1 se prende cada 1 segundo y el pixel 2 cada 1/2 segundo en un bucle infinito

**[¿CÚALES SON LOS ESTADOS DEL PROGRAMA?]** 

Tiene el estado Init, que es cuanndo el contador aun no ha empezado, y el WaitTimeout que es cuando esta esperando la siguiente instrucción

**[¿CÚALES SON LOS EVENTOS E INPUTS DEL PROGRAMA?]** 

Tiene el veneto Update que es el que ocurre en cada ciclo principal (while true) y el Interval es un evento de tiempo que cambia el estado del pixel, es como, ese limite de tiempo que debe esperar el pixel para volver a prenderse

**[¿CÚALES SON LAS ACCIONES DEL PROGRAMA?]** 

Se guarda el tiempo en startTime una vez se inicialice el tiempo
Se cambia el estado de Init a WaitTimeout una vez se inici el tiempo
Se encienden las luces con display.set_pixel cada vez que le corresponda
Se controla gradualmente la intencidad de las luces con self.pixelState, haciendo que se vean intensas (encendidas del todo, es decir, equivalentes a 9) o sin intensidad (apagadas, siendo 0)


## **ACTIVIDAD 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```py
from microbit import *
import utime

class Pixel:
    def __init__(self,pixelX,pixelY,initState,interval):
        self.state = "Init"
        self.startTime = 0
        self.interval = interval
        self.pixelX = pixelX
        self.pixelY = pixelY
        self.pixelState = initState

    def update(self):

        if self.state == "Init":
            self.startTime = utime.ticks_ms()
            self.state = "WaitTimeout"
            display.set_pixel(self.pixelX,self.pixelY,self.pixelState)

        elif self.state == "WaitTimeout":
            if utime.ticks_diff(utime.ticks_ms(),self.startTime) > self.interval:
                self.startTime = utime.ticks_ms()
                if self.pixelState == 9:
                    self.pixelState = 0
                else:
                    self.pixelState = 9
                display.set_pixel(self.pixelX,self.pixelY,self.pixelState)

pixel1 = Pixel(2,1,0,1000)
pixel2 = Pixel(2,2,0,2000)
pixel3 = Pixel(2,3,0,3000)

while True:
    pixel1.update()
    pixel2.update()
    pixel3.update()
```
> En realidad este código es exactamente el mismo al anterior, con la diferencia de que existe un tercer led a usar (pixel 3) y tienen ubicaciones idferentes para simular las luces del semaforo. Cada luz se prende una despues de otra

>Después de hacer que las tres luces se prendan, hay un desorden en los tiempos y no se vuelven a organizar. La verdad no supe como arreglarlo, ya que no entendí taaaaan bien en código en general

-  **Bitácora** 𖤓 ☆ ☼ ⋆⋅**

**[ESTADOS]**

Tiene el estado Init, que es cuanndo el contador aun no ha empezado, y el WaitTimeout que es cuando esta esperando la siguiente instrucción

**[EVENTOS]**

Tiene el veneto Update que es el que ocurre en cada ciclo principal (while true) y el Interval es un evento de tiempo que cambia el estado del pixel 

**[ACCIONES]** 

Se guarda el tiempo en startTime una vez se inicialice el tiempo

Se cambia el estado de Init a WaitTimeout una vez se inicia el tiempo

Se encienden las luces con display.set_pixel cada vez que le corresponda

Se controla gradualmente la intencidad de las luces con self.pixelState, haciendo que se vean intensas (encendidas del todo, es decir, equivalentes a 9) o sin intensidad (apagadas, siendo 0)

Cuando le corresponda, el pixel 1 espera 1 segundo, el pixel 2 espera 2 segundos y el pixel 3 espera 3 segundos. De modo en que se van prendiendo de arriba hacia abajo, como si estuviera pasando de rojo a verde... O mejor dicho, como si fueses a empezar una carrerita de mario kart
