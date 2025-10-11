# Bitácora de aprendizaje de la unidad 7

## 🌟**ACTIVIDAD 01**🌟

- ✨ **Incluye una captura de pantalla del ejemplo funcionando en tu máquina**
>
> <img width="422" height="455" alt="image" src="https://github.com/user-attachments/assets/72062ea3-f418-4b9a-aa6e-a85c678a02f6" />

- ✨ **Observa el proyecto, trata de entenderlo, pero ten presente que lo analizaremos más adelante**
>
> Viendo por encima el código tengo la certeza de decir que no entiendo casi nada, hay muchas palabras que ni siquiera se que significan ni para que existen dentro del código

- ✨ **¿Qué preguntas te surgen al ver el código?. Anota al menos tres preguntas que te gustaría investigar más adelante (no te preocupes que la idea de esta unidad es que las resuelvas)**
>
> En realidad son muchas preguntgas, dado a que no entiendo la gran mayoria de terminos que hay.. No se que es VAO, VBO; shaderProg..
>
> Ni siquiera entiendo si unsigned es un tipo de variable porque jamas la habia escuchado.
>
> La clase buildShaderProgram tambien se ve algo extraña y no entiendo su funcionalidad, medianamente ceo que llama algunos shaders o los crea, pero no estoy segura
>
> En la clase setupTriangle crea los vertices del tiangulo que vemos, pero no se que son las variables de abajo
>
> Y en el main, creo que tampoco entiendo nada de alli...
>
> En realidad creo que mi pregunta sera... "¿Como funciona este código?"

## 🌟**ACTIVIDAD 02**🌟

- ✨ **En tu resumen debes tratar de conectar GLFW, opengl32.lib, GLAD, GLM y los drivers de la GPU. ¿Qué rol cumple cada uno? ¿Cómo se relacionan entre sí?**
>
> Para poder crear un proyecto en OpenGL es necesario agregar elementos externos, lo cuales son las dependencias del proyecto. Entre estas hay dos librerías que son fundamentales para OpenGL las cuales son GLFW y GLAD, además en este caso también se descargo una biblioteca llamada GLM (ya voy a explicar estas tres). Para incluirlas simplemente hay que agregar una carpeta dentro de el proyecto, la cual va a contener subcarpetas con la información descargada.
>
> **GLFW:**
>
> Biblioteca multiplataforma que que permite crear las ventanas y eventos de entrada, tales como las del teclado o mouse
>
> **Opengl32.lib:**
>
> Es una biblioteca incluida en Windows que permite iniciar cualquier programa en opengl
>
> **GLAD:**
>
> Biblioteca con funciones de openGL y permite acceder a ellas en tiempo de ejecución
>
> **GML:**
>
> Biblioteca matemática para gráficos vectoriales, matrices y transformaciones que consiste en un solo código fuente
>
> **Drivers GPU:**
>
> Software que sirve como puente entre el sistema operativo y las aplicaciones se comuniquen con la tarjeta gráfica de la computadora

## 🌟**ACTIVIDAD 03**🌟

**═∘◦✧◦∘═ 🔅PARTE 1🔅 ═∘◦✧◦∘═**

- ✨ **Cambia los valores de bufferWidth y bufferHeight: divide por 2, por 4, multiplica por 2, por 4, etc. ¿Qué pasa? ¿Qué observas? ¿Qué crees que está pasando?**
>
> Cuando dividimos por 2 pasa esto:
>
> <img width="416" height="449" alt="image" src="https://github.com/user-attachments/assets/c4c3e980-a5bb-44ee-a2c7-cb91aa109132" />
>
> Cuando dividimos por 4 pasa esto:
>
> <img width="425" height="455" alt="image" src="https://github.com/user-attachments/assets/f1cdc4b9-ebc6-4783-bc2c-af33f21cf898" />
>
> Cuando multiplicamos por 2 pasa esto:
>
> <img width="394" height="432" alt="image" src="https://github.com/user-attachments/assets/f1916f0e-c7eb-4809-8be8-7847a1ec7c50" />

