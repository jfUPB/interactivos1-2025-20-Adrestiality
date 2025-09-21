
# Rúbrica de evaluación de la unidad | ACTIVIDAD 4

🔸 **Mi nota propuesta: 3.9**    
  
- ## ✨ **PROFUNDIDAD DE LA INDAGACIÓN: Logrado (4.4)** 

El estudiante hace experimentos y análisis con el protocolo binario y sus diferencias con el protocolo ASCII. Así mismo como hace experimentos para analizar y comprender la cantidad de bytes que se envían por dato y el cómo el protocolo binario ahorra bytes pese a su ineficiencia 

**═∘◦✧◦∘═ ⭐EVIDENCIA 1⭐ ═∘◦✧◦∘═** 

<img width="1030" height="562" alt="Captura de pantalla 2025-09-20 185332" src="https://github.com/user-attachments/assets/c7b30322-dbc4-442a-884e-c137f242bfdd" />

**═∘◦✧◦∘═ ⭐EVIDENCIA 2⭐ ═∘◦✧◦∘═**
<img width="1032" height="589" alt="Captura de pantalla 2025-09-20 185354" src="https://github.com/user-attachments/assets/66c27722-2ecf-46b8-885e-5ff1d099d2e1" />

**═∘◦✧◦∘═ ⭐EVIDENCIA 3⭐ ═∘◦✧◦∘═**
<img width="1057" height="565" alt="Captura de pantalla 2025-09-20 185412" src="https://github.com/user-attachments/assets/3afc34f5-6e30-4b5f-9d6a-06d66f7a796d" />  


- ## ✨ **CALIDAD DE LA EXPERIMENTACIÓN: Logrado (3.8)** 

El estudiante realiza experimentos en la actividad aplicativa donde evidencia los valores enviados y su correcta recepción desde la consola de p5js. Pese a que el estudiante no realizó un error de checksum, consigue hacer hipótesis del por qué pueden generarse estas fallas y la importancia del por qué se debe implementar el framing 

**═∘◦✧◦∘═ ⭐EVIDENCIA 4⭐ ═∘◦✧◦∘═**
<img width="821" height="133" alt="Captura de pantalla 2025-09-20 185508" src="https://github.com/user-attachments/assets/02a66c9d-41e6-46dc-8e5b-32e2c7d574b7" />


**═∘◦✧◦∘═ ⭐EVIDENCIA 5⭐ ═∘◦✧◦∘═**
<img width="929" height="154" alt="Captura de pantalla 2025-09-20 185528" src="https://github.com/user-attachments/assets/a36d7255-189f-4ba7-a390-195ebf32f37d" />


**═∘◦✧◦∘═ ⭐EVIDENCIA 6⭐ ═∘◦✧◦∘═**
<img width="960" height="94" alt="Captura de pantalla 2025-09-20 185548" src="https://github.com/user-attachments/assets/c312d545-e053-4a01-8d72-8b54487f768e" />


- ## ✨ **CALIDAD DEL ANÁLISIS Y LA REFLEXIÓN: Logrado (4.0)** 

El estudiante analiza deliberadamente el funcionamiento y la estructura del framing, así mismo como comprender la importancia de actualizar la recepción de los valores para el correcto funcionamiento de la experiencia interactiva con el microbit y p5jss

**═∘◦✧◦∘═ ⭐EVIDENCIA 7⭐ ═∘◦✧◦∘═**
<img width="1008" height="104" alt="Captura de pantalla 2025-09-20 185613" src="https://github.com/user-attachments/assets/8ff1c89a-562c-4d3e-bdf5-0a8f85969383" />

**═∘◦✧◦∘═ ⭐EVIDENCIA 8⭐ ═∘◦✧◦∘═**
<img width="1039" height="146" alt="Captura de pantalla 2025-09-20 185701" src="https://github.com/user-attachments/assets/8a08e247-5438-4c05-8d9c-a4eece01e533" />


- ## ✨ **APROPIACIÓN Y ARTICULACIÓN DE LOS CONCEPTOS: En desarrollo (3.4)** 
El estudiante se limita a explicar de manera básica la estructura del protocolo binario por medio de la representación de los bytes y su cantidad, haciendo repetidamente énfasis en que es más liviano y fácil de leer 

**═∘◦✧◦∘═ ⭐EVIDENCIA 9⭐ ═∘◦✧◦∘═**
<img width="1033" height="124" alt="Captura de pantalla 2025-09-20 185718" src="https://github.com/user-attachments/assets/2e40b448-8e79-4554-a2b3-c7f00c8e7739" />

# ACTIVIDAD 5

