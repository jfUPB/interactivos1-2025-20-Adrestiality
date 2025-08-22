# Unidad 3

## 🛠 Fase: Apply
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 06 | 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

https://editor.p5js.org/Adrestiality/sketches/BUTd2qeh9

```javascript
let bombTask;
let serialTask;
let event;
let port;
let connectBtn;

function setup(){
  createCanvas(400,400);
  textAlign(CENTER,CENTER);
  textSize(32);

  // Puerto serial
  port = createSerial();
  connectBtn = createButton('Connect To Microbit');
  connectBtn.position(130,300);
  connectBtn.mousePressed(connectBtnClick);

  event = new BombEvent();
  bombTask = new BombTask();
  serialTask = new SerialTask();
}

function draw(){
  background(0);

  // Actualizar tareas
  serialTask.update();
  bombTask.update();

  // Dibujar bomba
  bombTask.display();
}


class BombEvent {
  constructor(){
    this.value = null;
  }
  set(val){ this.value = val; }
  clear(){ this.value = null; }
  read(){ return this.value; }
}


class SerialTask {
  update(){
    if(port.availableBytes() > 0){
      let dataRx = port.read(1);
      if(dataRx === 'A') event.set('A');
      else if(dataRx === 'B') event.set('B');
      else if(dataRx === 'S') event.set('S');
      else if(dataRx === 'T') event.set('T');
    }

    // Actualizar texto del botón según estado del puerto
    if (!port.opened()) connectBtn.html('Connect to micro:bit');
    else connectBtn.html('Disconnect');
  }
}


class BombTask {
  constructor(){
    this.PASSWORD = ['A','B','A'];
    this.key = [];
    this.count = 20;
    this.startTime = millis();
    this.state = 'CONFIG';
  }

  update(){
    if(this.state === 'CONFIG'){
      if(event.read() === 'A'){
        event.clear();
        this.count = min(this.count + 1, 60);
      }
      else if(event.read() === 'B'){
        event.clear();
        this.count = max(this.count - 1, 10);
      }
      else if(event.read() === 'S'){
        event.clear();
        this.startTime = millis();
        this.state = 'ARMED';
      }
    }

    else if(this.state === 'ARMED'){
      if(millis() - this.startTime > 1000){
        this.count--;
        this.startTime = millis();
        if(this.count <= 0){
          this.state = 'EXPLODED';
        }
      }

      if(event.read() === 'A' || event.read() === 'B'){
        this.key.push(event.read());
        event.clear();
        if(this.key.length === this.PASSWORD.length){
          if(this.key.join('') === this.PASSWORD.join('')){
            this.state = 'CONFIG';
            this.count = 20;
          }
          this.key = [];
        }
      }
    }

    else if(this.state === 'EXPLODED'){
      if(event.read() === 'T'){
        event.clear();
        this.state = 'CONFIG';
        this.count = 20;
        this.startTime = millis();
      }
    }
  }

  display(){
    fill(255);
    if(this.state === 'CONFIG'){
      text(`CONFIG\n${this.count} `, width/2, height/2);
    }
    else if(this.state === 'ARMED'){
      text(`ARMED\n${this.count} `, width/2, height/2);
    }
    else if(this.state === 'EXPLODED'){
      fill(255,0,0);
      text("EXPLODED", width/2, height/2);
    }
  }
}

function connectBtnClick(){
  if(!port.opened()){
    port.open('MicroPython',115200);
  } else {
    port.close();
  }
}

function keyPressed() {
  if (key === 'A') event.set('A');
  else if (key === 'B') event.set('B');
  else if (key === 'S') event.set('S');
  else if (key === 'T') event.set('T');
}
```
```py
# Imports go at the top
from microbit import *

uart.init(baudrate=115200)
display.show(Image.HAPPY)

while True:
    display.show(Image.HAPPY)
    if button_a.was_pressed():
        uart.write('A')
        display.show(Image.ARROW_N)
        sleep(200)
    if button_b.was_pressed():
        uart.write('B')
        display.show(Image.ARROW_S)
        sleep(200)
    if accelerometer.was_gesture('shake'):
        uart.write('S')
        display.show(Image.SAD)
        sleep(200)
    if pin_logo.is_touched():
        uart.write('T')
        display.show(Image.HAPPY)
        sleep(200)
```
