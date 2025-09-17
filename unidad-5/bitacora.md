
# Evidencias de la unidad 5

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## 🎀**ACTIVIDAD 01**🎀

-  🎟️ **Describe cómo se están comunicando el micro:bit y el sketch de p5.js. ¿Qué datos envía el micro:bit?**

> El microbit está enviando constantemente una serie de datos por medio de la conección serial, los cuales el p5js usa para ejecución del código. Por ejemplo, si recive un True para el botón A, es porque está presionado en la microbit.

-  🐦 **¿Cómo es la estructura del protocolo ASCII usado?**

> La estructura está en hexadecimal, compuestas por numeros y letras.

-  🧣**Muestra y explica la parte del código de p5.js donde lee los datos del micro:bit y los transforma en coordenadas de la pantalla.**

``` java script
if (port.availableBytes() > 0) {
      let data = port.readUntil("\n");
      if (data) {
        data = data.trim();
        let values = data.split(",");
        if (values.length == 4) {
          microBitX = int(values[0]) + windowWidth / 2;
          microBitY = int(values[1]) + windowHeight / 2;
          microBitAState = values[2].toLowerCase() === "true";
          microBitBState = values[3].toLowerCase() === "true";
          updateButtonStates(microBitAState, microBitBState);
        } else {
          print("No se están recibiendo 4 datos del micro:bit");
        }
```
> Aquí el codigo lo que le pide a p5js es que lea las lineas de código hasta un /n, que es el salto de línea. Lo cual le permite identificar línea por línea la información que le llega

> Luego; si la cantidad de valores es equivalente a 4 (que en teoría sería un valor para la posición en x del microbit, otra para la posición en y, otro para el botón A y finalmente otro para el botón B) Le decimos que las variables 1 y 2, serán microBitX y microBitY que despues usamos como coordenadas. Finalmnete, asignamos los valores 1 y 2 como microBitAState, microBitBState, y que se estén actualizando cada rato

-  ☎️ **¿Cómo se generan los eventos A pressed y B released que se generan en p5.js a partir de los datos que envía el micro:bit?**

``` java script
function updateButtonStates(newAState, newBState) {
  // Generar eventos de keypressed
  if (newAState === true && prevmicroBitAState === false) {
    // create a new random color and line length
    lineModuleSize = random(50, 160);
    // remember click position
    clickPosX = microBitX;
    clickPosY = microBitY;
    print("A pressed");
  }
  // Generar eventos de key released
  if (newBState === false && prevmicroBitBState === true) {
    c = color(random(255), random(255), random(255), random(80, 100));
    print("B released");
  }
```
> En el código anterior definimos que ciertos valores true (los de los botones en caso de estar presionados) se nombraron como microBitAState, microBitBState. 

- 🍟 **Capturas de pantalla de los algunos dibujos que hayas hecho con el sketch.**
>
>Genuinamente estaba tratando de hacer esos arboltos pomposos de la película el Lorax, pero no me quedaron jajaja
<img width="826" height="805" alt="no se" src="https://github.com/user-attachments/assets/d4dfbf25-23a3-401e-b2c5-72fd73f88e32" />

## 🎃**ACTIVIDAD 02**🎃

- 🦐 **¿Por qué se ve este resultado?**
>
> <img width="991" height="435" alt="image" src="https://github.com/user-attachments/assets/172a31d2-c792-40c6-a7c0-783d2c5e91bb" />
> Se debe principalmnete al cambio de código que hicimos, ya que decidimos pasar de las líneas ASCII a líneas en binario gracias al struct que permite la entrada de datos en formato BigEndian. Los datos entran como 2h2B, siendo 2h dos valores enteros de dos bytes (X,Y) y siendo 2B dos valores enteros sin signo de un byte (Botones A y B)

- 🦧 ** Lo que ves ¿Cómo está relacionado con esta línea de código? **
>
> <img width="1009" height="253" alt="image" src="https://github.com/user-attachments/assets/93c1026a-49be-4b79-8b87-c26e0c4a33cf" />
> Igualmente, por el cambio de codigo, la traduccion en ASCII tambíen cambió. La traducción de cada valor es más corta, ya no son tantas letras y numeros como antes... aquneu sin duda es mejor que ver rombos y signos de interrogación como en la catura antrior

