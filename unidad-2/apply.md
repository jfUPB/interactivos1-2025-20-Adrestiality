# Unidad 2

## 🛠 Fase: Apply
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 04 ༓☾∘∙•⋅⋅⊰⋅•⋅**

<img width="941" height="871" alt="DIAGRAMA" src="https://github.com/user-attachments/assets/2920797c-9a5e-48b8-b5c5-0f8e9166fe31" />

> He de admitir que no me gusta mucho hacer diagramas para máquinas de estado ANTES de hacer los códigos, ya que siempre acabo haciendo códigos más extensos o cortos que lo planeado por el programa. Es por eso por la cual este diagrama ya incluye los fragmentos de código. Habían muchos if que no estoy segura si están bien puestos en esas casillitas azules, pero esperemos que si

## **ACTIVIDAD 05 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```py
from microbit import *
import utime

STATE_INIT=0
STATE_CONF=1
STATE_ARMED=2
STATE_EXPLODED=3

CONF_INTERVAL=1000

current_state = STATE_INIT
time_setting =20
start_time=0
interval = 0

while True:
    current_time = utime.ticks_ms()
    
    if current_state == STATE_INIT:
        display.show(Image.PACMAN)
        start_time = utime.ticks_ms()
        interval = CONF_INTERVAL
        current_state = STATE_CONF

    elif current_state == STATE_CONF:
        display.scroll(str(time_setting))
        
        if button_a.was_pressed():
            time_setting += 1
            
        if button_b.was_pressed():
            time_setting -= 1
            
        if accelerometer.was_gesture("shake"):
            countdown = time_setting
            start_time = utime.ticks_ms()
            current_state= STATE_ARMED

            
    elif current_state == STATE_ARMED:
        elapsed = utime.ticks_diff(current_time,start_time)
        remaining = countdown - elapsed // 1000
        
        if elapsed >= 0:
            display.scroll(str(remaining))
        else:
            display.show(Image.SKULL)
            current_state = STATE_EXPLODED

    elif current_state == STATE_EXPLODED:
        if pin_logo.is_touched():
            time_setting = 20
            current_state = STATE_CONF
```
-    [STATE INIT]
En este estado no hya eventos, es el estado base. Como me inspiré del código de la actividad anterior puse que se mostrara un pacman por un intervalo de 1 segundo (1000 milisegundos). Peerooo da la sorpresa que no tengo la más minima idea de por que no aparece. Va derechito a mostrar los números...
Creo que si quito el STATE INIT el código va a seguir igual. pero no quise intentarlo.
Espero me valgan la intencion de poner un Pacman. Capaz si alguien lee esto en un futuro, sería un easter egg ¿no?
En fin, de STATE INIT, pasa a STATE CONF

-    [STATE CONF]
En este estado es donde vemos por primera vez el contador en su valor inicial que es 20, al presionar a el valor se le sumara 1 o si presionas b le restara 1. Finalmente si sacudes la microbit se activara la bomba y pasará al siguiente estado, el STATE ARMED

-    [STATE ARMED]
Aquí sucede la cuenta regresiva. El programa esta constantemente verificando por medio de restas con los numeros del tiempo actual, que el valor sea diferente de 0 para que siga retrocediendo. Y cuando llega a 0, PUUMM aparece una calavera y pasa el siguiente estado, el STATE EXPLODED

-    [STATE EXPLODED]
Aquí la bomba ya explotó, por lo que solamente reestablece el tiempo y y espera a que el pin de la microbit se presione. Una vez se active te manda de vuelta a STATE CONF y vuelves a acceder a la onfiguración del tiempo
