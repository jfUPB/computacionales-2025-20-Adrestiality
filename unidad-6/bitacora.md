## 🐔 **ACTIVIDAD 01** 🐔

-  🦢 **¿Cómo puedes interactuar con la aplicación? Menciona específicamente las teclas y qué efecto parecen tener sobre las partículas.**

> La interacción del usuario con el programa se lmita al uso de las teclas EN MINUSCULAS y la ubicación del mouse. Las teclas son las siguientes:
>
> **'s'** congela el frame actual de las particulas, por lo que todo queda estático
> **'a'** atrae las particulas hacia la ubicación del mouse. El mouse puede guiarlas ya que siempre se van a mover hacia su ubicación actual
> **'r'** repele y aleja las particulas con respecto la unicación del mouse. Tambien aqui dependiendo de la ubicación del mouse se repelan las partículas dejando un trazo vacío
> **'n'** vuelve a dejar a las particulas en su comportamiento original. moviendose a lugares aleatorios hasta que se presiona alguna de las teclas

- 🦷 **¿Observas los diferentes tipos de “partículas”? ¿Se comportan todas igual inicialmente?**
>
> Parecen haber 3 tipos de particulas, las cuales se diferencian por color (rojo, verde azul) y tamaño (las rojas son las mas pequeñas, las verdes son las medianas, las azules son las mas grandes) pero de resto todas parecen comportarse igual. es como si fuesen convocadas al mismo comportamiento pese a ser distintas. Como un polimorfismo... No obstante en velocidad, no se si es impresion mia pero creo que las particulas rojas se mueen mas rapido

- 🐻‍❄️ **Toma algunas capturas de pantalla de la aplicación en diferentes momentos (estado inicial, después de presionar ‘a’, ‘r’, ‘s’, ‘n’) y añádelas a tu bitácora.**
>
> ESTADO INICIAL:
> <img width="1027" height="774" alt="image" src="https://github.com/user-attachments/assets/9377ccd7-c3cb-4b40-ad23-2f64f37d13d1" />
> <img width="1023" height="770" alt="image" src="https://github.com/user-attachments/assets/238fc819-869c-4e48-a651-8fc3f49dfc8d" />
>
> ESTADO S:
> <img width="1024" height="766" alt="image" src="https://github.com/user-attachments/assets/7fe82dfb-6d69-4392-ae30-32c07819f825" />
>
> ESTADO A:
> <img width="1016" height="756" alt="image" src="https://github.com/user-attachments/assets/b2b1db8a-dabf-4acc-9a0c-28ce2f376839" />
>
> ESTADO R:
> <img width="1025" height="753" alt="image" src="https://github.com/user-attachments/assets/22d7db16-48db-470d-98c2-3c9c5adefd2c" />
>
> ESTADO N:
> <img width="1004" height="763" alt="image" src="https://github.com/user-attachments/assets/86de9ca2-38e8-42ed-8b77-a2de0515e4fb" />

- 🐰 **¿Qué crees que está pasando “detrás de cámaras” cuando presionas las teclas? Formula una hipótesis inicial sobre cómo la aplicación cambia el comportamiento de las partículas.**
>
> Dentro del codigo hya algo llamado notify, que convoca a las particulas cuando hay cambios de estado

## 🐺 **ACTIVIDAD 02** 🐺
🦝🐩🦏🪽🛒📻🔩🔬️

- 🦝 **Explica con tus propias palabras el propósito del patrón Observer. ¿Qué problema resuelve?** 🦝
>
> Lo que hacemos aquí es hacer que cada una de las partículas se suscriba a un super mega plan que les notifica cada vez que debe haber un cambio en el comportamiento y cada partícula decide como reaccionar
>
> El subject no tiene que saber que hace cada observador, cada suscriptor, simplemente emite el mensaje y genera un efecto
>
> en palabras aun mas cristianas, es como cuando te llega la alerta de sismos de google, google solo emite la advertencia, tu ya decides como sales de la casa por la emergencia

- 🦾 **Dibuja un diagrama que muestre la relación entre Subject, Observer, ofApp y Particle en el caso de estudio, indicando quién es el Sujeto y quiénes los Observadores.**

> <img width="1630" height="617" alt="image" src="https://github.com/user-attachments/assets/0ea80b34-4716-4958-817e-701f6e12f6d2" />

- 🦿 **Construye un diagrama de secuencia que muestre cómo funciona el patrón Observer al presionar una tecla**

> <img width="1455" height="349" alt="image" src="https://github.com/user-attachments/assets/22555d55-a7ed-4d1d-9ea2-6220bcda6c59" />

- 🔧 **¿Qué ventajas crees que ofrece usar el patrón Observer en esta aplicación en comparación con, por ejemplo, que ofApp::update recorriera todas las partículas y les dijera directamente que cambien su comportamiento basado en una variable global? Piensa en términos de acoplamiento y extensibilidad.**
>
> Lo primero que pienso es que si usaramos ofApp::update tendriamos que estar cambiando constantemente el codigo por nueva particula que querramos agregar. Ademas de que tandria que saber los comportamientos de cada particula. Diferente de este nuevo patron, que solamente manda mensajes si necesidad de saber que hace cada cosa y es muy facil de reutilizar porque no hay que estarlo actulizando con cada cosa nueva que se haga