- 🐦‍🔥 **¿Qué ventajas y desventajas ves en usar un formato binario en lugar de texto en ASCII?**
>
> definitivamente el tema de la lectura. En texto era muchisimo mas facil leer los datos con ASCII ya que nos daba las coordenadas de la posición de la microbit y si los botones estaban en true o false. En la version hexadecimal del ASCII si era muy engorroso de leer porque ni espacios habian.... pero en binario ni lo uno ni lo otro... el unico medianamente digerible es el hexadecimal

- 🔥 **¿Cuántos bytes se están enviando por mensaje? ¿Cómo se relaciona esto con el formato '>2h2B'? ¿Qué significa cada uno de los bytes que se envían?**
>
> <img width="1012" height="247" alt="image" src="https://github.com/user-attachments/assets/5cf25436-9346-4820-9b06-26678e05881b" />
> <img width="1018" height="240" alt="image" src="https://github.com/user-attachments/assets/cc7950d8-b0cf-4385-90bf-9b1d293b763c" />
> Parece que se estan enviando unos 6 bytes por mensaje y cada mensaje se envia por cada "shake" que le hacemos a la microbit. En otras palabras, aqui se evidencia que se cumple muy estrictamente el formato 2h2B. Supongo que el orden de los bytes debe ser los 4 primeros bytes deben de corresponder a las posiciones en X y Y, mientras que los otros 2 bytws deben ser el verdadero o falso de los botones A y b

- 🏀 **¿Cómo se verían esos números en el formato '>2h2B'?**
>
> <img width="1008" height="247" alt="image" src="https://github.com/user-attachments/assets/1de0a343-8e91-4d7f-91c4-a1382f14ecf3" />
>
> ``` python
> xValue =  20
> yValue =  30
> ```
> 
> ``` python
> xValue = - 20
> yValue = - 30
> ```
>
> Al parecer, en formato binario y en modo texto, los numeros positivos se ven separaditos de a dos en dos. Los negativos se ven pegaditos de a cuatro. Para lograrlo decidi cambiar el codigo de la microbit, primero en donde iban los valores de X y Y, los cambie por valores positivos y luego negativos para compararlos más facil

- 🏵️ **¿Qué diferencias ves entre los datos en ASCII y en binario? ¿Qué ventajas y desventajas ves en usar un formato binario en lugar de texto en ASCII? ¿Qué ventajas y desventajas ves en usar un formato ASCII en lugar de binario?**
> <img width="1028" height="264" alt="image" src="https://github.com/user-attachments/assets/22df635e-5289-462a-8998-00a174f21ead" />
>
> La diferencia principal radica en la cantidad de bytes, la facilidad de lectura y lo universal que es el modo de pasar los datos, ya que me parece haber leido en algun lado mientras consultaba cosas sobre los datos binarios leer que pasardatos en este formato no es tan universal, al menos no tanto como el ASCII.
> 
> Las ventajas del binario sobre el ASCII es la cantidad de bytes, pues aquí se mandan más limpios y comptactos, pero su mayor desventaja es que no todos los caracteres se traducen al texto, pues la gran mayoria de paginas esperan un lenguaje ASCII para traducir
> 
> Las ventajas del ASCII sobre el binario sin duda es su universalidad y su facilidad para leer y comprender. Existen muchos traductores de ASCII lo cual optimiza su comprension a la hora de leerlo, pero su mayor desventaja es el peso de los bytes. Son más caracteres, son mas numeros y letras, es más texto menos compacto si no lo traduces, por lo que una persona promedio que aun no identifique algunas cosas de ASCII dependerá siempre de un traductor

## 🐳**ACTIVIDAD 03**🐳 
🐬🐋🐟🐠🧶🧵🩲👗👖💎🧿🩹📪🧊⛴️

