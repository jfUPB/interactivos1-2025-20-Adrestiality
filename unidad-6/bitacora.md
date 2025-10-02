 
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

<a name="evidencia1"></a>
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

<a name="evidencia2"></a>
- **Piensa en una página web simple, como un formulario de login**
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

- **Compara el bucle draw() de p5.js con este modelo de “esperar a que algo pase y reaccionar”**
>
> - ¿Qué ventajas crees que tiene el modelo basado en eventos para una interfaz de usuario web?
>
> Este modelo es mas facil de digerir para cualquier coa que lo este ejecutando. las paginas web casi siempre van a atener un numero limitado de interacciones, por lo que es mas facil dejar en el codigo literalmente un manual de acciones para cada accion diferente que creemos que va a hacer
>
> - ¿Sería eficiente tener un bucle draw() redibujando toda la página 60 veces por segundo si nada ha cambiado?
> 
> No, por supuesto que no. Es un sobreesfuerzo estupido el estar recargando una y otra vez cuando los cambios finalmentre se van a dar una vez un usuario presione una tecla o le de click algo

- **¿Por qué crees que podría ser útil usar JavaScript tanto en el cliente (navegador) como en el servidor? ¿Se te ocurre alguna ventaja para los desarrolladores?**
>
> Aqui aun no esoy muy segura. Porque supongo que aqui estamos finjiendo demencia de los otros dos lenguajes que son html y css. Pero en realidad el hecho de que tanto el navegador y el servidor esten hablando en un solo idioma constantemente es un poco mas eficaz a mi parecer

- **Resume con tus propias palabras la diferencia fundamental entre una comunicación HTTP tradicional y una comunicación usando WebSockets/Socket.IO. ¿En qué tipo de aplicaciones has visto o podrías imaginar que se usa esta comunicación en tiempo real?**
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

<a name="evidencia3"></a>
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

<a name="evidencia4"></a>
- **Asegúrate de tener este console.log en page2.js. Abre ambas páginas. Mueve la ventana de page1. Observa la consola del navegador de page2. ¿Qué datos muestra? Mueve la ventana de page2. Observa la consola de page1. ¿Qué pasa? ¿Por qué?**
>
> Las consolas del naegador deben de estra mostrando las coordenadas que estan analizando de la ventana contraria, a la que deben seguir 

- **Observa checkWindowPosition() en page2.js y modifica el código del if para comprobar si el código dentreo de este se ejecuta.Mueve cada ventana y observa las consolas. ¿Qué puedes concluir y por qué?**
>
> para este experimento decidi comentar todo el if a ver que pasaba. lo primero quennote es que ahora el circulo de la pagina 2, la que modificamos, se encontraba completamente pegad al limite, por lo que no se le veia bien si estaba al menos haciendo el ejercicio de apuntar al opuesto. el efecto en la page 1 fue que ya no podia calcular completamente bien la posicion de su opuesto

## **ACTIVIDAD 05**
- **IDEA**
>
> Reconozco que no fui muy creativa aqui. Decidi implementar un degrade automatico entre negro y blanco tomando de referencia las medidas de las ventanas ademas de que dependiendo de la posicion se pudiera variar el color de la bolita entre rojo, verde y azul ( RGB, super creativo)
>
> Implementarla fue muy complejo, ya que todo lo que intentaba y modificaba dañaba cosas o acababa dañando el servidor no se por que. Por lo que me abstuve a solo modificar la funcion draw para el fonso, y para la variacion de colores llame a mi relacion toxica porque no sabia que hacer. A la final este implemento algunas operaciones y variables las cuales le permitian establecer rangos de distancias y a cada una se le asiganaba un color. Aunque tuve que pulir algunas cosas porque este señor tambien me dañaba las conecciones del servidor
>
> A la final quedo algo asi. La sensibilidad del color rojo y azul no es mucha, pero se nota el cambio al menos
>
><a name="evidencia5"></a>
> <img width="1919" height="728" alt="Captura de pantalla 2025-10-02 155837" src="https://github.com/user-attachments/assets/3f091cda-d5bb-4511-9bb0-33291e7b22e4" />
> <img width="887" height="775" alt="Captura de pantalla 2025-10-02 155904" src="https://github.com/user-attachments/assets/f7c9afdc-9516-4623-b230-c229d591d295" />
> <img width="1653" height="734" alt="Captura de pantalla 2025-10-02 155847" src="https://github.com/user-attachments/assets/847056e3-466a-4869-9172-6839ae7ad8f8" />

