
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
- 
<img width="826" height="805" alt="no se" src="https://github.com/user-attachments/assets/d4dfbf25-23a3-401e-b2c5-72fd73f88e32" />

