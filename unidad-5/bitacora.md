
# Evidencias de la unidad 5

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## 🎀**ACTIVIDAD 01**🎀

-  🎟️ **Describe cómo se están comunicando el micro:bit y el sketch de p5.js. ¿Qué datos envía el micro:bit?**

> El microbit está enviando constantemente una serie de datos por medio de la conección serial, los cuales el p5js usa para ejecución del código. Por ejemplo, si recive un True para el botón A, es porque está presionado en la microbit.

-  🐦 **¿Cómo es la estructura del protocolo ASCII usado?**

> La estructura está en hexadecimal, compuestas por numeros y letras.

-  🧣**Muestra y explica la parte del código de p5.js donde lee los datos del micro:bit y los transforma en coordenadas de la pantalla.**

```
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

```
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
Genuinamente estaba tratando de hacer esos arboltos pomposos de la película el Lorax, pero no me quedaron jajaja
<img width="826" height="805" alt="no se" src="https://github.com/user-attachments/assets/d4dfbf25-23a3-401e-b2c5-72fd73f88e32" />

## 🎃**ACTIVIDAD 02**🎃
🐯🦞🏀🧱✂️🍛🍑🏵️🍂🔥🔅🔸

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

- 🦋 **¿Cuántos bytes se están enviando por mensaje? ¿Cómo se relaciona esto con el formato '>2h2B'? ¿Qué significa cada uno de los bytes que se envían?**
>
> <img width="1012" height="247" alt="image" src="https://github.com/user-attachments/assets/5cf25436-9346-4820-9b06-26678e05881b" />
> <img width="1018" height="240" alt="image" src="https://github.com/user-attachments/assets/cc7950d8-b0cf-4385-90bf-9b1d293b763c" />


