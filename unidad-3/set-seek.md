# Unidad 3

## 🔎 Fase: Set + Seek

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**

```py
from microbit import *
import utime

class Semaforo:
    def __init__(self,columna, tR,tY,tG):
        self.col= columna
        self.tr= tR
        self.ty =tY
        self.tg= tG
        display.set_pixel(self.col,0,9)
        self.interval= self.tr
        self.starTime=utime.ticks_ms()

        self.state="waitInRed"
        
    def update(self): 
        if self.state == "waitInRed":
            if utime.ticks_diff(utime.ticks_ms(),self.starTime)>= self.interval:
                display.set_pixel(self.col,0,0)
                display.set_pixel(self.col,1,9)
                self.interval= self.ty 
                self.starTime=utime.ticks_ms()
                self.state="waitInYellow"
        if self.state == "waitInYellow":
            if utime.ticks_diff(utime.ticks_ms(),self.starTime)>= self.interval:
                display.set_pixel(self.col,1,0)
                display.set_pixel(self.col,2,9)
                self.interval= self.tg
                self.starTime=utime.ticks_ms()
                self.state="waitInGreen"
        if self.state == "waitInGreen":
            if utime.ticks_diff(utime.ticks_ms(),self.starTime)>= self.interval:
                display.set_pixel(self.col,2,0)
                display.set_pixel(self.col,0,9)
                self.interval= self.tr
                self.starTime=utime.ticks_ms()
                self.state="waitInRed"
           
            

semaforo1 = Semaforo(0,5000,2000,3000)
semaforo2 = Semaforo(2,3000,1000,2000)
semaforo3 = Semaforo(4,4000,3000,2000)

while True:
    semaforo1.update()
    semaforo2.update()
    semaforo3.update()
```
>- [¿Qué ventajas tiene usar una clase (class) en este caso para representar un semáforo?]
>No tnemeos necesidad de estllar declarando las vaiables antes de escribir el while true. Además de que es más directo y compacto
>- [¿Puedes ver cómo la técnica de programación con máquinas de estado y el uso de funciona no bloqueantes te permite que varios semáforos funcionen al mismo tiempo?]
>  Me dí a entender como puedo programar todo lo que necesito en la propia microbit, sin necesidad de crear multiples estados, intervalos y variables

## **ACTIVIDAD 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**

```py
from microbit import *
import utime

STATE_INIT = 0
STATE_CONFIGURACION = 1
STATE_ARMED=2
STATE_EXPLODE=3
keyCount=0
PASSWORD=["A","B","A"]
keys=[" "]*len(PASSWORD)

current_state = STATE_INIT
ARMED_INTERVAL = 20000 
NUM=0
EXPLODE_INTERVAL=1000
start_time = 0
interval = 0

while True:
    if current_state == STATE_INIT:
        start_time = utime.ticks_ms()
        current_state = STATE_CONFIGURACION

    elif current_state == STATE_CONFIGURACION:
        display.show(Image.BUTTERFLY)
        if button_a.was_pressed():
            ARMED_INTERVAL += 1000
            current_state=STATE_CONFIGURACION

        if button_b.was_pressed():
            if ARMED_INTERVAL>1000:
                ARMED_INTERVAL -= 1000
                current_state=STATE_CONFIGURACION

        if accelerometer.was_gesture('shake'):
            start_time = utime.ticks_ms() 
            interval=ARMED_INTERVAL
            current_state= STATE_ARMED
    elif current_state == STATE_ARMED:
        if utime.ticks_diff(utime.ticks_ms(),start_time)>1000:
            display.show(str(NUM))
            start_time=utime.ticks_ms()
            NUM=int(ARMED_INTERVAL/1000)
            ARMED_INTERVAL-=1000
            if NUM>0:
                current_state=STATE_ARMED
            elif NUM<0:
                current_state= STATE_EXPLODE
        if button_a.was_pressed():
            keys[keyCount]="A"
            keyCount = keyCount+1
        if button_b.was_pressed():
             keys[keyCount]="B"
             keyCount = keyCount+1
        if keyCount==3:
            keyCount=0
            if keys==PASSWORD:
                NUM=20
                display.show(NUM,wait=False)
                current_state= STATE_CONFIGURACION
    elif current_state==STATE_EXPLODE:
        display.clear()
        audio.play(Sound.HELLO)
        if pin_logo.is_touched():
            current_state=STATE_CONFIGURACION
```

## **ACTIVIDAD 03 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```py
# Imports go at the top
from microbit import *
import utime

display.clear()

class Event:
    def __init__(self):
        self.value = 0

    def set(self,_val):
        self.value = _val

    def clear(self):
        self.value = 0

    def read(self):
        return self.value

class SerialTask:
    def __init__(self):
        uart.init(baudrate=115200)

    def update(self):
        if uart.any():
            data = uart.read(1)
            if data:
                if data[0] == ord('A'):
                    event.set('A')
                elif data[0] == ord('B'):
                    event.set('B')
                elif data[0] == ord('S'):
                    event.set('S')
                elif data[0] == ord('T'):
                    event.set('T')


class ButtonTask:
    def __init__(self):
        pass

    def update(self):
        if button_a.was_pressed():
            event.set('A')
        elif button_b.was_pressed():
            event.set('B')
        elif accelerometer.was_gesture('shake'):
            event.set('S')
        elif pin_logo.is_touched():
            event.set('T')

