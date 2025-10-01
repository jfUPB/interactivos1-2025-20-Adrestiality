 
## ACTIVIDAD 01

- **¿Qué ocurrió en la terminal cuando ejecutaste npm install? ¿Cuál crees que es su propósito?**

````
added 120 packages, and audited 121 packages in 2s

17 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
npm notice
npm notice New major version of npm available! 10.9.3 -> 11.6.1
npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.6.1
npm notice To update run: npm install -g npm@11.6.1
npm notice
````
>Cuando ejecutamos el install, lo que nos mustra son los numeros de la version que se esta ejecutando y si hay posbles actualizaciones

- **¿Qué mensaje específico apareció en la terminal después de ejecutar npm start? ¿Qué indica este mensaje?**
>
> <img width="580" height="429" alt="image" src="https://github.com/user-attachments/assets/5bf84eda-6591-43ed-b1aa-b12b2c8a16c2" />
>
> Despues de ejecutar el start nos deja entender que ya el servidor se abrio y que ya podemos hacer uso de el. Nos da una especie de direccion de enlace


- **Describe lo que ves inicialmente en page1 y page2 en tu navegador**
>
> <img width="1097" height="437" alt="image" src="https://github.com/user-attachments/assets/87ff6cc2-cb5a-45b6-b94e-01aca71d7087" />
> <img width="941" height="797" alt="image" src="https://github.com/user-attachments/assets/9c3cbe07-037e-48f5-a014-36ea0f4777ad" />
>
> Podemos ver una especie de aplicacion interactiva que consta de dos puntos (en dos ventanas diferentes) que estan unidos por una linea intermedia. la gracia de la aplicacion interactiva esta en que independientemente de la ubicacion de los dos puntos con ventanas de diferentes tamaños y ubicaciones, la linea que los conecta en la mitad, siempre esta apuntando la ubicacion del otro punto. En otras palabras, la ubicacion de los puntos se actualiza constantemente 

- **¿Qué mensajes aparecieron en la terminal del servidor cuando abriste page1 y page2?**
>
> Los mensajes que aparecen son sobre los ID  de las dos ventanas y los valores de las coordenadas que se actualizan en cada cambio
>
> <img width="548" height="484" alt="image" src="https://github.com/user-attachments/assets/c2baa36b-7197-4084-a391-0502450384a4" />

- **Describe qué sucede en ambas páginas del navegador cuando mueves una de las ventanas. ¿Cambia algo visualmente? ¿Qué mensajes aparecen (si los hay) en la consola del navegador (usualmente accesible con F12 -> Pestaña Consola) y en la terminal del servidor?**
>
> Claro que camboia algo. La ubicacion de las bolitas se actualizan en cada movimiento de ventana.
>
> En la consola del navegador podemos ver que tambien se le actualizan los valores a base de lo que aparece en la ventana del git
<img width="577" height="85" alt="image" src="https://github.com/user-attachments/assets/55b74ec6-ad53-4d89-a3b5-c6708fc3851b" />
<img width="1328" height="294" alt="image" src="https://github.com/user-attachments/assets/9e37e505-5ee2-487c-b967-65450d910e32" />

## **ACTIVIDAD 02**

- **Piensa en cómo te conectas a Internet en casa o en la Universidad. ¿Usas Wi-Fi? ¿Un cable de red? Eso es simplemente tu “rampa de acceso” a la gran red de carreteras. ¿Qué pasaría si esa rampa se corta? Anota tus ideas.**
>
> En mi casa usamos un cable de red, aunque cuando no estoy en ella uso la primera red wifi. Toamndo en cuenta que esto es nuestra rampa de acceso a la red de carreteras y cables que nos proporciona el internet, al derrumbarse simplemente quedamos fuera de la carretera temporal o definitivamente. Algo asi cuando tienes un carro en un garaje.. Quizas no lo usas porque tiene pico y plata o porque esta dañado o no puede andar

- **¿Puedes identificar otros ejemplos de relaciones Cliente-Servidor en tu vida diaria (no necesariamente digitales)? Por ejemplo, al pedir comida en un restaurante. ¿Quién es el cliente y quién el servidor? ¿Qué se pide y qué se entrega?**
>
>Realmente todo lo que tenga que ver con un veenderdor que te ofrece un tipo de producto en especifico y un cliente que busca ese mismo producto en especifico, como por ejemplo una tienda de ropa o una ferreteria, incluso una sastreria... tambien podemos llevar esto al nivel de las paginas web, la mera pagina puede funcionar como el vendedor, el servidor; y la cliente, aunque ahora de manera virtual, esta interesado en buscar algo alli

