
# Evidencias de la unidad 7 

## 🐙**ACTIVIDAD 01**

- 🦀 **¿Qué URL de Dev Tunnels obtuviste? ¿Por qué crees que necesitamos usar esta URL en lugar de http://localhost:3000 o la IP local de tu computador para que el celular se conecte?**
>
> En mi caso, obtuve "https://6k3bhnfz-3000.use2.devtunnels.ms/", y para celulares era "https://6k3bhnfz-3000.use2.devtunnels.ms/mobile/"
>
> Necesitamos Crear un servidor propio mas alla de las limitaciones del dispositivo que nos permita concetar varios dispositivos a la vez

- 🦀 **Describe brevemente qué hace npm install y npm start.**
>
> El npm instal, se encarga de descargar e instalar en el programa las dependencias y bibliotecas para que funcione correctamente; mientras que el npm start se encarga de iniciar y darle vida al servidor


- 🦀 **¿Qué mensajes observaste en la terminal del servidor al conectar el cliente de escritorio y el cliente móvil? ¿Eran diferentes los mensajes o identificadores?**

<a name="evidencia1"></a>
```
Server is listening on http://localhost:3000
New client connected
New client connected
Received message => { type: 'touch', x: 210.19798278808594, y: 243.05540466308594 }
Received message => { type: 'touch', x: 195.4116668701172, y: 202.67222595214844 }
Received message => { type: 'touch', x: 194.2127685546875, y: 195.4752197265625 }
```
> Los mensaje que me proporciona la terminal son similares a los que tenia en la unidad pasada con las ventanas y los circulos. Nos dice que los clientes estan conectados y que todo funciona bien, no obstante se diferencian en que las coordenadas que vemos no son posiciones de ventana, sino las coordenadas de la ubicacion nueva de la bolita a medida que la movemos con el touch

- 🦀 **Describe el comportamiento observado: ¿Funcionó la interacción? ¿Hubo algún retraso (latencia)?**
>
> La interacción fue exitosa. En el celular teniamos un recuadro gris que nos pedia que deslizaramos el dedo en el y al hacerlo la bolita en el comptador se movia de manera correspondiente. Genuinamente no soy muy conciente de muchas latencia que digamos, simplmente se demoraba un poquitito en recibir nuevamente coordenadas recien abierto el servidor o cuando quitaba mi dedo un rato y lo volvia a poner para deslizar

## 🐙**ACTIVIDAD 02**

- 🦀 **Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?**
>
> Como la propia palabra lo dice, es una especie de tunel, punte o ""mensajero"" que se encarga de pasar la informacion de manera segura desde un cliente A a un cliente B. Es necesario gracias a la seguridad que proporciona, ya que estamos generando un servidor en la interperie de la red, por lo que Dev Tunnels es nuestro tunel seguro para pasar y extraer informacion  de los clientes

- 🦀 **Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.**
>
> TOUCHMOVED: Es la función que se encarga de recibir las coordenadas de cada movimieno nuevo que se genera. Podria decirse que es la funcion más importante de todo el programa con respecto a la interactividad
>
> THRESHOLD: Es la funion que limita las coordenadas del TouchMoved. Es decir, es la que se encarga de establecer ciertos rangos de valores o limites que le permiten identificar a touchMoved cuando las nuevas coordenadas son muy similares y significan un simle tambaleo del usuario y cuando definitivamente la nueva coordenada implica un nuevo movimiento relevante a mostrar

- 🦀 **Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?**
>
> Usar una conección con la Ip local de los dispositivos tiene la gran limitación de estar conectados obligatoriamente a la misma red, por lo que usar datos ni siquiera es opcion aqui. Mientras que dev tunnels establece una conección entre los clientes en medio de la interperie del internet pero de manera segura bajo la condicion de ambos dispositivos esten conectados a internet