SERVER.JS
````javascript
//SERVER.JS

const express = require('express');
const http = require('http');
const socketIO = require('socket.io');
const path = require('path');
const app = express();
const server = http.createServer(app); 
const io = socketIO(server); 
const port = 3000;

let page1 = { x: 0, y: 0, width: 100, height: 100 };
let page2 = { x: 0, y: 0, width: 100, height: 100 };
let connectedClients = new Map();
let syncedClients = new Set();

app.use(express.static(path.join(__dirname, 'views')));

app.get('/page1', (req, res) => {
    res.sendFile(path.join(__dirname, 'views', 'page1.html'));
});

app.get('/page2', (req, res) => {
    res.sendFile(path.join(__dirname, 'views', 'page2.html'));
});

io.on('connection', (socket) => {
    console.log('A user connected - ID:', socket.id);
    connectedClients.set(socket.id, { page: null, synced: false });
    
    socket.on('disconnect', () => {
        console.log('User disconnected - ID:', socket.id);
        connectedClients.delete(socket.id);
        syncedClients.delete(socket.id);
        // Notificar a otros clientes que se perdió la sincronización
        socket.broadcast.emit('peerDisconnected');
    });

    socket.on('win1update', (window1, sendid) => {
        console.log('Received win1update from ID:', socket.id, 'Data:', window1);
        if (isValidWindowData(window1)) {
            page1 = window1;
            connectedClients.set(socket.id, { page: 'page1', synced: false });
            socket.broadcast.emit('getdata', { data: page1, from: 'page1' });
            checkAndNotifySyncStatus();
        }
    });

    socket.on('win2update', (window2, sendid) => {
        console.log('Received win2update from ID:', socket.id, 'Data:', window2);
        if (isValidWindowData(window2)) {
            page2 = window2;
            connectedClients.set(socket.id, { page: 'page2', synced: false });
            socket.broadcast.emit('getdata', { data: page2, from: 'page2' });
            checkAndNotifySyncStatus();
        }
    });

    socket.on('requestSync', () => {
        const clientInfo = connectedClients.get(socket.id);
        if (clientInfo?.page === 'page1') {
            socket.emit('getdata', { data: page2, from: 'page2' });
        } else if (clientInfo?.page === 'page2') {
            socket.emit('getdata', { data: page1, from: 'page1' });
        }
    });

    socket.on('confirmSync', () => {
        syncedClients.add(socket.id);
        const clientInfo = connectedClients.get(socket.id);
        if (clientInfo) {
            connectedClients.set(socket.id, { ...clientInfo, synced: true });
        }
        checkAndNotifySyncStatus();
    });    
});

function isValidWindowData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkAndNotifySyncStatus() {
    const page1Clients = Array.from(connectedClients.entries()).filter(([id, info]) => info.page === 'page1');
    const page2Clients = Array.from(connectedClients.entries()).filter(([id, info]) => info.page === 'page2');
    
    const bothPagesConnected = page1Clients.length > 0 && page2Clients.length > 0;
    const allClientsSynced = Array.from(connectedClients.keys()).every(id => syncedClients.has(id));
    const hasMinimumClients = connectedClients.size >= 2;

    console.log(`Debug - Connected clients: ${connectedClients.size}, Page1: ${page1Clients.length}, Page2: ${page2Clients.length}, Synced: ${syncedClients.size}`);

    
    if (bothPagesConnected && allClientsSynced && hasMinimumClients) {
        io.emit('fullySynced', true);
        console.log('All clients are fully synced');
    } else {
        io.emit('fullySynced', false);
        console.log(`Sync status: pages=${bothPagesConnected}, synced=${allClientsSynced}, clients=${connectedClients.size}`);
    }
}

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
});


````

PAGE1.JS
````javascript
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
}

let previousPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
};

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let point1 = [currentPageData.width / 2, currentPageData.height / 2];
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;
let connectionTimeout;

const BG_MAP_MAX_DIST = 1000;
const BG_GRAY_VALUE = 50;
const BG_GRAY_TOLERANCE = 10;
const BG_WHITE_THRESHOLD = 230;
const BG_BLACK_THRESHOLD = 25;

function computeBgOpacity_page1() {
    let distancia = dist(currentPageData.x, currentPageData.y, remotePageData.x, remotePageData.y);
    return map(distancia, 0, BG_MAP_MAX_DIST, 255, 0);
}

function getBallColorFromBg_page1(bg) {
    if (bg <= BG_BLACK_THRESHOLD) return color(0, 255, 0);
    if (abs(bg - BG_GRAY_VALUE) <= BG_GRAY_TOLERANCE) return color(255, 0, 0);
    if (bg >= BG_WHITE_THRESHOLD) return color(0, 0, 255);
    return color(0, 255, 0);
}

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();

    socket.on('connect', () => {
        console.log('Connected with ID:', socket.id);
        isConnected = true;
        socket.emit('win1update', currentPageData, socket.id);
        
        setTimeout(() => {
            socket.emit('requestSync');
        }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            console.log('Received valid remote data:', remotePageData);
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
        console.log('Sync status:', synced ? 'SYNCED' : 'NOT SYNCED');
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Peer disconnected, waiting for reconnection...');
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Disconnected from server');
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    currentPageData = {
        x: window.screenX,
        y: window.screenY,
        width: window.innerWidth,
        height: window.innerHeight
    };

    if (currentPageData.x !== previousPageData.x || currentPageData.y !== previousPageData.y || 
        currentPageData.width !== previousPageData.width || currentPageData.height !== previousPageData.height) {

        point1 = [currentPageData.width / 2, currentPageData.height / 2]
        socket.emit('win1update', currentPageData, socket.id);
        previousPageData = currentPageData;
    }
}


function draw() {
    let bg = computeBgOpacity_page1();
    background(bg);

    if (!isConnected) {
        showStatus('Conectando al servidor...', color(255, 165, 0));
        return;
    }
    
    if (!hasRemoteData) {
        showStatus('Esperando conexión de la otra ventana...', color(255, 165, 0));
        return;
    }
    
    if (!isFullySynced) {
        showStatus('Sincronizando datos...', color(255, 165, 0));
        return;
    }

    let bolaColor = getBallColorFromBg_page1(bg);

    // bolita local
    noStroke();
    fill(bolaColor);
    drawCircle(point1[0], point1[1]);

    checkWindowPosition();
    
    let vector1 = createVector(currentPageData.x, currentPageData.y);
    let vector2 = createVector(remotePageData.x, remotePageData.y);
    let resultingVector = createVector(vector2.x - vector1.x, vector2.y - vector1.y);

    stroke(50);
    strokeWeight(20);
    fill(bolaColor);
    drawCircle(resultingVector.x + remotePageData.width / 2, resultingVector.y + remotePageData.height / 2);
    line(point1[0], point1[1], resultingVector.x + remotePageData.width / 2, resultingVector.y + remotePageData.height / 2);
}

function showStatus(message, statusColor) {
    textSize(24);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 150);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, 1*height / 6, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, 1*height / 6);
}

function drawCircle(x, y) {
    ellipse(x, y, 150, 150);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
}

````

PAGE2.JS
````javascript
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
}

let previousPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
};

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let point2 = [currentPageData.width / 2, currentPageData.height / 2];
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;
let connectionTimeout;

const BG_MAP_MAX_DIST_2 = 1000;
const BG_GRAY_VALUE_2 = 50;
const BG_GRAY_TOLERANCE_2 = 10;
const BG_WHITE_THRESHOLD_2 = 230;
const BG_BLACK_THRESHOLD_2 = 25;

function computeBgOpacity_page2() {
    let distancia = dist(currentPageData.x, currentPageData.y, remotePageData.x, remotePageData.y);
    return map(distancia, 0, BG_MAP_MAX_DIST_2, 255, 0);
}

