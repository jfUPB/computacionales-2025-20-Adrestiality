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
> 000

- ✨ **¿Qué es el contexto OpenGL?**
>
> 000

- ✨ **¿Cuál es el rol de la biblioteca GLFW y qué ventaja tiene usarla?**
>
> 000

- ✨ **¿Por qué crees que OpenGL necesita un contexto (recuerda la analogía del taller de arte)?**
>
> 000

- ✨ **¿En últimas qué será el framebuffer y a qué te recuerda de las dos primeras unidades del curso?**
>
> 000

- ✨ **¿Qué relación entre en el viewport y el framebuffer?**
>
> 000

- ✨ **¿En todo la analizado hasta ahora qué rol juega los drivers de la GPU y la GPU misma?**
>
> 000

- ✨ **¿Por qué crees que sea necesario activar el VSync? ¿Si no lo activas y la imagen es estática qué crees que pase, y si es dinámica?**
>
> 000

- ✨ **En esta unidad estamos usando OpenGL moderno, pero ¿Qué es OpenGL Legacy? ¿Qué diferencias hay entre ambos?**
>
> 000

- ✨ **¿Qué es el shader program? ¿Por qué es importante en OpenGL moderno?**
>
> 000

- ✨ **Trata de revisar el código setupTriangle(), intuitivamente ¿Qué crees que hace? ¿Qué crees que es el VAO y el VBO?**
>
> 000

- ✨ **Será necesario seguirlo haciendo en cada loop? Si no es necesario ¿En qué casos crees que esto puede ser útil?**
>
> 000

- ✨ **Finalmente, recuerda lo que hace glfwSwapBuffers(mainWindow); ¿Por qué crees que es importante? ¿Qué pasaría si no lo llamas? ¿Cómo explicas lo que pasa si no lo llamas? (experimenta)**
>
> 000

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