- **Toma la URL de tu sitio web favorito. Intenta identificar el protocolo, el nombre de dominio y la ruta (si la hay). ¿Qué crees que pasa si solo escribes el nombre de dominio (ej. www.google.com) sin una ruta específica? ¿Qué “página por defecto” crees que te envía el servidor?**
>
> Veamos loa pagina de Mope.io
>
>Es un jueguito online que consiste en moverse a traves de un mapa y comer casi culquier cosa que tengas en tu paso. entre mas comes, mas tamaño tienes, y entre mas grande mas puedes consumir y puedes eliminar a otros jugadores
>
> https://mope.io/
>
>El enlace del juego esta conformado unicamente por el https que es el protocolo y el mope.io que es el servidor

- **Compara HTTP con los protocolos seriales que usaste**
>
> - ¿Qué similitudes encuentras?
>
> La principal similitud esta en, obviamente, su funcionalidad y objetivo. Ya que ambas tienen como proposito permitir la comunicacion entre uno o varios dispositivos que cambian de estado
>
> - ¿Qué diferencias clave ves?
>
> La principal diferencia esta marcada en el como se escribe y se lee, asi mismo como que tanto puede abarcar cada tipo de protocolo
>
> - ¿Por qué crees que HTTP necesita ser más complejo que un simple envío de bytes como hacías con el micro:bit?
>
> Es muy diferente hablar del paso de informacion de una microbit que cuenta con una cantidad maxima de interacciones a hablar del cambio de informacion que se necesita de miles de millones de paginas web a tu diminuto dispositivo. La diferencia es demasiado enorme

- Piensa en una página web simple, como un formulario de login
>
> - ¿Qué parte crees que es HTML (ej. los campos de texto, el botón)?
>
> HTML se encargaria de definir todo lo de la ubicacion de las cosas. Aqui va un recuadro, aqui va un titulo, este parrafo y esta barra para que el usuario ponga su nombre... y asi sucesivamente
>
> - ¿Qué parte es CSS (ej. el color del botón, el tipo de letra)?
>
> CSS se encarga de lo bonito. El boton va de cierto color, al igual que lasletras tienen este otro y este tamaño de fuente... Aqui hay una imagen, y aqui hay un patron.... y etc etc
>
> - ¿Qué parte es JavaScript (ej. la comprobación de si escribiste algo antes de enviar, el mensaje de “contraseña incorrecta” que aparece sin recargar la página)?
>
> Java script se encarga de darle vida a todo. Se encarga de que los botones te redireccionen a donde deben, que te algan los textos de ingresa aqui tui nombre o que tge saque los avisos en caso de dejar un campo vacio

- Compara el bucle draw() de p5.js con este modelo de “esperar a que algo pase y reaccionar”.
>
> - ¿Qué ventajas crees que tiene el modelo basado en eventos para una interfaz de usuario web?
>
> Este modelo es mas facil de digerir para cualquier coa que lo este ejecutando. las paginas web casi siempre van a atener un numero limitado de interacciones, por lo que es mas facil dejar en el codigo literalmente un manual de acciones para cada accion diferente que creemos que va a hacer
>
> - ¿Sería eficiente tener un bucle draw() redibujando toda la página 60 veces por segundo si nada ha cambiado?
> 
> No, por supuesto que no. Es un sobreesfuerzo estupido el estar recargando una y otra vez cuando los cambios finalmentre se van a dar una vez un usuario presione una tecla o le de click algo

- ¿Por qué crees que podría ser útil usar JavaScript tanto en el cliente (navegador) como en el servidor? ¿Se te ocurre alguna ventaja para los desarrolladores?
>
> Aqui aun no esoy muy segura. Porque supongo que aqui estamos finjiendo demencia de los otros dos lenguajes que son html y css. Pero en realidad el hecho de que tanto el navegador y el servidor esten hablando en un solo idioma constantemente es un poco mas eficaz a mi parecer