>
> Cuando multiplicamos por 4 pasa esto: (Aunque se ve muy igual a la anterior)
>
> <img width="404" height="434" alt="image" src="https://github.com/user-attachments/assets/652fbb4e-97f1-48ff-b14c-40bf58487acd" />
>
> Aquí es donde vemos reflejada la relacion entre la ventana y el framebuffer...
> El framebuffer es la hoja original en donde dibujamos con la gpu, y la ventana es una especie de proyección. La línea que modificamos es respecto al tamaño del buffer, y claro, se distorsiona lo que vemos en la proyección de la ventana 

- ✨ **Entonces hagamos “digestión”: en tu bitácora, escribe un resumen de lo que has aprendido hasta ahora y piensa en un experimento del tipo ¿Qué pasaría si?**
>
> Perfecto, hagamos un resumen
>
> Hasta ahora en este punto hemos visto que para poder iniciar algo en OpenGL necesitamos ciertas dependencia que contienen bibliotecas necesarias para poder crear no solo los contextos para poder dibujar, sino tambien para la creacion de las ventanas y eventos con este. Adicionalmente ahora tenemos el concepto muy interesante del framebuffer y la ventana. El frameBuffer es un lienzo imaginario donde la GPU dibuja tras recibir las instrucciones de OpenGL, y este lienzo se proyecta en la ventana que creamos
>
> Ahora, hagamos un experimento
>
> Hace un momento modificamos el FrameBuffer, pero, ¿Qué tal si modificamos la ventana?
>
> para ello, puse la cambié línea:
```
const unsigned int SCR_WIDTH = 400;
const unsigned int SCR_HEIGHT = 400;
```
```
const unsigned int SCR_WIDTH = 300;
const unsigned int SCR_HEIGHT = 250;
````
> sucede esto
> 
> <img width="249" height="437" alt="image" src="https://github.com/user-attachments/assets/a8092944-7c76-4374-b141-c1eb3e94d9c3" />
>
> Tambien se distorciona la imagen

- ✨ **¿Qué pasa si cambias el primer parámetro de glDrawArrays a GL_LINES? ¿Qué pasa si lo cambias a GL_POINTS? ¿Qué pasa si cambias el tercer parámetro a 2? ¿Qué pasa si lo cambias a 4?**
>
> Si cambiamos la línea a GL_LINES pasa esto:
>
> <img width="398" height="430" alt="image" src="https://github.com/user-attachments/assets/992be936-d779-4cd6-9c4a-cec07de0b6bf" />
>
> Si cambimos la líena a GL_POINTS pasa esto: (son puntitos super pequeñitos)
>
><img width="404" height="432" alt="image" src="https://github.com/user-attachments/assets/60080083-a0d6-4071-9c04-e41bceb8770c" />
>
> Si cambiamos a 2 pasa esto: (No hay nada)
>
> <img width="459" height="511" alt="image" src="https://github.com/user-attachments/assets/20ecb1c7-7dfd-4795-b6a9-ec2049b6ba7e" />
>
> Si cambiamos a 4 pasa esto: (aparece el mismo triangulo)
>
><img width="405" height="433" alt="image" src="https://github.com/user-attachments/assets/a14469c2-9b9f-4fc9-b5ee-21dc707371eb" />
>
> Parece que la funcion triangulo solo funciona bien si se le dan los parametros correctos. si le ponemos dos vertices no se crea, si le damos 4 se crea uno normal ignorando el cuarto vertice
>
> La funcion línea parece funcionar con minimo 2 vertices, por lo que tambien creo que ignora el excedente de dichos vertices
>
> De resto, la funcion punto parece que si funciona con cualquier cantidad de vertice... solo que seria genial hacerlos mas grandes


- ✨ **¿Qué es el contexto OpenGL?**
>
> Es una estructura de datos que contiene los recursos y la conexión de ventana donde se dibujarán los gráficos

- ✨ **¿Cuál es el rol de la biblioteca GLFW y qué ventaja tiene usarla?**
>
> Es la que nos permite crear las ventanas y recibir sus eventos, así como también eventos de entrada.
> Se encarga de los datos como el tamaño de la ventana o si pulsamos la tecla Esc para cerrarla
>
> La ventaja de utilizar esa biblioteca es que nos permite reutilizar código para no tener que diseñar el uso de las ventanas en cada programa

- ✨ **¿Por qué crees que OpenGL necesita un contexto (recuerda la analogía del taller de arte)?**
>
> El contexto le otorga las herramientas a OpenGL para que haga las cosas que queremos que haga
>
> Un artista no puede pintar si no tiene si quiera un espacio donde hacerlo y mucho menos si no tiene sus herramientas 
Eso es lo que nos otorga el contexto

- ✨ **¿En últimas qué será el framebuffer y a qué te recuerda de las dos primeras unidades del curso?**
>
> El frameBuffer es el área sobre el cual open gl (en realidad es la GPU bajo las órdenes de openGL) dibuja lo que pedimos. El cual se ajusta a la ventana que creamos
>
> En relación con las primeras unidades del curso, el framebuffer también contiene direcciones de memoria de lo que se debe ver en pantalla y así mismo almacenando su información (como el color por ejemplo)

- ✨ **¿Qué relación entre en el viewport y el framebuffer?**
>
> El framebuffer contiene la información del dibujo realizado, el viewport es la ventana que proyecta el dibujo

- ✨ **¿En todo la analizado hasta ahora qué rol juega los drivers de la GPU y la GPU misma?**
>
> Los drivers de la GPU son un conjunto de programas que permiten a las aplicaciones comunicarse con la GPU. Mientras que la GPU es la encargada de procesar la creación de dicha imágenes. Para este caso en Open GL lo que ocurre es que por medio de esta API se utilizan los drivers de la GPU y estos traducen el lenguaje que usemos (en este caso c++) para que sea ejecutable para la GPU

- ✨ **¿Por qué crees que sea necesario activar el VSync? ¿Si no lo activas y la imagen es estática qué crees que pase, y si es dinámica?**
>
> El VSync se encarga de limitar el refresco de la ventana al mismo refresco del monitor. Es decir, sincroniza ambos procesos de refresco para evitar que haga tearing y que tenga un movimiento natural 
>
> Por ejemplo en este caso, sin esta parte del código supongo que no se actualizaría correctamente en caso de cambiar el tamaño del viewport

- ✨ **En esta unidad estamos usando OpenGL moderno, pero ¿Qué es OpenGL Legacy? ¿Qué diferencias hay entre ambos?**
>
> OpenGL legacy es una implementación antigua del OpenGL que utiliza pipelines (entradas secuenciales donde la salida de una etapa, es la entrada de la siguiente) de funciones fijas en lugar de Shaders programables 
>
> Su diferencia principal con el moderno es que los Shaders son programables en el moderno, ofreciendo también los buffers de vértices para otorgar más control

- ✨ **¿Qué es el shader program? ¿Por qué es importante en OpenGL moderno?**
>
> Un programa shader es un programa que se ejecuta en la GPU para controlar la apariencia visual de lo que se dibuja (siendo fundamental para iluminación, texturas y sombras, lo que recuerda a programas de diseño grafico), es importante ya que reemplazó los pipelines fijos por unos programables, cediendo más control

- ✨ **Trata de revisar el código setupTriangle(), intuitivamente ¿Qué crees que hace? ¿Qué crees que es el VAO y el VBO?**
>
> setupTriangle lo que configura los datos del triángulo (como los vértices) y los manda a la GPU, definiendo como se va a ver en pantalla 
>
>El VAO es un objeto que encapsula todos los estados de los buffers y atributos de vértices para crear el triángulo
>
> El VBO se trata de un espacio en la memoria de la GPU en donde está la información de los vértices sobre las figuras que se van a proyectar en la pantalla. Es decir eso es lo que define si lo que vemos es 3D o 2D. Por ejemplo aquí se aplica si uno lo ve como el encargado de los vértices del triángulo.

- ✨ **Será necesario seguirlo haciendo en cada loop? Si no es necesario ¿En qué casos crees que esto puede ser útil?**
>
> Lo más probable es que no se tenga que estar llamando constantemente, ya que siempre es la misma figura: un triángulo, independientemente de cuanto volteemos el canvas
>
> Adicionalmente , desde antes ya había una función triángulo.
Reforzando la idea de que basta con que los Shaders apliquen una sola vez en este caso de código, ya que el triángulo es siempre el mismo
>
> En un caso en el que esto podría ser útil sería por ejemplo si fuera necesario modificar constantemente las visuales del objeto de queremos crear. Por ejemplo modificar el número de sus vértices o su color

- ✨ **Finalmente, recuerda lo que hace glfwSwapBuffers(mainWindow); ¿Por qué crees que es importante? ¿Qué pasaría si no lo llamas? ¿Cómo explicas lo que pasa si no lo llamas? (experimenta)**
>
> La función se encarga de intercambiar el buffer trasero por el delantero asegurando una imagen fluida 
>
> Si no se llama hipotéticamente deberían suceder parpadeos... Veamos que pasa si quitamos la línea:
>
> 

## 🌟**ACTIVIDAD 04**🌟

**═∘◦✧◦∘═ 🔅PARTE 2🔅 ═∘◦✧◦∘═**

- ✨ **Luego de estudiar las unidades 1 y 2 de este curso y ver el video, escribe con tus propias palabras ¿Cuál es la diferencia entre una CPU y una GPU?**
>
> 000

- ✨ **¿Cuáles son los tres pasos claves del pipeline de OpenGL? Explica en tus propias palabras cuál es el objetivo de cada paso**
>
> 00

- ✨ **La gran novedad que introduce OpenGL moderno es el pipeline programable. ¿Qué significa esto? ¿Qué diferencia hay entre el pipeline fijo y el programable? ¿Qué ventajas le ves a esto? y si el pipeline es programable, ¿Qué tengo que programar?**
>
> 00

- ✨ **Si fueras a describir el proceso de rasterización ¿Qué dirías?**
>
> 00

- ✨ **¿Qué son los fragmentos? ¿Es lo mismo un fragmento que un pixel? ¿Por qué?**
>
> 00

- ✨ **Explica qué problema resuelve el Z-buffer y ¿Qué es el depth test?**
>
> 00

- ✨ **¿Por qué se presenta el problema de la aliasing? ¿Qué es el anti-aliasing?**
>
> 00

- ✨ **¿Qué relación hay entre la iluminación y el fragment shader? Siempre es necesario tener en cuenta la iluminación en un fragment shader? o puedo hacer un fragment shader sin iluminación? Explica que implicaciones tiene esto**
>
> 00

- ✨ **¿Qué implica para la GPU que una aplicación tenga múltiples fuentes de iluminación?**
>
> 00

- ✨ **Implementa el código anterior en tu máquina y captura pantalla del resultado. Pero antes de hacerlo trata de predecir qué va a pasar.**
>
> 00

## 🌟**ACTIVIDAD 05**🌟

- ✨ **Modifica el código del triángulo para que sea interactivo.**
>
> 00

- ✨ **Incluye una captura de pantalla del triángulo interactivo funcionando en tu máquina.**
>
> 00

- ✨ **Explica el proceso de normalización de las coordenadas del mouse y cómo se relaciona con el sistema de coordenadas de OpenGL.**
>
> 00

- ✨ **Explica el proceso de normalización a coordenadas de dispositivo (NDC) y cómo se relaciona con el sistema de coordenadas de OpenGL.**
>
> 00

## 🌟**ACTIVIDAD 06**🌟

- ✨ **Describe brevemente los cambios que realizaste en el código C++ (dónde obtienes el tiempo, cómo y dónde actualizas el uniform)**
>
> 00

- ✨ **Pega el código modificado de tu fragment shader**
>
> 00

- ✨ **Explica cómo usaste la función de tiempo (sin, cos, u otra) para lograr el efecto de cambio de color cíclico. ¿Qué rango de valores produce tu cálculo y cómo afecta eso al color final?**
>
> 00

- ✨ **Incluye una captura de pantalla o UN ENLACE a un video mostrando el resultado del triángulo con color cambiante**
>
> 00

- ✨ **Reflexión: ¿Qué otros efectos visuales simples podrías lograr usando el tiempo como uniform? Piensa en la posición, el tamaño o la rotación (aunque no hemos visto rotaciones formalmente, ¡intuitivamente podrías intentarlo!). Anota al menos una idea.**
>
> 00

## 🌟**AUTOEVALUACIÓN**🌟

- ✨ **MI NOTA PROPUESTA:0.0**
- ✨ **DEFENSA:**

