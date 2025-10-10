
# Evidencias de la unidad 7 

## 🐙**ACTIVIDAD 01**

- 🦀 **¿Qué URL de Dev Tunnels obtuviste? ¿Por qué crees que necesitamos usar esta URL en lugar de http://localhost:3000 o la IP local de tu computador para que el celular se conecte?**
>
> En mi caso, obtuve "https://6k3bhnfz-3000.use2.devtunnels.ms/", y para celulares era "https://6k3bhnfz-3000.use2.devtunnels.ms/mobile/"
>
> Necesitamos Crear un servidor propio mas alla de las limitaciones del dispositivo que nos permita concetar varios dispositivos a la vez

- 🦀 **Describe brevemente qué hace npm install y npm start.**
>
> El npm instal, se encarga de descargar e instalar en el programa las dependencias y bibliotecas para que funcione correctamente; mientras que el npm start se encarga de iniciar y darle vida al servidor


- 🦀 **¿Qué mensajes observaste en la terminal del servidor al conectar el cliente de escritorio y el cliente móvil? ¿Eran diferentes los mensajes o identificadores?**

```
Server is listening on http://localhost:3000
New client connected
New client connected
Received message => { type: 'touch', x: 210.19798278808594, y: 243.05540466308594 }
Received message => { type: 'touch', x: 195.4116668701172, y: 202.67222595214844 }
Received message => { type: 'touch', x: 194.2127685546875, y: 195.4752197265625 }
```
> Los mensaje que me proporciona la terminal son similares a los que tenia en la unidad pasada con las ventanas y los circulos. Nos dice que los clientes estan conectados y que todo funciona bien, no obstante se diferencian en que las coordenadas que vemos no son posiciones de ventana, sino las coordenadas de la ubicacion nueva de la bolita a medida que la movemos con el touch

- 🦀 **Describe el comportamiento observado: ¿Funcionó la interacción? ¿Hubo algún retraso (latencia)?**
>
> La interacción fue exitosa. En el celular teniamos un recuadro gris que nos pedia que deslizaramos el dedo en el y al hacerlo la bolita en el comptador se movia de manera correspondiente. Genuinamente no soy muy conciente de muchas latencia que digamos, simplmente se demoraba un poquitito en recibir nuevamente coordenadas recien abierto el servidor o cuando quitaba mi dedo un rato y lo volvia a poner para deslizar

## 🐙**ACTIVIDAD 02**

- 🦀 **Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?**
>
> Como la propia palabra lo dice, es una especie de tunel, punte o ""mensajero"" que se encarga de pasar la informacion de manera segura desde un cliente A a un cliente B. Es necesario gracias a la seguridad que proporciona, ya que estamos generando un servidor en la interperie de la red, por lo que Dev Tunnels es nuestro tunel seguro para pasar y extraer informacion  de los clientes

- 🦀 **Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.**
>
> TOUCHMOVED: Es la función que se encarga de recibir las coordenadas de cada movimieno nuevo que se genera. Podria decirse que es la funcion más importante de todo el programa con respecto a la interactividad
>
> THRESHOLD: Es la funion que limita las coordenadas del TouchMoved. Es decir, es la que se encarga de establecer ciertos rangos de valores o limites que le permiten identificar a touchMoved cuando las nuevas coordenadas son muy similares y significan un simle tambaleo del usuario y cuando definitivamente la nueva coordenada implica un nuevo movimiento relevante a mostrar

- 🦀 **Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?**
>
> Usar una conección con la Ip local de los dispositivos tiene la gran limitación de estar conectados obligatoriamente a la misma red, por lo que usar datos ni siquiera es opcion aqui. Mientras que dev tunnels establece una conección entre los clientes en medio de la interperie del internet pero de manera segura bajo la condicion de ambos dispositivos esten conectados a internet