-  🌙 **Justifica con ejemplos concretos tomados de las aplicaciones modificadas.**

| Aspecto                     | Protocolo ASCII | Protocolo Binario | Ejemplo |
|--------------------------------|----------------|-----------------------------|----------------|
 | **Eficiencia** | Poco eficiente ya que ocupa más bytes y su cantidad por dato es indefinida (motivo por el cual necesita usar /n) | Muy eficiente, ya que sus datos son mas compactos y sus tamaños son definidos | Con el protocolo ASCII el numero 225 requiere de enviar el 2, 2, 5 mientras que en binario deberia bastar con un solo byte|
| **Velocidad** |Lento ya que se envian muchos más caracteres | rapido ya que son menos bytes para transmitir la misma información | En cualquier juego, por ejemplo minecraft, que esta actualizando constantemente los valores de la coordenadas de la posicion del jugador, deberian llegar mas rapido si se envian en bytes|
| **Facilidad** | Es más facil de depurar y no suele tener margen error por mas que se sobrecarguen los valores. ademas es facil de leer    | Dificil de depurar ya que existe una gran margen de error y hay que incluir codigos que le den un sistema robusto al programa que debe recibir los datos y calificar cuales deben servir y cuales no. ademas es dificil de leer y depende de una traduccion hexadecimal para comprenderlo| El ASCII se puede leer en un simple monitor serial, y el binario solo se lee en hexadecimales... ni modo de leer rombos con signos de interrogación no? |
| **Recursos** | Consume mas memoria porque envia más bytes   | Consume menos memoria porque son menos bytes | En dispositivos de memoria demasiado limitada conviene usar bytes |
>
-  🌙 **¿Por qué fue necesario introducir framing en el protocolo binario?**

> Porque con el binario no hay delimitadores de los valores que llegan, el framing nos permite decirle al programa donde empieza y donde termina un conjunto de datos para despues decirle que hacer con ellos 
>
-  🌙 **¿Cómo funciona el framing?**

> Se le proporciona un tamaño fijo para que pueda empezar a separar los valores y luego usarlos para otras cosas
>
-  🌙 **¿Qué es un carácter de sincronización?**

> es un caracter especial que indica el inicio de un paquete de datos
>
-  🌙 **¿Qué es el checksum y para qué sirve?**

> es una suma de datos que nos permite detectar errores. Si la suma de datos no corresponde a la misma del framing, se interpreta que los valores estan incompletos y se descarta la linea de datos y espera a recibir una nueva y evaluarla
>
-  🌙 **¿Qué hace la función concat? ¿Por qué?**

> combina  dos cadenas de valores, ya que a veces los datos en el protocolo binario pueden llegar fragmentadas
>
-  🌙 **En la función readSerialData() tenemos un bucle que recorre el buffer solo si este tiene 8 o más bytes ¿Por qué?**

> Anteriormente, en el framing se otorgo una cantidad especifica de bytes. En el ejemplo del codigo, son 8. Si tiene menos, no se puede procesar
>
-  🌙 **En el código anterior qué significa 0xaa?**

> significa hexadecimal
>
-  🌙 **En el código anterior qué hace la función shift y la instrucción continue? ¿Por qué?**

> shift elimina el primer elemento del buffer, el continue limpia los bytes hasta encontrar el 0xAA
>
-  🌙 **Si hay menos de 8 bytes qué hace la instrucción break? ¿Por qué?**

> Se sale del bucle y espera a la siguiente linea de datos para su analisis. gracias a esto, el codigo no usa valores incompletos y evita los errores
>
-  🌙 **¿Cuál es la diferencia entre slice y splice? ¿Por qué se usa splice justo después de slice?**

> Slice copia los 8 bytes sin borrarlos, el splice elimina los bytes del buffer. Lo limpia para la siguiente llegada de datos
>
-  🌙 **A la siguiente parte del código se le conoce como programación funcional ¿Cómo opera la función reduce?**

> Es la suma de los bytes para el checksum
>
-  🌙 **¿Por qué se compara el checksum enviado con el calculado? ¿Para qué sirve esto?**

> valida que los datos no se hayan corrompido, si es elcaso, se descarta
>
-  🌙 **En el código anterior qué hace la instrucción continue? ¿Por qué?**

> salta el procesamiento del paquete con error y pasa al siguiente
>
-  🌙 **¿Qué es un DataView? ¿Para qué se usa?**

> permite leer datos de diferentes tamaños
>
-  🌙 **¿Por qué es necesario hacer estas conversiones y no simplemente se toman tal cual los datos del buffer?**

> el buffer solamente puede leer una secuencia de bytes, por lo que el dataview lo traduce por el
>

