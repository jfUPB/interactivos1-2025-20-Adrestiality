# Unidad 3

## 🤔 Fase: Reflect

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───
 
### **ACTIVIDAD 08 ༓☾∘∙•⋅⋅⊰⋅•⋅**
 
**NOTA: acabo de terminar esta bitacora, y me senti en un deja vu increible. Acabo de descubrir que estas preguntas son las mismas del reflect de la unidad anterior... ya decia yo que eso de añadir un nuevo evento a la bomba lo habia visto en otro lugar...**
 
### **[Parte 1]**
 
1. **Describe con tus palabras qué es una máquina de estados. ¿Cuáles son sus cuatro componentes fundamentales que has utilizado en esta unidad?** 
Es una especie de modelo computacional o un diagrama que nos permite simplificar, diria yo que al maximo, el funcionamiento de un código que se compone de diferentes fases y tiene interacciones entre si. La verdad ahorita mismo no soy muy consiente de cuales son los 4 componentes del que nos referimos, pero recuerdo que dentro de los diagramas teniamos que especificar los estados del codigo, sus acciones y sus trancisiones entre si. Tambien los vectores de prueba eran muy utiles
 
2. **Explica por qué la técnica de máquina de estados es tan útil para gestionar la “concurrencia” (atender varios eventos y tareas “al mismo tiempo”) en un dispositivo con un solo hilo de ejecución como el micro:bit o en p5.js. ¿Qué problema soluciona en comparación con usar funciones como sleep()?**  
Usar la tecnica de maquina de estados es util cuando queremos ver de manera simplificada el comportamiento del codigo sin necesidad de estar viendo el código en si. Es como desmenuzar el comportamiento de lo que queremos hacer y nos deja miuy claro para donde van las cosas.     
Con respecto al sleep, podemos basicamente retardar la llegada de algunas funciones condenando los fps, algo que normalmente sería letal en un juego, pero en una microbit puede ser tolerable
 
3. **Imagina que tienes que añadir una nueva funcionalidad a la bomba: si se recibe un evento especial (por ejemplo, una combinación de botones o un comando serial) mientras la cuenta regresiva está activa, el tiempo se reduce a la mitad. ¿Cómo modificarías tu diagrama de máquina de estados para incluir este nuevo evento y acción?**  
No estoy muy segura del todo de como se podría añadir la funcion, pero seria necesario crear un evento especial como el de la contraseñña "ABA", pero en este caso tendríamos que tener muy presente el tiempo actual y el tiempo restante de la bomba, de modo en que si se activa dicho evento, las funciones puedan dividir el tiempo actual en 2 y establecer una nueva cuenta regresiva con dichos nuevo valor
 
4. **Explica qué es un “vector de prueba” y por qué es una herramienta crucial para verificar que una máquina de estados funciona como se espera.**   
Los vectores de prueba me parece que tienen un nombre muy engañoso. Parece como si fuesen pruebas que vas haciendoa  medida que haces el codigo para verificar de a poquitos que estas codificando bien. Estos llamados vectores de prueba son como "las misiones secundarias" de un codigo, es decir, hay un estado inicial y unas condiciones planteadas y se requiere de un evento en especifico que conlleva a un resultado esperado. Los llamo misiones secundarias, porque siento que estas alteran el flujo principal del codigo, enriqueciendo el abanco de posibilidades en el codigo

### [Parte 2]
 
1. **¿Qué parte del diseño de la bomba te resultó más desafiante: crear el diagrama de estados o traducir ese diagrama a código? ¿Por qué?**
Genuinamente, me pareció mas dificil codificar que hacer el diagrama. El diagrama es divertido, aunque ironicamente no soy fan de hacer diagramas antes de codificar, pero me dejan muy enclaro lo que quiero hacer para los codigos. ya en la parte de codificar es porque directamente siento que no le tengo la chispa a codificar. La verdad esta unidad me dio muy duro hacer codigo, dependi mucho de ayuda de mis compañeros porque ni con IA lograba lo que quería
 
2. **Describe un error o “bug” que encontraste al implementar tu programa. ¿Cómo te ayudó pensar en términos de estados, eventos y transiciones a identificar y solucionar el problema?**
Quizás es más el hecho de no saber escribir algunas funciones me llevaban a probar cosas muy raras con variables que encontraba por ahi
 
3. **El problema de la bomba era complejo. ¿Qué estrategia usaste para abordarlo? ¿Comenzaste con una versión simple y añadiste funcionalidades poco a poco?**
Inicialmente trate de hacer la traduccion de los codigos de la bomba linea por linea y funcion por funcion. pero descubri que hay funciones que exiaten en python que en javascript no, entonces me enrede mucho poer ese lado
 
5. **Ahora que entiendes el patrón de máquina de estados, ¿En qué otro tipo de proyecto o sistema de entretenimiento digital crees que podrías aplicarlo?**
siento que puede ser util en mini juegos, asi como la bomba. si se crea una buena narrativa y una buena identidad del producto, se puede crear un buen mini juego de una bomba que explita y debes encontrar la contraseña antes de que exploteee
 
### **ACTIVIDAD 09 ༓☾∘∙•⋅⋅⊰⋅•⋅**
 
1. **Continuar: ¿Qué actividad, explicación o ejemplo de esta unidad te ayudó más a entender el poder de las máquinas de estados? ¿Qué elemento consideras que es indispensable y debería mantener?**   
Definitivamente la explicacion paso a paso del diagrama y los ejemplos que ya habian en la pagina donde estan las instrucciones de las actividades me sirvieron mucho. quizas mis diagramas no son perfectos aun, pero me parece muy intuitivo asi
 
2. **Dejar de hacer: ¿Hubo algún paso o actividad que te pareció confuso? ¿Qué cambiarías o eliminarías?** 
No en realidad, solo siento que no se deberia limitar tanto la fase de apply. Esta en particular fue muy dificil porque dependiamos del microbit, asi que aquellos que no lograron acabar los dos códigos en clase, no teniamos manera de verificar el correcto funcionamiento del codigo... Tambien reconozco que se me hizo imposible la ultima actividad, la de traducir los codigos... no se, siento que me quedo atras con esta logica
 
3. **Empezar a hacer: ¿Qué te habría ayudado a entender mejor?**    
Por algun motivo me cuesta mucho pensar y ser creativa cuando hago codigos. Al no saber funciones, opciones y poco más de cosas, me cuesta encontrar en internete el tipo de funciones que necesito para mi caso especifico o inventarme yo misma las funciones de manera creativa
 
5. **Ritmo y dificultad: En una escala del 1 (muy fácil) al 5 (muy difícil), ¿Cómo calificarías la dificultad de pasar del análisis de un programa a diseñar y programar uno complejo? ¿Por qué?**  
5, la verdad me dio duro esta unidad jaja, lo genial es hacer los diagramitas asi sencillitos
 
7. **Comentario adicional: ¿Hay algo más que te gustaría compartir sobre tu proceso de aprendizaje en esta unidad? ¿Algún momento de frustración o de “¡Aha!” que quieras destacar?**   
no tengo comentarios adicionales. Siento que el profesor hace mucho esfuerzo para llegar a su cometido de enseñarnos la logica de programacion, lo encuentro muy dedicado :)  
