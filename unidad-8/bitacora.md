
# Evidencias de la unidad 8
## 🦑 ACTIVIDAD 1

- 🦐 **Documenta los referentes visuales que te inspiren**
>
> Mi idea siem pre fue la siguiente. como no estoy completamente segura de como hacer una actividad que siem pre tuviera al usuario concentrado, entonces mas bien pense... por que el usuario no crea mas bien sus propias visuales??
>
> Asi que mi inspiracion base fue esta actividad de generative desing:
>
> <img width="1780" height="740" alt="image" src="https://github.com/user-attachments/assets/89e723b6-cfd5-4b2c-9ab4-4481e053b6de" />

- 🦐 **Define el concepto de las visuales que quieres crear**
>
> Mis visuales se definen como ondas que se modifican y desplazan respecto los altos, bajos y medios de una cancion. generando asi un producto visual que cambia constantemente... tus lineas nunca seran iguales desde que las trazas y van a ser aun mas unicas ya que las ondas distorcionan tus trazos cada vez mas

- 🦐 **Explica cómo el móvil y el micro:bit controlarán las visuales**
>
> Lo que tenia en mente era que en el fondo hubieran ondas con el ritmo de la cancion
>
> Desde el celular podias trazar lienas que se distorsionaban tambien respecto al audio
>
> Finalmente, queria que el microbit me permitiera cambiar el angulo de las ondas del fondo

- 🦐 **Haz un bocetos de todas las interfaces del sistema**
>
> Muy genuinamnete este fue un dibujo que hice en clase en paint para indicarle a la IA lo que quería hacer
>
><a name="evidencia1"></a>
> <img width="810" height="505" alt="image" src="https://github.com/user-attachments/assets/08ba80e3-1896-4310-bf33-a0d18ffb5285" />


- 🦐 **Haz un diagrama que explique cómo se comunicarán los diferentes componentes del sistema**
>
> <img width="730" height="803" alt="image" src="https://github.com/user-attachments/assets/2952e704-df41-467c-8d88-e13da161c4fe" />


## 🦑 ACTIVIDAD 2

- 🦐 **Documenta todo el proceso de construcción**
>
> La verdad no fue muy dificil el incluir el microbit en algo aqui, por lo que basto generar un simple codigo con una ia
>
> Y sorprendentemente, con solo la primeraq vez funciono

- 🦐 **Incluye todos los códigos: servidor, cliente móvil, cliente de escritorio y micro:bit**

MICROBIT----------------------------------
```
from microbit import *
uart.init(115200)
display.set_pixel(0,0,9)

while True:
    xValue = accelerometer.get_x()
    yValue = accelerometer.get_y()
    data = "{},{}\n".format(xValue, yValue)
    uart.write(data)
    sleep(50)
```

SERVER.JS---------------------------------
```
const express = require('express');
const http = require('http');
const socketIO = require('socket.io');

const app = express();
const server = http.createServer(app); 
const io = socketIO(server); 
const port = 3000;

app.use(express.static('public'));

io.on('connection', (socket) => {
    console.log('New client connected');
    socket.on('message', (message) => {
        console.log('Received message =>', message);
        socket.broadcast.emit('message', message);
    });

    
    socket.on('mobileData', (data) => {
    io.emit('desktopData', data);
  });


    socket.on('disconnect', () => {
        console.log('Client disconnected');
    });
});

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
});
```

DESKTOP------------------------------------

