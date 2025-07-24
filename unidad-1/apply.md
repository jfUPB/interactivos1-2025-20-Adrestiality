# Unidad 1

## 🛠 Fase: Apply


─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 05 ༓☾∘∙•⋅⋅⊰⋅•⋅**
//CÓDIGO MICROBIT//
```
from microbit import *

uart.init(baudrate=115200)

while True:

    if button_a.is_pressed():
        uart.write('A')
    else:
        uart.write('N')

    sleep(100)
```
//CÓDIGO P5SJ//
```
  let port;
  let connectBtn;
  let connectionInitialized = false;

  function setup() {
    createCanvas(400, 400);
    background(220);
    port = createSerial();
    connectBtn = createButton("Connect to micro:bit");
    connectBtn.position(80, 300);
    connectBtn.mousePressed(connectBtnClick);
  }

  function draw() {
    background(220);

    if (port.opened() && !connectionInitialized) {
      port.clear();
      connectionInitialized = true;
    }

    if (port.availableBytes() > 0) {
      let dataRx = port.read(1);
      if (dataRx == "A") {
        fill("red");
      } else if (dataRx == "N") {
        fill("green");
      }
    }

    rectMode(CENTER);
    rect(width / 2, height / 2, 50, 50);

    if (!port.opened()) {
      connectBtn.html("Connect to micro:bit");
    } else {
      connectBtn.html("Disconnect");
    }
  }

  function connectBtnClick() {
    if (!port.opened()) {
      port.open("MicroPython", 115200);
      connectionInitialized = false;
    } else {
      port.close();
    }
  }
```
-    #### ¿Notaste que la aplicación no funcionó? 
Realmente la aplicación si funciona, pero quizás no como esperábamos... Se debe a que una vez copiamos todos los codigos el boton que activa el cuadro rojo aparece por milisegundos, independientemente si dejabamos presionado el boton o no

-    #### ¿Qué crees que podría estar mal?
En cierto fragmento del código original del microbit teniamos "button_a.is_pressed()", lo cual detecta que el boton esta siendo presionado ahora mismo. El cambio realizado fue de "is" a "was", el cual detecta que el botón fue presionado desde la última vez que se llamó su función

-    #### Explica cómo funciona el sistema físico interactivo que acabamos de crear
Recordemos que debemos manejar dos programas diferentes. 
Una que programa a la microbit (micro:bit)y otro que se comunica con la microbit a modo de controlador(P5sj) 

Por el lado de micro:bit tenemos un código que interpreta los botones que se presionan con letras en mayúsculas.

Por el lado del P5sj tenemos otro código que crea botones para conectar la microbit (adicionalmente le incorporamos una libreria que le permite crear las opciones necesarias para vincularse con la microbit), interpreta su conección y dependiendo de dichas letras mayúsculas que le llegan, hace funciones diferentes... en este caso, se tiene un rectángulo hecho, y dependiendo de la letra presionada el rectangulo es rojo o verde.

### **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**}
-    [Enlace a P5js](https://editor.p5js.org/Adrestiality/sketches/fDEQm0OMm)

//CÓDIGO MICROBIT//
```
from microbit import *

uart.init(baudrate=115200)
display.show(Image.BUTTERFLY)

while True:

    if button_a.was_pressed():
        uart.write('A') 
    if button_b.was_pressed():
        uart.write('N')
 
    sleep(100)
```
//CÓDIGO P5SJ//
```
let port;
let connectBtn;
let connectionInitialized = false;
let x = 200;

function setup() {
  createCanvas(400, 400);
  background(220);
  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(130, 300);
  connectBtn.mousePressed(connectBtnClick);
}

function draw() {
  background(220);

  if (port.opened() && !connectionInitialized) {
    port.clear();
    connectionInitialized = true;
  }

  if (port.availableBytes() > 0) {
    let dataRx = port.read(1);
    if (dataRx == "A") {
      x = x - 20;
      print("A");

    } else if (dataRx == "N") {
      x = x + 20;
    }
  }

  //print(x);
  circle(x, height / 2, 150);

  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
  } else {
    connectBtn.html("Disconnect");
    connectBtn.position(130, 300);
  }
}

function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);
    connectionInitialized = false;
  } else {
    port.close();
  }
}
```
