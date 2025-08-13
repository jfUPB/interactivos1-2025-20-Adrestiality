# Unidad 2

## 🤔 Fase: Reflect
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**

**[PARTE 1: recuperación de conocimiento]**

-  Describe con tus palabras qué es una máquina de estados. ¿Cuáles son sus cuatro componentes fundamentales que has utilizado en esta unidad? 

Es un sistema que puede estar en una cantidad específica, no infinita, de estados. También estas pueden cambiar de estado en respuesta a ciertos eventos o interacciones.

-  Explica por qué la técnica de máquina de estados es tan útil para gestionar la “concurrencia” (atender un temporizador y botones “al mismo tiempo”) en un dispositivo con un solo hilo de ejecución como el micro:bit. ¿Qué problema soluciona en comparación con usar funciones como sleep()? 

La técnica de estados es útil ya que nos permite administrar las acciones y eventos que suceden con la microbit. Adicionalemnte, nos permite añadir sub - eventos, por asi decirlo, a los eventos principales. El sleep nos soluciona el problema de cuando queremos que cierta función se duerma o se desactive cierta función pero puede tener consecuencias para los fps de las animaciones o imágenes que aparecen en el display

-  Imagina que tienes que añadir una nueva funcionalidad a la bomba temporizada: si se agita (shake) el micro:bit mientras la cuenta regresiva está activa, el tiempo se reduce a la mitad. ¿Cómo modificarías tu diagrama de máquina de estados para incluir este nuevo evento y acción? 

Pues primero añadiría el sub evento, (con las misma línea de código que el que se usa para activar la bomba) y que la acción sea dividir el tiempo que configuramos a la mitad, y que luego retome la cuenta regresiva. Aunque esto ultimo no se bien como se haría

- Explica qué es un “vector de prueba” y por qué es una herramienta crucial para verificar que una máquina de estados funciona como se espera 

Es un vector que tiene ciertos datos de entrada que tiene como proósito probar la funcionalidad del código. Nos sirve para, valga la redundancia; comprobar segmentos del código antes de ingresar las variables reales o dejarlo que ejecute con el caso real de valores

**[PARTE 2:  reflexión sobre tu proceso]**

-  ¿Qué parte del diseño de la bomba temporizada te resultó más desafiante: crear el diagrama de estados (Actividad 04) o traducir ese diagrama a código MicroPython (Actividad 05)? ¿Por qué?

Muy honestamente considero que fue el código en la parte en la que el sistema debía verificar que aun estaba en cuenta regresiva o si ya estaba en 0 para pasar de estado. De resto, siento que el código que habia  de las caritas y lo del semáforo nos guiaba mucho. por otro lado, aun no me queda muy muy claro la estructura que va dentro de los cuadros de el diagrama (los grises), pero en general es fácil graficar la secuencia de estados 

-  Describe un error o “bug” que encontraste al implementar tu programa. ¿Cómo te ayudó pensar en términos de estados, eventos y transiciones a identificar y solucionar el problema?

realmente tuve dos problemas. El rpimero es que queria que se viera un pacman en el display antes de llegar al estado de configuración pero no se veia sino que el código iba directamente al estado de configuración... La solución seria usar un sleep que condena un poco los fps. 
El otro problema era respecto al contador en el display, ya que iba pasando pero iba como de 3 en 3. El problema esta en el que la cuenta seguía disminuyendo pero la animación de los numeros era muy tardía entonces esa diferencia hacia que el numero no fuese continuo sino que saltaba de 3 en 3.

-  El problema de la bomba era complejo. ¿Qué estrategia usaste para abordarlo? ¿Comenzaste con una versión simple y añadiste funcionalidades poco a poco?

La verdad es que fue divertido al inicio. Estaban muy claros los estados y las variables necesarias y en que momento se debian establecer los valores que fuesen equivalentes a un tiempo real. Todo era rosa hasta la cuenta regresiva... Ahí tuve que ver que era lo que hacia una IA para solucionarlo porque no encontre más que hacer. La solución era que se restaran algunos tiempos para que el código verificara si la cuenta estaba o no en 0

-  Ahora que entiendes el patrón de máquina de estados, ¿En qué otro tipo de proyecto o sistema de entretenimiento digital crees que podrías aplicarlo?

Hmmm la verdad no se me ocurre ahorita ninguno

### **ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

**BITÁCORA DE CAROLINA GARCÍA ORTEGA**

-  **[REVISIÓN ACTIVIDAD 4]**
Me gusta bastante su diagrama. Es bastante conciso y facil de leer. No esta sobrecargado con líneas de código como el mío

-  **[REVISIÓN ACTIVIDAD 5]**
Veo que ella no tenía un estado init como yo, sino que el código empezaba en el estado de configuración. Me gusta que ella pudiera poner un dibujito en el display. de resto lo veo bastante bien y correcto

### **ACTIVIDAD 08 ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  [Continuar] ¿Qué actividad, explicación o ejemplo de esta unidad te ayudó más a entender el poder de las máquinas de estados? ¿Qué elemento consideras que es indispensable y debería mantener?

Lo que más me ayudó a entender conceptos fue el diagrama y el código del cambio de caritas. Leerlo línea por línea e irlo comparando con el diagrama me ayudó a entender muchas funciones

-  [Dejar de hacer] ¿Hubo algún paso o actividad que te pareció confuso, innecesariamente complicado o que aportó poco a tu aprendizaje? ¿Qué cambiarías o eliminarías?

Creo que algo que me cuesta mucho es la lógica, pero también, el desconocer algunas funciones que hay. Reconozco que soy muy floja para ponerme a leer y entender las librerías que hay o se pueden incorporar y acabo acudiendo a segundos para que me ayuden una vez me sienta estancada. Pero respecto a la clase, no considero que haya que dejar de hacer algo. Me gustan las clases entretenidas que nos hacen reír, es mas divertido

-  [Empezar a hacer] ¿Qué te habría ayudado a entender mejor?

Saber de la existencia de las funciones que puedo o no emplear en alguna actividad. Pero creo que eso es más tarea del estudiante a medida que se va familiarizando con el lenguaje


-  [Ritmo y dificultad] En una escala del 1 (muy fácil) al 5 (muy difícil), ¿Cómo calificarías la dificultad de pasar del análisis de un programa (Actividad 03) al diseño desde cero de uno complejo (Actividad 04 y 05)? ¿Por qué?

Le pondría un 5. La verdad es que me divertí un poco programando. Cosa que es poco común dado a que mis neuronas son alérgicas a la lógica de programación
 
-  [Comentario adicional] ¿Hay algo más que te gustaría compartir sobre tu proceso de aprendizaje en esta unidad? ¿Algún momento de frustración o de “¡Aha!” que quieras destacar?

Probablemente mi momento "aha" fue cuando comprendi como integrar las acciones secundarias dentro de los estados y cuando entendí algunas cosas del tiempo, aunque aun debo reforzarlas un poco

