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

## **ACTIVIDAD 03 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```PY
from microbit import *
import utime

STATE_INIT = 0
STATE_HAPPY = 1
STATE_SMILE = 2
STATE_SAD = 3

HAPPY_INTERVAL = 1500
SMILE_INTERVAL = 1000
SAD_INTERVAL = 2000

current_state = STATE_INIT
start_time = 0
interval = 0

while True:
    # pseudoestado STATE_INIT
    if current_state == STATE_INIT:
        display.show(Image.HAPPY)
        start_time = utime.ticks_ms()
        interval = HAPPY_INTERVAL
        current_state = STATE_HAPPY
    elif current_state == STATE_HAPPY:
        if button_a.was_pressed():
            # Acciones para el evento
            display.show(Image.SAD)
            # Acciones de entrada para el siguiente estado
            start_time = utime.ticks_ms()
            interval = SAD_INTERVAL
            current_state = STATE_SAD
        if utime.ticks_diff(utime.ticks_ms(), start_time) > interval:
            # Acciones para el evento
            display.show(Image.SMILE)
            # Acciones de entrada para el siguiente estado
            start_time = utime.ticks_ms()
            interval = SMILE_INTERVAL
            current_state = STATE_SMILE
    elif current_state == STATE_SMILE:
        if button_a.was_pressed():
            display.show(Image.HAPPY)
            start_time = utime.ticks_ms()
            interval = HAPPY_INTERVAL
            current_state = STATE_HAPPY
        if utime.ticks_diff(utime.ticks_ms(), start_time) > interval:
            display.show(Image.SAD)
            start_time = utime.ticks_ms()
            interval = SAD_INTERVAL
           current_state = STATE_SAD
    elif current_state == STATE_SAD:
        if button_a.was_pressed():
            display.show(Image.SMILE)
            start_time = utime.ticks_ms()
            interval = SMILE_INTERVAL
            current_state = STATE_SMILE
        if utime.ticks_diff(utime.ticks_ms(), start_time) > interval:
            display.show(Image.HAPPY)
            start_time = utime.ticks_ms()
            interval = HAPPY_INTERVAL
            current_state = STATE_HAPPY
```

-  **Bitácora** 𖤓 ☆ ☼ ⋆⋅**
// https://app.diagrams.net/ //

**[POR QUÉ EL PROGRAMA PERMITE REALIZAR DE MANERA CONCURRENTE VARIAS TAREAS]** 
Por que una vez estemos en uno de los estados, antes de que pase el tiempo necesario para el cambio de acción o de carita, si presionamos una tecla, podemos por asi decirlo redirigir el flujo de estados. Es como una tarea secundaria que se realiza en un caso específico.

**[ESTADOS]**
Son las propias caritas que realizamos en el programa. INIT, HAPPY, SMILE y SAD. 

**[EVENTOS]**
button_a.was_pressed() y utime.ticks_diff(...) > interval, que hacen referencia a cuando el botón a de la microbit fue presionado y cuando ha pasado un tiempo determinado desde el ultimo cambio respectivamente.

**[ACCIONES]** 
De init comienza el conteo del tiempo y pasa a HAPPY.
De HAPPY, si esperamos el tiempo necesario pasa a SMILE, pero si presionamos la tecla a, nos llevará a SAD.
De SMILE, si esperamos el tiempo necesario pasa a SAD, pero si presionamos la tecla a, nos llevará a HAPPY.
De SAD, si esperamos el tiempo necesario nos devuelve al inicio con HAPPY, pero si presionamos la tecla a, nos llevará a SMILE.

**[DESCRIBE Y APLICA AL MENOS 3 VECTORES]** 

> Para definir un vector de prueba debes llevar al sistema a un estado, generar los eventos y observar el estado siguiente y las acciones que ocurrirán. Por tanto, un vector de prueba tiene unas condiciones iniciales del sistema, unos resultados esperados y los resultados realmente obtenidos. Si el resultado obtenido es igual al esperado entonces el sistema pasó el vector de prueba, de lo contrario el sistema puede tener un error.

Tomando en cuenta el código con las caritas, podemos identificar 3 vectores de prueba diferentes
1. Si estamos en el estado SMILE, podemos pasar a HAPPY si se presiona el botón a
2. Si estamos en el estado SAD, podemos pasar a SMILE si se presiona el botón a
3. Si estamos en el estado HAPPY, podemos pasar a SAD si se presiona el botón a