>- 🦀 **Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).**
>
> ![Imagen de WhatsApp 2025-10-09 a las 17 35 06_92d4ac39](https://github.com/user-attachments/assets/89bce61f-f9cf-4190-b2b9-bc38ab0a73f8)
> <img width="1331" height="535" alt="image" src="https://github.com/user-attachments/assets/18401f1c-1a0e-41bb-8497-5d992fc9d583" />
> <img width="404" height="551" alt="image" src="https://github.com/user-attachments/assets/eb2684a0-996e-4c6b-be20-7be5a34058b0" />

## 🐙**ACTIVIDAD 03**

- 🦀 **¿Cuál es la función principal de express.static(‘public’) en este servidor? ¿Cómo se compara con el uso de app.get(‘/ruta’, …) del servidor de la Unidad 6?**
> 
> App.get es la funcion que en la unidad anterior nos proporcionaba una ruta especifica para que los clientes se cconectaran y tuviesen sus propior archivos estáticos, mientras que express.static nos proporciona todo en un solo lugar. Si ingresamos el github que clonamos inicialmente, encontraremos la carpeta public la cual esta llamada en la funcion

- 🦀 **Explica detalladamente el flujo de un mensaje táctil: ¿Qué evento lo envía desde el móvil? ¿Qué evento lo recibe el servidor? ¿Qué hace el servidor con él? ¿Qué evento lo envía el servidor al escritorio? ¿Por qué se usa socket.broadcast.emit en lugar de io.emit o socket.emit en este caso?**
>
> EVENTO QUE ENVIA DESDE EL MOVIL: TouchMoved
>
> EVENTO QUE LO RECIVE EN EL SERVIDOR: socket.on
>
> QUE HACE EL SERVIDOR CON EL: socket.broadcast
>
> Se debe usar socket.broadcast ya que es lo que nos permite una conexión continua con los datos, es como una conección en vivo. Si la cambiamos, los clientes ni siquiera sabrian que se desconectaron, por lo que seguirian funcionando

- 🦀 **Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ¿Quién recibiría el mensaje retransmitido por el servidor? ¿Por qué?**
>
> Originalmente pense en que si yo abria otropc son el enlace que tenía el dispositivo con el servidor (es decir, el enlace sin /mobile/) podria acceder, al menos visualmente, a las cosas que el dispositivo con el servidor podia tener.
>
> Pero oh sorpresa, cuando pegue el enlace salía un ERROR y la pantalla en balnco... Por lo que solo dejaba dos opciones (en realidad una) Instala todas las cosas necesarias para tambien abrir el servidor desde este segundo pc o cambiar el enlace añadiendo la extensión mobile
> La primera opcion no era posible, pues no es posible "crear y acceder" a un servidor, es decir, no puedo crear dos servidores iguales y acceder a la informacio de sus clientes. Por lo que me fui por la segunda opcion del enlace con la extención y WOOOW, tenia la interfaz y opciones del celular en el pc. podia mover la bolita desde ambos lugares casi que a la vez
>
>Pero y entonces, en donde se reflejan los movimientos de la bolita? UNICAMENTE en el dispositivo que tiene el servidor abierto, en este caso, el primer pc...

- 🦀 **¿Qué información útil te proporcionan los mensajes console.log en el servidor durante la ejecución?**
>
> El console.log nos proporciona informacion muy util, como los clientes y su estado (conectados y desconectados) y los mensajes que se estan pasando entre ellos, en este caso, las actualizaciones tipo touch que se etan enviando

## 🐙**ACTIVIDAD 04**

- 🦀 **Realiza un diagrama donde muestres el flujo completo de datos y eventos entre los tres componentes: móvil, servidor y escritorio. Puedes ilustrar con un ejemplo de coordenadas táctiles (x, y) y cómo viajan a través del sistema.**
>
> <img width="867" height="808" alt="000" src="https://github.com/user-attachments/assets/a91d9f89-26d7-43d8-890c-442455504183" />


## 🐙**ACTIVIDAD 05**

000

## 🐙**AUTOEVALUACIÓN**

- 🪸 **MI NOTA PROPUESTA: 00**
- 🪸 **DEFENSA:**

