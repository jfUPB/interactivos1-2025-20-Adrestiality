# Unidad 1

## 🛠 Fase: Apply


─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 05 ༓☾∘∙•⋅⋅⊰⋅•⋅**
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
####¿Notaste que la aplicación no funcionó? 

####¿Qué crees que podría estar mal?

#### Explica cómo funciona el sistema físico interactivo que acabamos de crear

### **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**}

https://editor.p5js.org/Adrestiality/sketches/fDEQm0OMm
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
Escribe el enlace a tu programa en el editor de p5.js.
Copia el código de tu programa en la bitácora (recuerda insertarlo usando markdown y el lenguaje javascript).
Copia el código del micro:bit en la bitácora (recuerda insertarlo usando markdown y el lenguaje python).
