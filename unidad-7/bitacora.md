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

- ✨ **Necesito que hagas digestión de esta información y que la entiendas. Para ello te voy a pedir un resumen en tus propias palabras de lo que acabas de leer. En tu resumen debes tratar de conectar GLFW, opengl32.lib, GLAD, GLM y los drivers de la GPU. ¿Qué rol cumple cada uno? ¿Cómo se relacionan entre sí? Mira, trata de hacer esto de memoria y como si estuvieras contándole a un amigo que quiere aprender OpenGL. Cuando haces el proceso de memoria tu cerebro hace un esfuerzo adicional y eso te ayuda a aprender. Además, si no recuerdas algo quiere decir que no lo entendiste bien y eso es una buena señal para que vuelvas a leerlo**
>
> 000

## 🌟**ACTIVIDAD 03**🌟

**═∘◦✧◦∘═ 🔅PARTE 1🔅 ═∘◦✧◦∘═**

- ✨ **Qué tal si ensayas. Prueba con esta línea**
>
> 000

- ✨ **¿Qué pasa si?**
>
> 000

- ✨ **Cambia los valores de bufferWidth y bufferHeight: divide por 2, por 4, multiplica por 2, por 4, etc. ¿Qué pasa? ¿Qué observas? ¿Qué crees que está pasando?**
>
> 000

- ✨ **Entonces hagamos “digestión”: en tu bitácora, escribe un resumen de lo que has aprendido hasta ahora y piensa en un experimento del tipo ¿Qué pasaría si?**
>
> 000

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

