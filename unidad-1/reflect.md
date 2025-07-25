# Unidad 1

## 🤔 Fase: Reflect

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───
### ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

### [Parte 1]

-  #### Basándote en los ejemplos que vimos de sistemas físicos interactivos al iniciar el curso, describe las tres características que definen a un sistema físico interactivo.
1. Uso de tecnología para crear algo
2. Interacción entre humano y máquina
3. El resultado de la interacción siempre será diferente y única dependiendo del usuario y su estado
   
-  #### Explica el modelo input-process-output de Patrick Hübner usando como ejemplo el sistema que construiste con micro:bit y p5.js en la Actividad 06. ¿Cuál fue el input, cuál fue el proceso y cuál fue el output?
Aquí buscábamos crear un sistema que cambiara d posición cierto circulos dependiendo de los botones que el usuario presionara en el microbit.

INPUT:
Serían los botones de la microbit que a su vez se traducian como letras

PROCESO: 
En la página de microbit, hicimos un código para que reconociera los botones como letras y el como duran presionadas dentro del programa. 
Luego en P5sj creamos otro código, con una librería adicional a las que se proporcionan, para que se creara un circulo y un boton para conectar a la microbit. 

OUTPUT:
Dependiendo de las letras que se creaban a base de los botones, El circulo se movia a la izquierda o derecha 

-  #### ¿Cuál es la función de la línea uart.write('A') en el código del micro:bit y qué función en p5.js se encarga de “escuchar” ese mensaje?
Esa línea era la que traducía el botón de la microbit y le asignaba una letra, en este caso le asignaba la "A".
Ya en P5sj hay otra línea que es datarx que creo que es la que se encarga de leer dicha letra para que el resto del código la use a su favor

-  #### ¿Cuál es la diferencia fundamental entre el arte/diseño tradicional y el arte/diseño generativo?
Aunque si bien tanto el arte generativo y el tradicional se componen principalmente de tener una mente humana, el arte generativo tambien se compone del uso de una máquina, que con ciert autonomía, realiza una serie de ordenes y un producto, mientras que el tradicional depende únicamente de la mente y la habilidad de la persona

-  #### Imagina que quieres que un círculo en p5.js cambie a un color aleatorio cada vez que sacudes el micro:bit. Describe qué tendrías que programar en el micro:bit y qué tendrías que programar en p5.js para lograrlo.
Para ello, se requiere incorporar una biblioteca para crear unas líneas que te permiten crear un boton que accede a la microbit. Luego se necesita otrso códigos que te permiten leer los estimulos de la microbit. Luego hacemos el circulo, su tamaño y ubicacion, y luego que dependiendo del estiulo cambie de color

### [Parte 2]

-  #### ¿Qué fue más desafiante para ti en esta unidad: la parte conceptual (entender qué es un sistema físico interactivo) o la parte técnica (hacer que el micro:bit y p5.js se comunicaran)? ¿Por qué?
probablemnte la parte de la técnica.. programar siempre ha sido un poco complicado para mi. Pero lo encuentro interesante.

-  #### Describe el momento “¡Aha!” que tuviste cuando lograste que una acción en el micro:bit (presionar un botón, sacudirlo) tuviera un efecto visible en el canvas de p5.js por primera vez. ¿Qué fue lo que entendiste en ese instante?
Cuando conseguí crear una especie de dona gigante que se agranda y se achica. Entendi como hacer que el radio de la dona se adaptara al movimiento en x del mouse

-  #### Al inicio de la unidad te pregunté: “¿Este curso para qué me sirve?”. Después de experimentar y construir tu primer prototipo, ¿Cómo ha cambiado o se ha vuelto más concreta tu respuesta a esa pregunta?
No. considero que igue sigue siendo la misma respuesta. En esta carrera la interacción humano máquna es demasiado útil y cumple con nuestro propósito. crear experiencias y momentos

-  #### El tutorial de la Actividad 05 te llevó paso a paso. ¿Cómo te sentiste con ese método de aprendizaje? ¿Te dio seguridad o preferirías haberlo intentado por tu cuenta desde el principio?
La verdad me gustóbastante esta metodología. hacer todo paso a paso y sumado a la explicación del docente. creo que fue una actividad que me gustó realizar, no por el producto, sino por su metodología

### ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

[BITÁCORA DE CAROLINA GARCÍA]
En realidad, yo tome de inspiración el código de caro. Realmente logró todo de una manera más concisa y directa. Me gusta su orden y lo compacto que hace las cosas.
El código hace que apareza un circulo y con ello un boton para conectar la microbit. luego, dependiendo del botón que se undió, los circulos se movian 20 posiciones a la izquierda o derecha

### ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  #### Continuar: ¿Qué actividad, video o ejemplo de esta unidad te resultó más inspirador o te ayudó más a entender el potencial de los sistemas físicos interactivos?
uff sin duda el código que que hacxe imágenes generativas dependiendo de ma música

-  #### Dejar de hacer: ¿Hubo alguna parte que te pareció demasiado abstracta, muy rápida o confusa? ¿Hay algo que crees que podríamos cambiar para que sea más claro?
No realmente. siento que la mayor dificultad es no entender python (y eso sumándolo a que se me dificulta la programación y su lógica). Lo que hace que no entienda que estoy programando específicamente. comprendo por segmentos, pero no se por que cierta función hace lo que hace, y por qué hace otras cosas si lo mezclamos con más funciones

-  #### Empezar a hacer: ¿Qué te genera más curiosidad ahora? ¿Te gustaría explorar más sensores del micro:bit (luz, temperatura), crear visualizaciones más complejas en p5.js o ver más ejemplos de proyectos artísticos?
He de admitir que tengo cierto interés y curiosidad en hacer más cosas con las microbit... le tengo cierto encanto a esas cositas

-  #### Balance inspiración vs. técnica: ¿Cómo sentiste el equilibrio entre ver los videos inspiradores de la Actividad 01 y la parte técnica de conectar las herramientas en las actividades 03-06?
Aunque si bien considero que los primeros videos nos da una excelente introducción del curso, tambien puede llegar a intiidarnos un poco. 
Me gustaría tambien poder ver material de productos con la microbit por ejemplo, que es con lo que empezamos estas semanas

-  #### Comentario adicional: ¿Hay algo más que quieras compartir sobre tu experiencia en esta unidad introductoria?
Me gusta el acompañamiento docente de estos cursos. De resto, considero que no tengo más comentarios adicionales

  