- 🥏**Explica por qué en la unidad anterior teníamos que enviar la información delimitada y además marcada con un salto de línea y ahora no es necesario.**
>
> Para ello, veamos esto...
> ```
> 1024 = 49 48 50 52 [en ASCII]
> ```
> ```
> 15 = 49 53 [en ASCII]
> ``` 
> ¿Ves que la cantidad de bytes cambia con solo los números?
>
> Veamos este otro
> ```
> true = 116 114 117 101 [en ASCII]
> ```
> ```
> false = 102 97 108 115 101 32 [en ASCII]
> ```
>
> El motivo por el cual se necesitaban los saltos de pagina es porque la cantidad de bytes estaba indefinida y tampoco habia manera de definirla. Entonces para que el programa pueda diferenciar entre una linea de datos y otra, se usa el salto de pagina. Ahora no se necesita, pues literalmente el codigo de la microbit define cuantos bytes tiene cada tipo de dato, y ya que ese limite jamas se sobrepasa, pues el codigo ya relaciona automaticamente la cantidad de bytes con el limite de bytes por linea

- 👘**Compara el código de la unidad anterior relacionado con la recepción de los datos seriales que ves ahora. ¿Qué cambios observas?**
>
> El cambio principal que se nota en dicha sección es la forma en la que p5.js recibe los datos del microbit. En el codigo anterior tenemos funciones que le indican que debe leer cuatro datos, separados por comas hasta el /n. Ahora aqui es diferente. Necesitamos que se lean 6 bytes y se le indican cuantos bytes tiene el tipo de dato que queremos y le asiganmos un nombre de variable. 

- 🎭 **¿Qué ves en la consola? ¿Por qué crees que se produce este error?**
>
> La verdad no tengo la microbit en este momento, pero pienso que se desincronizan los datos que se generan con la microbit, con los que se empaquetan en los bytes. O puede ser una desincronización que se genera donde el codigo no traduce bien y se confunde.


- 🛡️ **Analiza el código, observa los cambios. Ejecuta y luego observa la consola. ¿Qué ves?**
>
> Como dije previamente, en este momento no cuento con mi microbit. Pero puedo deducir que, ahora que el propio codigo se encarga de hacerle una especie de control de calidad a los datos que recibe, ya no tiene un margen de error. Por lo que ya no tiene por que enredar los datos

- 🪢 ** ¿Qué cambios tienen los programas y ¿Qué puedes observar en la consola del editor de p5.js?**
> El cambio principal esta en lo que dije anteriormente, la amnera en que los datos se reciben y una que otra funcion que no esta por ahi

## 🎩**ACTIVIDAD 04**🎩   👾😈🐦‍⬛🐜🕷️👥🗣️👣🎇🎓🎱🔮♠️♟️

