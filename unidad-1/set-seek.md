# Unidad 1

## 🔎 Fase: Set + Seek

### Actividad 01

#### ¿Qué es un sistema físico interactivo?
es una experiencia relacionada con un usuario y un codigo, cuyo resultado depende de las acciones del usuario. crear imagenes diferentes dependiendo de los movimientos de la mano, o crear piezas abstractas dependiendo de los ritmos de una cancion

#### ¿Cómo podrías aplicar lo que has visto en tu perfil profesional?
para crear experiencias interactivas. un momento que te obliga a recordar. he de admitir que me llama la atencion crear un sistema fisico que sea manipulado por una masa de personas... imagínate un sistema físico que crea imagenes dependiendo de como aplaude las personas en un concierto... 

### Actividad 02

#### ¿Qué es el diseño/arte generativo?
es un tipo de arte que emplea principalmente el uso de tecnologías con cierto grado de autonomía para la elaboración de una pieza, pero las propuestas y reglas siguen siendo de mano humana que abren puertas para una nueva forma de creación de productos y un nuevo género de arte

#### ¿Cómo podrías aplicar lo que has visto en tu perfil profesional?
El uso de las tecnologías es crucial para la elaboración de los sistemas físicos interactivos. siento que es como una corriente diferente a los que nos acostumbran a la carrera... no todo son juegos u animaciones, aqui se nos proporciona una tercera opcion con arte humano-maquina...

### Actividad 03

#### Inputs
Los botones del microbit, el acelerómetro y el serial que conecta el pc y la tarjeta.

### Outputs
Las caritas que hace el microbit y lo de los circulos de colores con las letras.

### Proceso
El programa en Python se encarga de enviarle las señales de lo que se debe ver en cada caso de cada señal o gesto que hagamos y el P5.sj se encarga de recibir las señales del microbit.

### Actividad 04

####[Enlace a P5js](https://editor.p5js.org/Adrestiality/sketches/0W3UMoq6-)

#### Código
```
function setup() {
  createCanvas(600, 600, WEBGL);
}

function draw() {
  background(200);

  orbitControl();
  
   ambientLight(50, 50, 50);

  directionalLight(255, 100, 100, 10, 10, -1);
 
  specularMaterial(206,183,219);
  
  stroke(51,9,17)

  radius = mouseX
  tubeRadius = radius/2
  
  torus(mouseX, tubeRadius,16,10);
  
}
```
#### Imágenes
![]("C:\Users\sruiz\Pictures\Screenshots\Captura de pantalla 2025-07-20 095824.png")