class BombTask:
    def __init__(self):
        self.PASSWORD = ['A','B','A']
        self.key = ['']*len(self.PASSWORD)
        self.keyindex = 0
        self.count = 20
        self.startTime = utime.ticks_ms()
        self.state = 'CONFIG'
        display.clear()
        display.show(self.count,wait=False)

    def update(self):
        if self.state == 'CONFIG':
            if event.read() == 'A':
                event.clear()
                self.count = min(self.count+1,60)
                display.show(self.count,wait=False)

            if event.read() == 'B':
                event.clear()
                self.count = max(10,self.count-1)
                display.show(self.count, wait=False)

            if event.read() == 'S':
                event.clear()
                self.startTime = utime.ticks_ms()
                self.state = 'ARMED'

        elif self.state == 'ARMED':
            if utime.ticks_diff(utime.ticks_ms(),self.startTime) > 1000:
                self.startTime = utime.ticks_ms()
                self.count = self.count - 1
                display.show(self.count,wait=False)
                if self.count == 0:
                    display.show(Image.SKULL)
                    self.state = 'EXPLODED'

            if event.read() == 'A':
                event.clear()
                self.key[self.keyindex] = 'A'
                self.keyindex = self.keyindex + 1

            if event.read() == 'B':
                event.clear()
                self.key[self.keyindex] = 'B'
                self.keyindex = self.keyindex + 1

            if self.keyindex == len(self.key):

                passIsOK = True
                for i in range(len(self.key)):
                    if self.key[i] != self.PASSWORD[i]:
                        passIsOK = False
                        break;
                if passIsOK == True:
                    self.count = 20
                    display.show(self.count,wait=False)
                    self.keyindex = 0
                    self.state = 'CONFIG'
                else:
                    self.keyindex = 0

        elif self.state == 'EXPLODED':
            if event.read() == 'T':
                event.clear()
                self.count = 20
                display.show(self.count,wait=False)
                self.startTime = utime.ticks_ms()
                self.state = 'CONFIG'

bombTask = BombTask()
serialTask = SerialTask()
buttonTask = ButtonTask()
event = Event()

while True:
    serialTask.update()
    buttonTask.update()
    bombTask.update()
```

## **ACTIVIDAD 04 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
# Imports go at the top
from microbit import *
import utime

display.clear()

class Event:
    def __init__(self):
        self.value = 0

    def set(self,_val):
        self.value = _val

    def clear(self):
        self.value = 0

    def read(self):
        return self.value

class SerialTask:
    def __init__(self):
        uart.init(baudrate=115200)

    def update(self):
        if uart.any():
            data = uart.read(1)
            if data:
                if data[0] == ord('A'):
                    event.set('A')
                elif data[0] == ord('B'):
                    event.set('B')
                elif data[0] == ord('S'):
                    event.set('S')
                elif data[0] == ord('T'):
                    event.set('T')


class ButtonTask:
    def __init__(self):
        pass

    def update(self):
        if button_a.was_pressed():
            event.set('A')
        elif button_b.was_pressed():
            event.set('B')
        elif accelerometer.was_gesture('shake'):
            event.set('S')
        elif pin_logo.is_touched():
            event.set('T')

class BombTask:
    def __init__(self):
        self.PASSWORD = ['A','B','A']
        self.key = ['']*len(self.PASSWORD)
        self.keyindex = 0
        self.count = 20
        self.startTime = utime.ticks_ms()
        self.state = 'CONFIG'
        display.clear()
        display.show(self.count,wait=False)

    def update(self):
        if self.state == 'CONFIG':
            if event.read() == 'A':
                event.clear()
                self.count = min(self.count+1,60)
                display.show(self.count,wait=False)

            if event.read() == 'B':
                event.clear()
                self.count = max(10,self.count-1)
                display.show(self.count, wait=False)

            if event.read() == 'S':
                event.clear()
                self.startTime = utime.ticks_ms()
                self.state = 'ARMED'

        elif self.state == 'ARMED':
            if utime.ticks_diff(utime.ticks_ms(),self.startTime) > 1000:
                self.startTime = utime.ticks_ms()
                self.count = self.count - 1
                display.show(self.count,wait=False)
                if self.count == 0:
                    display.show(Image.SKULL)
                    self.state = 'EXPLODED'

            if event.read() == 'A':
                event.clear()
                self.key[self.keyindex] = 'A'
                self.keyindex = self.keyindex + 1

            if event.read() == 'B':
                event.clear()
                self.key[self.keyindex] = 'B'
                self.keyindex = self.keyindex + 1

            if self.keyindex == len(self.key):

                passIsOK = True
                for i in range(len(self.key)):
                    if self.key[i] != self.PASSWORD[i]:
                        passIsOK = False
                        break;
                if passIsOK == True:
                    self.count = 20
                    display.show(self.count,wait=False)
                    self.keyindex = 0
                    self.state = 'CONFIG'
                else:
                    self.keyindex = 0

        elif self.state == 'EXPLODED':
            if event.read() == 'T':
                event.clear()
                self.count = 20
                display.show(self.count,wait=False)
                self.startTime = utime.ticks_ms()
                self.state = 'CONFIG'

bombTask = BombTask()
serialTask = SerialTask()
buttonTask = ButtonTask()
event = Event()

while True:
    serialTask.update()
    buttonTask.update()
    bombTask.update()
```
<img width="636" height="230" alt="image" src="https://github.com/user-attachments/assets/c630a9aa-7a1d-41a7-a84e-4ab4972b4028" />