- Resume con tus propias palabras la diferencia fundamental entre una comunicación HTTP tradicional y una comunicación usando WebSockets/Socket.IO. ¿En qué tipo de aplicaciones has visto o podrías imaginar que se usa esta comunicación en tiempo real?
>
> La comunicacion http consta principalemnte de que tu, como usuario, esperes una respuesta a tu peticion, que, aunque no esta mal, se úede mejorar gracias a WebSockets que te proporciona una libreria llena de opciones que reducen y casi que eliminan ese tiempo de espera. Todo es inmediato, volviendolo mucho mas eficaz

## **ACTIVIDAD 03** 

- **Detén el servidor si está corriendo. Cambia la primera ruta de /page1 a /pagina_uno. Inicia el servidor. Intenta acceder a http://localhost:3000/page1. ¿Funciona? Ahora intenta acceder a http://localhost:3000/pagina_uno. ¿Funciona? ¿Qué te dice esto sobre cómo el servidor asocia URLs con respuestas? Restaura el código.**
>
> No funciona si lo cambiamos a "pagina_uno2 ya que dentro del codigo tenemos definido que se llama page 1. Independientemente si cambiamo a pagina_uno antes o despues de bajar el servidor, no va a funcionar

- **Asegúrate de que el servidor esté corriendo (npm start). Abre http://localhost:3000/page1 en una pestaña. Observa la terminal del servidor. ¿Qué mensaje ves? Anota el ID. Abre http://localhost:3000/page2 en OTRA pestaña. Observa la terminal. ¿Qué mensaje ves? ¿El ID es diferente? Cierra la pestaña de page1. Observa la terminal. ¿Qué mensaje ves? ¿Coincide el ID con el que anotaste? Cierra la pestaña de page2. Observa la terminal.**
>
> Cada ventana tiene su propio ID, pero, independientemente si se abre o se cierran las pestañas seguiran con el mismo numero y letras

- **Inicia el servidor y abre page1 y page2. Mueve la ventana de page1. Observa la terminal del servidor. ¿Qué evento se registra (win1update o win2update)? ¿Qué datos (Data:) ves? Mueve la ventana de page2. Observa la terminal. ¿Qué evento se registra ahora? ¿Qué datos ves? Experimento clave: cambia socket.broadcast.emit(‘getdata’, page1); por socket.emit(‘getdata’, page1); (quitando broadcast). Reinicia el servidor, abre ambas páginas. Mueve page1. ¿Se actualiza la visualización en page2? ¿Por qué sí o por qué no? (Pista: ¿A quién le envía el mensaje socket.emit?). Restaura el código a broadcast.emit**
>
> Cuando realizamos movimientos entre las ventanas, los que aparece en el git es la actualizacion de su ubicacion en x y y, ademas de los valores de alto y ancho de la ventana, lo cual permite que en la actividad interactiva siempre parezcan conectados los puntos
>
> Cuando cambiamos esas lineas de codigo pasa algo raro pero no se como explicarlo. por decirlo de alguna manera las coordenadas de la pagina1 ya no se actualizan correctamente y puese hacer que la pagina 2 se confunda y cree una bolita en su propia ventana cuando realmente deberia estra dando la ilusion de que esta conectada a las otra

- **Detén el servidor. Cambia const port = 3000; a const port = 3001;. Inicia el servidor. ¿Qué mensaje ves en la consola? ¿En qué puerto dice que está escuchando? Intenta abrir http://localhost:3000/page1. ¿Funciona? Intenta abrir http://localhost:3001/page1. ¿Funciona? ¿Qué aprendiste sobre la variable port y la función listen? Restaura el puerto a 3000.**
>
> Una vez cambiamos los numeros desde el codigo base, cuando tratamos de abrir las paginas pero con el 300 original, nos dice que no se puede acceder a la pagina. En otras palabras hay que tener mucho cuidador para poder abrir la pagina con el numeo correcto

## **ACTIVIDAD 04**

- **Abre page2.html en tu navegador (con el servidor corriendo). Abre la consola de desarrollador (F12). Detén el servidor Node.js (Ctrl+C). Refresca la página page2.html. Observa la consola del navegador. ¿Ves algún error relacionado con la conexión? ¿Qué indica? Vuelve a iniciar el servidor y refresca la página. ¿Desaparecen los errores?**
>
> Caundo dsactivamos el servidor desde el node.jsla consola de la pagina te saca un error diciendo que hay un error de coneccion. Una vez reestablecemos el ervidor, la pagina se refrezca y sigue comun y corriente