>- 🦀 **Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).**
>
> ![Imagen de WhatsApp 2025-10-09 a las 17 35 06_92d4ac39](https://github.com/user-attachments/assets/89bce61f-f9cf-4190-b2b9-bc38ab0a73f8)
<a name="evidencia2"></a>
> <img width="1331" height="535" alt="image" src="https://github.com/user-attachments/assets/18401f1c-1a0e-41bb-8497-5d992fc9d583" />
> <img width="404" height="551" alt="image" src="https://github.com/user-attachments/assets/eb2684a0-996e-4c6b-be20-7be5a34058b0" />

## 🐙**ACTIVIDAD 03**

- 🦀 **¿Cuál es la función principal de express.static(‘public’) en este servidor? ¿Cómo se compara con el uso de app.get(‘/ruta’, …) del servidor de la Unidad 6?**
> 
> App.get es la funcion que en la unidad anterior nos proporcionaba una ruta especifica para que los clientes se cconectaran y tuviesen sus propior archivos estáticos, mientras que express.static nos proporciona todo en un solo lugar. Si ingresamos el github que clonamos inicialmente, encontraremos la carpeta public la cual esta llamada en la funcion

- 🦀 **Explica detalladamente el flujo de un mensaje táctil: ¿Qué evento lo envía desde el móvil? ¿Qué evento lo recibe el servidor? ¿Qué hace el servidor con él? ¿Qué evento lo envía el servidor al escritorio? ¿Por qué se usa socket.broadcast.emit en lugar de io.emit o socket.emit en este caso?**
> 
> EVENTO QUE ENVIA DESDE EL MOVIL: TouchMoved
>
> EVENTO QUE LO RECIVE EN EL SERVIDOR: socket.on
>
> QUE HACE EL SERVIDOR CON EL: socket.broadcast
>
> Se debe usar socket.broadcast ya que es lo que nos permite una conexión continua con los datos, es como una conección en vivo. Si la cambiamos, los clientes ni siquiera sabrian que se desconectaron, por lo que seguirian funcionando

- 🦀 **Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ¿Quién recibiría el mensaje retransmitido por el servidor? ¿Por qué?**
>
<a name="evidencia3"></a>
> Originalmente pense en que si yo abria otropc son el enlace que tenía el dispositivo con el servidor (es decir, el enlace sin /mobile/) podria acceder, al menos visualmente, a las cosas que el dispositivo con el servidor podia tener.
>
> Pero oh sorpresa, cuando pegue el enlace salía un ERROR y la pantalla en balnco... Por lo que solo dejaba dos opciones (en realidad una) Instala todas las cosas necesarias para tambien abrir el servidor desde este segundo pc o cambiar el enlace añadiendo la extensión mobile
> La primera opcion no era posible, pues no es posible "crear y acceder" a un servidor, es decir, no puedo crear dos servidores iguales y acceder a la informacio de sus clientes. Por lo que me fui por la segunda opcion del enlace con la extención y WOOOW, tenia la interfaz y opciones del celular en el pc. podia mover la bolita desde ambos lugares casi que a la vez
>
>Pero y entonces, en donde se reflejan los movimientos de la bolita? UNICAMENTE en el dispositivo que tiene el servidor abierto, en este caso, el primer pc...

- 🦀 **¿Qué información útil te proporcionan los mensajes console.log en el servidor durante la ejecución?**
>
> El console.log nos proporciona informacion muy util, como los clientes y su estado (conectados y desconectados) y los mensajes que se estan pasando entre ellos, en este caso, las actualizaciones tipo touch que se etan enviando

## 🐙**ACTIVIDAD 04**

- 🦀 **Realiza un diagrama donde muestres el flujo completo de datos y eventos entre los tres componentes: móvil, servidor y escritorio. Puedes ilustrar con un ejemplo de coordenadas táctiles (x, y) y cómo viajan a través del sistema.**
>
<a name="evidencia4"></a>
> <img width="867" height="808" alt="000" src="https://github.com/user-attachments/assets/a91d9f89-26d7-43d8-890c-442455504183" />


## 🐙**ACTIVIDAD 05**

- 🦀 **Diseño actividad interactiva**
>
>  La verdad reconozco que diseñar esta actividad tuvo su complique... 
>
>Inicialmente estaba trabajando con una compañera, pensábamos hacer el apply juntas, pero al parecer nuestras propuestas no eran las más altas para lo esperado además de que olvidamos un factor importante que era   añadir dos clientes diferentes. Siendo este último el motivo por el cual eventualmente tratamos mejor de terminar de manera individual 
>
>Por mi parte, decidí volver a la idea inicial de hacer visuales tipo concierto 
Pero, ¿Como hacía las visuales de un concierto si usualmente tu como espectador no interactuas con ella, solamente las ves? 
>
>A la final llegue a la conclusión de que el propio usuario pudiera crear sus propias visuales, de manera en que su curiosidad por crear sea la que lo mantenga durante toda la canción 
>
>Escogí BINARY DATA IV de Alfonso Peduto, una de mis canciones de piano favoritas (en realidad todos sus 3 álbumes me encantan) porque tienen un toque extraño pero único 
>
>Mi idea inicialmente era: los altos, medios y bajos de la canción se ven como ondas en los dos laterales de la pantalla, dejando el resto de espacio limpio para dibujar, y que tus trazos se movieran también respecto a la música
>
>Eventualmente fracase con el código
>
>De verdad. No fui capaz. De verdad estoy harta de intentar programar y no lograrlo
>
>En parte me siento muy atras cuando mis compañeros logran cosas más increíbles por su cuenta.
>
> Pero bueno, el caso está en que volví con mi relación tóxica
>
>Y después de estar peleando por 3 horas logré algo como lo de las capturas. 
>Las ondas no están en los laterales y no me gusta mucho los trazos que se hacen a la final, pero es lo mejor que pude hacer

- 🦀 **Códigos**

> [!WARNING]
> NOTA: ESTE CÓDIGO FUE GENERADO CON IA.

veamos el código

> DESKTOP:
>
> - index.html
```javascript
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
>
> - sketch.js
```javascript
let song, fft;
let bassLevel = 0, midLevel = 0, trebleLevel = 0;
let trails = []; 
let socket;
let started = false;

let bassColor, midColor, trebleColor;

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
}