- 🐈‍⬛**INTENTO 1**
``` java script
// P_1_2_1_01
//
// Generative Gestaltung – Creative Coding im Web
// ISBN: 978-3-87439-902-9, First Edition, Hermann Schmidt, Mainz, 2018
// Benedikt Groß, Hartmut Bohnacker, Julia Laub, Claudius Lazzeroni
// with contributions by Joey Lee and Niels Poldervaart
// Copyright 2018
//
// http://www.generative-gestaltung.de
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.

/**
 * shows how to interpolate colors in different styles/ color modes
 *
 * MOUSE
 * left click          : new random color set
 * position x          : interpolation resolution
 * position y          : row count
 *
 * KEYS
 * 1-2                 : switch interpolation style
 * s                   : save png
 * c                   : save color palette
 */
"use strict";

var tileCountX = 2;
var tileCountY = 10;
var colorsLeft = [];
var colorsRight = [];
var colors = [];

var interpolateShortest = true;

let c;
let lineModuleSize = 0;
let angle = 0;
let angleSpeed = 1;
const lineModule = [];
let lineModuleIndex = 0;
let clickPosX = 0;
let clickPosY = 0;

let port;
let connectBtn;
let microBitConnected = false;

const STATES = {
  WAIT_MICROBIT_CONNECTION: "WAITMICROBIT_CONNECTION",
  RUNNING: "RUNNING",
};

let appState = STATES.WAIT_MICROBIT_CONNECTION;
let microBitX = 0;
let microBitY = 0;
let microBitAState = false;
let microBitBState = false;
let prevmicroBitAState = false;
let prevmicroBitBState = false;

function setup() {
  createCanvas(800, 800);
  colorMode(HSB);
  noStroke();
  shakeColors();

  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(0, 0);
  connectBtn.mousePressed(connectBtnClick);
}

function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);

  } else {
    port.close();
  }
}

function updateButtonStates(newAState, newBState) {
  // Generar eventos de keypressed
  if (newAState === true && prevmicroBitAState === false) {
    interpolateShortest = true;
    print("A pressed");
  }
  // Generar eventos de key released
  if (newBState === false && prevmicroBitBState === true) {
    interpolateShortest = false;
    print("B pressed");
  }

  prevmicroBitAState = newAState;
  prevmicroBitBState = newBState;
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
}

function readSerialData() {
  // Acumula los bytes recibidos en el buffer
  let available = port.availableBytes();
  if (available > 0) {
    let newData = port.readBytes(available);
    serialBuffer = serialBuffer.concat(newData);
  }

  // Procesa el buffer mientras tenga al menos 8 bytes (tamaño de un paquete)
  while (serialBuffer.length >= 8) {
    // Busca el header (0xAA)
    if (serialBuffer[0] !== 0xaa) {
      serialBuffer.shift(); // Descarta bytes hasta encontrar el header
      continue;
    }

    // Si hay menos de 8 bytes, espera a que llegue el paquete completo
    if (serialBuffer.length < 8) break;

    // Extrae los 8 bytes del paquete
    let packet = serialBuffer.slice(0, 8);
    serialBuffer.splice(0, 8); // Elimina el paquete procesado del buffer

    // Separa datos y checksum
    let dataBytes = packet.slice(1, 7);
    let receivedChecksum = packet[7];
    // Calcula el checksum sumando los datos y aplicando módulo 256
    let computedChecksum = dataBytes.reduce((acc, val) => acc + val, 0) % 256;

    if (computedChecksum !== receivedChecksum) {
      console.log("Checksum error in packet");
      continue; // Descarta el paquete si el checksum no es válido
    }

    // Si el paquete es válido, extrae los valores
    let buffer = new Uint8Array(dataBytes).buffer;
    let view = new DataView(buffer);
    microBitX = view.getInt16(0);
    microBitY = view.getInt16(2);
    microBitAState = view.getUint8(4) === 1;
    microBitBState = view.getUint8(5) === 1;
    updateButtonStates(microBitAState, microBitBState);

    console.log(
      `microBitX: ${microBitX} microBitY: ${microBitY} microBitAState: ${microBitAState} microBitBState: ${microBitBState}`
    );
  }
}

function draw() {
 
  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
    microBitConnected = false;
  } else {
    microBitConnected = true;
    connectBtn.html("Disconnect");
  }
}
    

    tileCountX = int(map(microBitX/10, 0, width, 2, 100));
    tileCountY = int(map(microBitY/10, 0, height, 2, 10));
    var tileWidth = width / tileCountX;
    var tileHeight = height / tileCountY;
    var interCol;
    colors = [];

    for (var gridY = 0; gridY < tileCountY; gridY++) {
      var col1 = colorsLeft[gridY];
      var col2 = colorsRight[gridY];

      for (var gridX = 0; gridX < tileCountX; gridX++) {
        var amount = map(gridX, 0, tileCountX - 1, 0, 1);

        if (interpolateShortest) {
          // switch to rgb
          colorMode(RGB);
          interCol = lerpColor(col1, col2, amount);
          // switch back
          colorMode(HSB);
        } else {
          interCol = lerpColor(col1, col2, amount);
        }

        fill(interCol);

        var posX = tileWidth * gridX;
        var posY = tileHeight * gridY;
        rect(posX, posY, tileWidth, tileHeight);

        // save color for potential ase export
        colors.push(interCol);
        }
      }

function shakeColors() {
  for (var i = 0; i < tileCountY; i++) {
    colorsLeft[i] = color(random(0, 60), random(0, 100), 100);
    colorsRight[i] = color(random(160, 190), 100, random(0, 100));
  }
}

function keyPressed() {
  if (key == "a")
    shakeColors();
  if (key == "c" || key == "C")
    writeFile([gd.ase.encode(colors)], gd.timestamp(), "ase");
  if (key == "s" || key == "S") saveCanvas();
}
```
> - EXPECTATIVA: La verdad hice esto simplemente eliminando las lineas que identifique que ya no estaban cuando cambiamos la lectura de datos de ASCII a binario. Llevo horas acumuladas de sueño y veo algo borroso. No creo que funcione cuando llegue a clase a probarlo, pero tampoco espero que sea muy dificil. ¿Quizas puse algunas nuevas lineas donde no era?
>
> - REALIDAD: no se lol