function getBallColorFromBg_page2(bg) {
    if (bg <= BG_BLACK_THRESHOLD_2) return color(0, 255, 0);
    if (abs(bg - BG_GRAY_VALUE_2) <= BG_GRAY_TOLERANCE_2) return color(255, 0, 0);
    if (bg >= BG_WHITE_THRESHOLD_2) return color(0, 0, 255);
    return color(0, 255, 0);
}

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();

    socket.on('connect', () => {
        console.log('Connected with ID:', socket.id);
        isConnected = true;
        socket.emit('win2update', currentPageData, socket.id);
        
        setTimeout(() => {
            socket.emit('requestSync');
        }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            console.log('Received valid remote data:', remotePageData);
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
        console.log('Sync status:', synced ? 'SYNCED' : 'NOT SYNCED');
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Peer disconnected, waiting for reconnection...');
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
        console.log('Disconnected from server');
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    currentPageData = {
        x: window.screenX,
        y: window.screenY,
        width: window.innerWidth,
        height: window.innerHeight
    };

    if (currentPageData.x !== previousPageData.x || currentPageData.y !== previousPageData.y || 
        currentPageData.width !== previousPageData.width || currentPageData.height !== previousPageData.height) {

        point2 = [currentPageData.width / 2, currentPageData.height / 2]
        socket.emit('win2update', currentPageData, socket.id);
        previousPageData = currentPageData; 
    }
}


function draw() {
    let bg = computeBgOpacity_page2();
    background(bg);
    
    if (!isConnected) {
        showStatus('Conectando al servidor...', color(255, 165, 0));
        return;
    }
    
    if (!hasRemoteData) {
        showStatus('Esperando conexión de la otra ventana...', color(255, 165, 0));
        return;
    }
    
    if (!isFullySynced) {
        showStatus('Sincronizando datos...', color(255, 165, 0));
        return;
    }

    let bolaColor = getBallColorFromBg_page2(bg);

    // bolita local
    noStroke();
    fill(bolaColor);
    drawCircle(point2[0], point2[1]);

    checkWindowPosition();
    
    let vector2 = createVector(remotePageData.x, remotePageData.y);
    let vector1 = createVector(currentPageData.x, currentPageData.y);
    let resultingVector = createVector(vector2.x - vector1.x, vector2.y - vector1.y);
    
    stroke(50);
    strokeWeight(20);
    fill(bolaColor);
    drawCircle(resultingVector.x + remotePageData.width / 2, resultingVector.y + remotePageData.height / 2);
    line(point2[0], point2[1], resultingVector.x + remotePageData.width / 2, resultingVector.y + remotePageData.height / 2);
}

function showStatus(message, statusColor) {
    textSize(24);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 150);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, 1*height / 6, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, 1*height / 6);
}

function drawCircle(x, y) {
    ellipse(x, y, 150, 150);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
}
````

##  **AUTOEVALUACIÓN** 

- **Mi nota propuesta:** 5
- **Justificación:**
>
> El estudiante consigue crear el servidor local dentro de su dispositivo y entender el funcionamiento básico con respecto a la actualización de datos
>
> [evidencia actividad 1](#evidencia1)
>
> El estudiante consigue comprender la analogia del internet como una inmensa carretera y nuestro navegador como nuestro vehiculo en este, ademas de la estructura basica de las paginas de html, css y javascript, asi como tambien la utilidad de las bibliotecs como puente principal para la creacion de servidores con respuesta inmediata
>
> [evidencia actividad 2](#evidencia2)
>
> El estudiante comprende el funcionamiento de la actualizacion de datos mediante el cambio deliverado de ciertos valores que ocasionan fallas en el servidor y como evitarlas
>
> [evidencia actividad 3](#evidencia3)
>
> El estudiante compara entre las consolas que proporciona el explorador web y la ventana de git y el como los datos se actualizan entre ambas para que puedan estra entrelazadas
>
> [evidencia actividad 4](#evidencia4)
>
> El estudiante consigue modificar el codigo base para hacer añadidos interactivos a la aplicacion
>
> [evidencia actividad 5](#evidencia5)