function draw() {
  if (!started) return;

  background(0, 40);

  fft.analyze();

  bassLevel = fft.getEnergy("bass") * 2.2 ;
  midLevel = fft.getEnergy("mid") * 2.0 ;
  trebleLevel = fft.getEnergy("treble") * 2.5 ;

  // Dibujar ondas de energía
  drawWave(bassLevel, bassColor, 0.25);
  drawWave(midLevel, midColor, 0.15);
  drawWave(trebleLevel, trebleColor, 0.05);

  // Dibujar trazos del móvil
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
    userStartAudio(); // Reanuda el contexto de audio
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
>
>MOBILE
>
> - index.html
```javascript
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
>
> - sketch.js
```javascript
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
>
> SERVER.JS
```javascript
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
- 🦀 **Capturas**
<a name="evidencia5"></a>
><img width="1874" height="994" alt="Captura de pantalla 2025-10-13 152158" src="https://github.com/user-attachments/assets/5454587f-e609-4923-9e27-c49d61c2dbb0" />
><img width="1863" height="982" alt="Captura de pantalla 2025-10-13 152121" src="https://github.com/user-attachments/assets/10952d3b-50c8-495b-a2f9-407dd70d09a8" />
><img width="1861" height="998" alt="Captura de pantalla 2025-10-13 152109" src="https://github.com/user-attachments/assets/765db4c2-bbc3-438e-a0a0-974ec69a5f59" />
><img width="1850" height="954" alt="Captura de pantalla 2025-10-13 152207" src="https://github.com/user-attachments/assets/4833c2af-4eb8-42bd-bcc7-2798d30501a0" />

## 🐙**AUTOEVALUACIÓN**

- 🪸 **MI NOTA PROPUESTA: 5.0**
- 🪸 **DEFENSA:**
  
ACTIVIDAD 1
> 
> El eswtudiante analiza las principales diferencias entre el servidor de la unidad anterior y la de esta unidad
> 
> [evidencia actividad 1](#evidencia1)

ACTIVIDAD 2
> 
> El estudiante analiza la importancia del dev tunnels como un puente seguro del servidor en medio de la inmensidad del internet que nos permite conectar dispositivos
> 
> [evidencia actividad 2](#evidencia2)

ACTIVIDAD 3
> 
> El estudiante analiza el flujo de mensajes, de mod en que analiza que provoca que reaccion y quien le manda cosas a quien
> 
> [evidencia actividad 3](#evidencia3)

ACTIVIDAD 4
> 
> El estudiante realiza un diagrama evidenciando el flujo de datos entre los tres componentes princiapales
> 
> [evidencia actividad 4](#evidencia4)

ACTIVIDAD 5
> 
> El estudiante diseña una aplicacion interactiva donde crotrola las visuales en base a una canción
> 
> [evidencia actividad 5](#evidencia5)

