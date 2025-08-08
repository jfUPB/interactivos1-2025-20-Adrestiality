# Unidad 2

## 🤔 Fase: Reflect
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**

[PARTE 1: recuperación de conocimiento]

-  Describe con tus palabras qué es una máquina de estados. ¿Cuáles son sus cuatro componentes fundamentales que has utilizado en esta unidad? 

Es un sistema que puede estar en una cantidad específica, no infinita, de estados. También estas pueden cambiar de estado en respuesta a ciertos eventos o interacciones.

-  Explica por qué la técnica de máquina de estados es tan útil para gestionar la “concurrencia” (atender un temporizador y botones “al mismo tiempo”) en un dispositivo con un solo hilo de ejecución como el micro:bit. ¿Qué problema soluciona en comparación con usar funciones como sleep()? 

La técnica de estados es útil ya que nos permite administrar las acciones y eventos que suceden con la microbit. Adicionalemnte, nos permite añadir sub - eventos, por asi decirlo, a los eventos principales. El sleep nos soluciona el problema de cuando queremos que cierta función se duerma o se desactive cierta función pero puede tener consecuencias para los fps de las animaciones o imágenes que aparecen en el display

-  Imagina que tienes que añadir una nueva funcionalidad a la bomba temporizada: si se agita (shake) el micro:bit mientras la cuenta regresiva está activa, el tiempo se reduce a la mitad. ¿Cómo modificarías tu diagrama de máquina de estados para incluir este nuevo evento y acción? 

Pues primero añadiría el sub evento, (con las misma línea de código que el que se usa para activar la bomba) y que la acción sea dividir el tiempo que configuramos a la mitad, y que luego retome la cuenta regresiva. Aunque esto ultimo no se bien como se haría

- Explica qué es un “vector de prueba” y por qué es una herramienta crucial para verificar que una máquina de estados funciona como se espera 

Es un vector que tiene ciertos datos de entrada que tiene como proósito probar la funcionalidad del código. Nos sirve para, valga la redundancia; comprobar segmentos del código antes de ingresar las variables reales o dejarlo que ejecute con el caso real de valores

-  **[PARTE 2:  reflexión sobre tu proceso]**

¿Qué parte del diseño de la bomba temporizada te resultó más desafiante: crear el diagrama de estados (Actividad 04) o traducir ese diagrama a código MicroPython (Actividad 05)? ¿Por qué?

xxxx

Describe un error o “bug” que encontraste al implementar tu programa. ¿Cómo te ayudó pensar en términos de estados, eventos y transiciones a identificar y solucionar el problema?

xxx

El problema de la bomba era complejo. ¿Qué estrategia usaste para abordarlo? ¿Comenzaste con una versión simple y añadiste funcionalidades poco a poco?

xxx

Ahora que entiendes el patrón de máquina de estados, ¿En qué otro tipo de proyecto o sistema de entretenimiento digital crees que podrías aplicarlo?

### **ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

**BITÁCORA DE CAROLINA GARCÍA ORTEGA**

-  [REVISIÓN ACTIVIDAD 4]

-  [REVISIÓN ACTIVIDAD 5]

### **ACTIVIDAD 08 ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  [Continuar] ¿Qué actividad, explicación o ejemplo de esta unidad te ayudó más a entender el poder de las máquinas de estados? ¿Qué elemento consideras que es indispensable y debería mantener?

-  [Dejar de hacer] ¿Hubo algún paso o actividad que te pareció confuso, innecesariamente complicado o que aportó poco a tu aprendizaje? ¿Qué cambiarías o eliminarías?

-  [Empezar a hacer] ¿Qué te habría ayudado a entender mejor?

-  [Ritmo y dificultad] En una escala del 1 (muy fácil) al 5 (muy difícil), ¿Cómo calificarías la dificultad de pasar del análisis de un programa (Actividad 03) al diseño desde cero de uno complejo (Actividad 04 y 05)? ¿Por qué?

-  [Comentario adicional] ¿Hay algo más que te gustaría compartir sobre tu proceso de aprendizaje en esta unidad? ¿Algún momento de frustración o de “¡Aha!” que quieras destacar?