-  SKETCH.JS
```
let song, fft;
let bassLevel = 0, midLevel = 0, trebleLevel = 0;
let trails = []; 
let socket;
let started = false;
let bassColor, midColor, trebleColor;

// Variables para micro:bit
let port;
let reader;
let waveRotation = 0;
let targetRotation = 0;

function preload() {
  song = loadSound('Alfonso Peduto - Binary Data IV [OFFICIAL AUDIO].mp3');
}

function setup() {
  createCanvas(windowWidth, windowHeight);
  background(0);
  textAlign(CENTER, CENTER);
  textSize(32);
  fill(255);
  text("Haz clic para comenzar", width / 2, height / 2);
  
  socket = io();
  fft = new p5.FFT();
  
  bassColor = color(255, 180, 200);
  midColor = color(200, 180, 255);
  trebleColor = color(180, 220, 255);
  
  socket.on('desktopData', (data) => {
    trails.push({
      points: data.path,
      t: millis()
    });
  });
  
  // Botón para conectar micro:bit
  let connectBtn = createButton('Conectar micro:bit');
  connectBtn.position(20, 20);
  connectBtn.mousePressed(connectMicrobit);
}

async function connectMicrobit() {
  try {
    port = await navigator.serial.requestPort();
    await port.open({ baudRate: 115200 });
    
    const textDecoder = new TextDecoderStream();
    const readableStreamClosed = port.readable.pipeTo(textDecoder.writable);
    reader = textDecoder.readable.getReader();
    
    readMicrobitData();
    console.log("Micro:bit conectado");
  } catch (error) {
    console.error("Error conectando micro:bit:", error);
  }
}

async function readMicrobitData() {
  try {
    let buffer = '';
    while (true) {
      const { value, done } = await reader.read();
      if (done) break;
      
      buffer += value;
      let lines = buffer.split('\n');
      buffer = lines.pop();
      
      for (let line of lines) {
        let values = line.trim().split(',');
        if (values.length >= 2) {
          let x = parseInt(values[0]);
          targetRotation = map(x, -1024, 1024, -PI/4, PI/4);
        }
      }
    }
  } catch (error) {
    console.error("Error leyendo micro:bit:", error);
  }
}

function draw() {
  if (!started) return;
  
  background(0, 40);
  
  // Suavizar rotación
  waveRotation = lerp(waveRotation, targetRotation, 0.1);
  
  fft.analyze();
  bassLevel = fft.getEnergy("bass") * 2.2;
  midLevel = fft.getEnergy("mid") * 2.0;
  trebleLevel = fft.getEnergy("treble") * 2.5;
  
  // Dibujar ondas CON rotación
  push();
  translate(width / 2, height / 2);
  rotate(waveRotation);
  translate(-width / 2, -height / 2);
  
  drawWave(bassLevel, bassColor, 0.25);
  drawWave(midLevel, midColor, 0.15);
  drawWave(trebleLevel, trebleColor, 0.05);
  
  pop();
  
  // Dibujar trazos del móvil SIN rotación
  for (let i = trails.length - 1; i >= 0; i--) {
    let tr = trails[i];
    let age = millis() - tr.t;
    let alpha = map(age, 0, 2500, 255, 0);
    if (alpha <= 0) {
      trails.splice(i, 1);
      continue;
    }
    strokeWeight(3);
    stroke(lerpColor(bassColor, trebleColor, noise(age * 0.001)), alpha);
    noFill();
    beginShape();
    for (let p of tr.points) {
      let x = p.x * width;
      let y = p.y * height;
      let waveOffset = sin(frameCount * 0.03 + x * 0.02) * (bassLevel * 0.5);
      vertex(x, y + waveOffset);
    }
    endShape();
  }
}

function mousePressed() {
  if (!started) {
    started = true;
    userStartAudio();
    song.loop();
  }
}

function drawWave(level, col, scale) {
  stroke(col);
  strokeWeight(2);
  noFill();
  beginShape();
  for (let x = 0; x < width; x += 10) {
    let wave = sin(x * 0.02 + frameCount * 0.05) * (level * scale);
    vertex(x, height / 2 + wave);
  }
  endShape();
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}
```

- INDEX.HTML
```
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <title>Binary Data IV Visual</title>

    <!-- Librerías necesarias -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.9.0/p5.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.9.0/addons/p5.sound.min.js"></script>
    <script src="/socket.io/socket.io.js"></script>

    <!-- Tu sketch -->
    <script src="sketch.js"></script>

    <style>
      body {
        margin: 0;
        overflow: hidden;
        background-color: black;
      }
    </style>
  </head>
  <body>
  </body>
</html>
```

MOBILE------------------------------------

-  SKETCH.JS
```
let socket;
let drawingPath = [];
let isDrawing = false;

function setup() {
  createCanvas(windowWidth, windowHeight);
  background(20);
  socket = io();
}

function draw() {
  background(20, 30);
  stroke(255);
  noFill();

  beginShape();
  for (let p of drawingPath) {
    vertex(p.x * width, p.y * height);
  }
  endShape();
}

function touchStarted() {
  isDrawing = true;
  drawingPath = [];
  return false;
}

function touchMoved() {
  if (isDrawing) {
    let x = constrain(mouseX / width, 0, 1);
    let y = constrain(mouseY / height, 0, 1);
    drawingPath.push({ x, y });
  }
  return false;
}

function touchEnded() {
  isDrawing = false;
  // Enviar la trayectoria al servidor
  socket.emit('mobileData', { path: drawingPath });
  drawingPath = [];
  return false;
}
```

- INDEX.HTML
```
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Actividad 5 - Mobile</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
      html, body {
        margin: 0;
        padding: 0;
        overflow: hidden;
        background-color: #111;
      }
      canvas {
        display: block;
      }
    </style>
  </head>

  <body>
    <!-- Librerías necesarias -->
    <script src="/socket.io/socket.io.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.9.0/p5.min.js"></script>

    <!-- Tu sketch -->
    <script src="sketch.js"></script>
  </body>
</html>
```
IMÁGENES
><a name="evidencia2"></a>
> <img width="1901" height="940" alt="Captura de pantalla 2025-10-29 170259" src="https://github.com/user-attachments/assets/756363fc-532e-4b9b-a40f-24b88a7ba8a5" />
> <img width="1886" height="900" alt="Captura de pantalla 2025-10-29 170229" src="https://github.com/user-attachments/assets/dad2dfe6-b8a9-4ca4-ab95-e24f7bc7809d" />

## 🦑 AUTOEVALUACIÓN

- 🦐 **NOTA PROPUESTA: 5.0**

- 🦐 **DEFENSA**

- ACTIVIDAD 1

El estudiante diseña nuevas funcionalidades en su actividad interactiva para incluir el microbit
[evidencia actividad 1](#evidencia1)

- ACTIVIDAD 2

El estudiante adapta el codigo de la actividad interactiva anterior para incluir el uso del microbit
[evidencia actividad 2](#evidencia2)