- **Comenta la línea socket.emit(‘win2update’, currentPageData, socket.id); dentro del listener connect. Reinicia el servidor y refresca page1.html y page2.html. Mueve la ventana de page2 un poco para que envíe una actualización. ¿Qué pasó? ¿Por qué?**
>
> Al pareceer lo que hicimos fue hacer que la pagina 1 ya no recibiera actualizaciones de la ubicacion de la pagina 2. Por ende la pagina 2 era la unica a la que se le movia la secuencia de imagenes, ya que el si estaba recibiendo actualizaciones del 1. Esto mismo tambien se ve evidenciado en el git, ya que solo aprecen las coordenadas de solo una de las paginas

- **Asegúrate de tener este console.log en page2.js. Abre ambas páginas. Mueve la ventana de page1. Observa la consola del navegador de page2. ¿Qué datos muestra? Mueve la ventana de page2. Observa la consola de page1. ¿Qué pasa? ¿Por qué?**
>
> Las consolas del naegador deben de estra mostrando las coordenadas que estan analizando de la ventana contraria, a la que deben seguir 

- **Observa checkWindowPosition() en page2.js y modifica el código del if para comprobar si el código dentreo de este se ejecuta.Mueve cada ventana y observa las consolas. ¿Qué puedes concluir y por qué?**
>
> para este experimento decidi comentar todo el if a ver que pasaba. lo primero quennote es que ahora el circulo de la pagina 2, la que modificamos, se encontraba completamente pegad al limite, por lo que no se le veia bien si estaba al menos haciendo el ejercicio de apuntar al opuesto. el efecto en la page 1 fue que ya no podia calcular completamente bien la posicion de su opuesto

- **Cambia el background(220) para que dependa de la distancia entre las ventanas. Puedes calcular la magnitud del resultingVector usando let distancia = resultingVector.mag(); y luego usa map() para convertir esa distancia a un valor de gris o color. background(map(distancia, 0, 1000, 255, 0)); (ajusta el rango 0-1000 según sea necesario).**
>
> 000

## **ACTIVIDAD 05**

SERVER.JS
````
// server.js
const express = require('express');
const http = require('http');
const socketIO = require('socket.io');
const path = require('path');

const app = express();
const server = http.createServer(app);
const io = socketIO(server);
const port = process.env.PORT || 3000;

let page1 = { x: 0, y: 0, width: 200, height: 200, color: '#ff4444', pulse: 0 };
let page2 = { x: 0, y: 0, width: 200, height: 200, color: '#44ff44', pulse: 0 };

app.use(express.static(path.join(__dirname, 'views')));
app.get('/page1', (req, res) => res.sendFile(path.join(__dirname, 'views', 'page1.html')));
app.get('/page2', (req, res) => res.sendFile(path.join(__dirname, 'views', 'page2.html')));

function isValidWindowData(data) {
  return data &&
         typeof data.x === 'number' &&
         typeof data.y === 'number' &&
         typeof data.width === 'number' &&
         typeof data.height === 'number';
}
function getRandomColor() {
  return '#' + Math.floor(Math.random()*16777215).toString(16).padStart(6,'0');
}

io.on('connection', (socket) => {
  console.log('Conectado:', socket.id);

  socket.on('disconnect', () => {
    console.log('Desconectado:', socket.id);
    socket.broadcast.emit('peerDisconnected');
  });

  socket.on('win1update', (data) => {
    if (isValidWindowData(data)) {
      data.color = getRandomColor();
      data.pulse = Date.now();
      page1 = data;
      io.emit('getdata', { page: 'page1', data: page1 });
    }
  });

  socket.on('win2update', (data) => {
    if (isValidWindowData(data)) {
      data.color = getRandomColor();
      data.pulse = Date.now();
      page2 = data;
      io.emit('getdata', { page: 'page2', data: page2 });
    }
  });
});

server.listen(port, () => {
  console.log(`Servidor en http://localhost:${port}`);
});
````

PAGE1.JS
````
// page1.js
let myData = { x: window.screenX, y: window.screenY, width: window.innerWidth, height: window.innerHeight, color: '#ff4444', pulse: Date.now() };
let otherData = { x: 0, y: 0, width: 200, height: 200, color: '#44ff44', pulse: 0 };

let socket;
let pulses = [];

function setup() {
  createCanvas(windowWidth, windowHeight);
  socket = io();

  socket.on('connect', () => {
    socket.emit('win1update', myData);
  });

  socket.on('getdata', (res) => {
    if (res.page === 'page2') {
      otherData = res.data;
      pulses.push({ x: otherData.x+otherData.width/2, y: otherData.y+otherData.height/2, start: millis(), color: otherData.color });
    }
  });
}

