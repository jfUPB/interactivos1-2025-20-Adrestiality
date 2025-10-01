 
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
