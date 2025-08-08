# Unidad 2

## 🛠 Fase: Apply
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 04 ༓☾∘∙•⋅⋅⊰⋅•⋅**

## **ACTIVIDAD 05 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```py
from microbit import *
import music
import utime

STATE_CONFIG = 0
STATE_ARMED = 1
STATE_EXPLODED = 2

state = STATE_CONFIG
time_setting = 20  
min_time = 10
max_time = 60
last_time = utime.ticks_ms()

while True:
    current_time = utime.ticks_ms()

    if state == STATE_CONFIG:
        display.scroll(str(time_setting)) 

        if button_a.was_pressed():
            if time_setting < max_time:
                time_setting += 1

        if button_b.was_pressed():
            if time_setting > min_time:
                time_setting -= 1

        if accelerometer.was_gesture("shake"):
            countdown = time_setting
            start_time = utime.ticks_ms()
            state = STATE_ARMED

    elif state == STATE_ARMED:
        elapsed = utime.ticks_diff(current_time, start_time)
        remaining = countdown - elapsed // 1000

        if remaining >= 0:
            display.scroll(str(remaining))
        else:
            display.show(Image.SKULL)
            music.play(music.BA_DING)
            state = STATE_EXPLODED

    elif state == STATE_EXPLODED:
        if pin_logo.is_touched():
            time_setting = 20
            state = STATE_CONFIG
```