function draw() {
  background(30);

  // bolita propia
  fill(myData.color);
  ellipse(myData.x + myData.width/2, myData.y + myData.height/2, 100, 100);

  // bolita de la otra ventana
  fill(otherData.color);
  ellipse(otherData.x + otherData.width/2, otherData.y + otherData.height/2, 100, 100);

  // línea entre ambas
  stroke(255);
  line(myData.x + myData.width/2, myData.y + myData.height/2,
       otherData.x + otherData.width/2, otherData.y + otherData.height/2);

  drawPulses();
  checkWindowChange();
}

function checkWindowChange() {
  let newData = { x: window.screenX, y: window.screenY, width: window.innerWidth, height: window.innerHeight };
  if (newData.x !== myData.x || newData.y !== myData.y || newData.width !== myData.width || newData.height !== myData.height) {
    myData = { ...newData, color: getRandomColor(), pulse: Date.now() };
    socket.emit('win1update', myData);
    pulses.push({ x: myData.x+myData.width/2, y: myData.y+myData.height/2, start: millis(), color: myData.color });
  }
}

function drawPulses() {
  for (let i = pulses.length-1; i>=0; i--) {
    let p = pulses[i];
    let age = millis()-p.start;
    if (age > 1000) { pulses.splice(i,1); continue; }
    let r = map(age,0,1000,0,200);
    let alpha = map(age,0,1000,150,0);
    push();
    let c = color(p.color);
    stroke(red(c), green(c), blue(c), alpha);
    noFill();
    ellipse(p.x, p.y, r, r);
    pop();
  }
}

function windowResized(){ resizeCanvas(windowWidth, windowHeight); }
function getRandomColor(){ return '#' + Math.floor(Math.random()*16777215).toString(16).padStart(6,'0'); }
````

PAGE2.JS
````
// page2.js
let myData = { x: window.screenX, y: window.screenY, width: window.innerWidth, height: window.innerHeight, color: '#44ff44', pulse: Date.now() };
let otherData = { x: 0, y: 0, width: 200, height: 200, color: '#ff4444', pulse: 0 };

let socket;
let pulses = [];

function setup() {
  createCanvas(windowWidth, windowHeight);
  socket = io();

  socket.on('connect', () => {
    socket.emit('win2update', myData);
  });

  socket.on('getdata', (res) => {
    if (res.page === 'page1') {
      otherData = res.data;
      pulses.push({ x: otherData.x+otherData.width/2, y: otherData.y+otherData.height/2, start: millis(), color: otherData.color });
    }
  });
}

function draw() {
  background(30);

  fill(myData.color);
  ellipse(myData.x + myData.width/2, myData.y + myData.height/2, 100, 100);

  fill(otherData.color);
  ellipse(otherData.x + otherData.width/2, otherData.y + otherData.height/2, 100, 100);

  stroke(255);
  line(myData.x + myData.width/2, myData.y + myData.height/2,
       otherData.x + otherData.width/2, otherData.y + otherData.height/2);

  drawPulses();
  checkWindowChange();
}

function checkWindowChange() {
  let newData = { x: window.screenX, y: window.screenY, width: window.innerWidth, height: window.innerHeight };
  if (newData.x !== myData.x || newData.y !== myData.y || newData.width !== myData.width || newData.height !== myData.height) {
    myData = { ...newData, color: getRandomColor(), pulse: Date.now() };
    socket.emit('win2update', myData);
    pulses.push({ x: myData.x+myData.width/2, y: myData.y+myData.height/2, start: millis(), color: myData.color });
  }
}

function drawPulses() {
  for (let i = pulses.length-1; i>=0; i--) {
    let p = pulses[i];
    let age = millis()-p.start;
    if (age > 1000) { pulses.splice(i,1); continue; }
    let r = map(age,0,1000,0,200);
    let alpha = map(age,0,1000,150,0);
    push();
    let c = color(p.color);
    stroke(red(c), green(c), blue(c), alpha);
    noFill();
    ellipse(p.x, p.y, r, r);
    pop();
  }
}

function windowResized(){ resizeCanvas(windowWidth, windowHeight); }
function getRandomColor(){ return '#' + Math.floor(Math.random()*16777215).toString(16).padStart(6,'0'); }
````


