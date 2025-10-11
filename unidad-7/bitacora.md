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

> [!WARNING]
> NOTA: NUNCA EN SUS VIDAS QUITEN ESA LÍNEA SI NO QUIEREN 10 MINUTOS DE ESTRES Y SI NO QUIEREN CONDENAR EL BIENESTAR DE LA BITÁCORA POR NO HABERLE HECHO COMIT ANTES DE DE HACER EL EXPERIMENTO. JAMAAAAAAAAAAS LO HAGAN, JAMAAAAAS

>
> Fue una experiencia horrible. Crei que retirar la línea solo afectaría la mera ventana con el triangulo y el como se actualizaba a medida que agrandabas la ventana.. PERO NO. TODO EL COMPUTADOR ENTRÓ EN CRISIS EXISTENCIAL Y SE PARALIZÓ POR 10 MINUTOS. Ya no recibia los datos del teclado (Como el impr pant para tratar de tomar captura  o el esc cuando trate de cerrar la ventana), mouse iba re lento y le costó mucho tomar los clicks...
>
> En conclusión, si, la funcion glfwSwapBuffers(mainWindow); es la mas importante para el bienestar de todos...
>
> Esta fue la foto que pude tomar ya que las capturas no servían:
>
> ![Imagen de WhatsApp 2025-10-10 a las 23 35 14_f74754b3](https://github.com/user-attachments/assets/f8c721aa-706a-4ac9-8e7d-c2ebd64263d1)

## 🌟**ACTIVIDAD 04**🌟

**═∘◦✧◦∘═ 🔅PARTE 2🔅 ═∘◦✧◦∘═**

- ✨ **Luego de estudiar las unidades 1 y 2 de este curso y ver el video, escribe con tus propias palabras ¿Cuál es la diferencia entre una CPU y una GPU?**
>
> 000

- ✨ **¿Cuáles son los tres pasos claves del pipeline de OpenGL? Explica en tus propias palabras cuál es el objetivo de cada paso**
>
> - Vertex shading
> 
> Se encarga de calcular todo lo necesario en la escena 
Cada uno de los objetivos, sus caras y vértices, al igual que la información de cada una de las caras traducidas en píxeles y aplica los colores en RGB y carga sus texturas 
Además de que para ahorrar recursos, calcula las distancias de cada objeto, de modo en que solo renderiza las cosas que estén al frente y que sean visibles desde la perspectiva de la cámara 
>
> Es decir, calcula todo lo 3D a 2D
>
> - Rasterization
> 
> Se encarga de optimizar al máximo el plano 2D creado por el Vertex shading y aplicarle correctamente los colores, también como asegurarse de que no se hagan las texturas traseras innecesarias que no se vean en ese momento en el modelo
>
> - Fragment shading
> 
> Esta se encarga del cálculo de la posición de las normales (hacia que lado están mirando las caras de la malla de polígonos) para así establecer el rango de color que se debe aplicar. En otras palabras, si la cara en ese contexto en específico debe ir muy claro porque le está dando toda la luz o muy oscuro porque está en las sombras, haciendo escenas mucho más realistas

- ✨ **La gran novedad que introduce OpenGL moderno es el pipeline programable. ¿Qué significa esto? ¿Qué diferencia hay entre el pipeline fijo y el programable? ¿Qué ventajas le ves a esto? y si el pipeline es programable, ¿Qué tengo que programar?**
>
> La novedad del pipeline programable es que ciertas etapas del pipeline de renderizado, que antes estaban fijas y controladas por hardware, ahora se pueden personalizar con los Shaders
>
> La diferencia entre el pipeline fijo y el programable, es que en el fijo sus etapas son predefinidas con un control demasiado limitado. Mientras que con el pipeline programable es que puedes crear Shaders para las estampas más importantes, como la transformación de píxeles y su coloración. Facilitando la creación de gráficos complejos 
> 
> Las ventajas principales están en que ofrecen mayor flexibilidad y rendimiento, volviéndose un estándar de la industria 
>
> Y lo que se debe programar principalmente es el Vertex shader, el Fragment shading y la Rasterization

- ✨ **Si fueras a describir el proceso de rasterización ¿Qué dirías?**
>
> es el encargado de la optimización de los colores y elimina lo innecesario a la vista de la cámara
>
> también divide las imágenes en fragmentos que a su vez están divididos por pixeles

- ✨ **¿Qué son los fragmentos? ¿Es lo mismo un fragmento que un pixel? ¿Por qué?**
>
> No son lo mismo, los fragmentos contienen pixeles
>
> los fragmentos son conjuntos que forman triángulos, estos triángulos dividen cada parte de las imágenes que serán visibles al final, y son estos los que ayudan a optimizar el proceso, ya que en lugar de pensar en billones de pixeles ahora pensamos en millones de fragmentos

- ✨ **Explica qué problema resuelve el Z-buffer y ¿Qué es el depth test?**
>
> El Z-BUFFER es el encargado de la profundidad. Es gracias a este que se identifican cuáles píxeles se encuentran más lejos desde la perspectiva de la cámara, eso es lo que permite que se vean principalmente los elementos más cercanos a la cámara.

- ✨ **¿Por qué se presenta el problema de la aliasing? ¿Qué es el anti-aliasing?**
>
> El Aliaing es un caso en el que las aristas de los fragmentos interceptan a los píxeles por la mitad lo que genera que se vea irregular la forma. Es por esto que existe el anti-aliaing, que divide los píxeles con 16 puntos distintos y dependiendo de cuántos puntos se ven cubiertos será el valor del color que se encuentran en el Pixel.
>
> Es por eso que muchas veces los píxeles las orillas suelen ser más transparentes.

- ✨ **¿Qué relación hay entre la iluminación y el fragment shader? Siempre es necesario tener en cuenta la iluminación en un fragment shader? o puedo hacer un fragment shader sin iluminación? Explica que implicaciones tiene esto**
>
> El Fragment shading es el encargado de calcular el color final de cada píxel basándose en diferentes factores como la iluminación 
>
> No es obligatorio llevar iluminación si lo que se desea es simular colores planos (cosa poco común). De resto es necesario para darle profundidad al objeto 
>
> La principal implicación de no ponerle la luz es que se vea un color plano cutre y también podría afectar a como percibimos las texturas ya que muchas dependen de la posición de la luz para que se vean

- ✨ **¿Qué implica para la GPU que una aplicación tenga múltiples fuentes de iluminación?**
>
> el hecho de que un programa tenga múltiples iluminaciones, requiere de que se generen miles de cálculos instantáneos para poder variar la tonalidad de cada una de las caras que conforman el fragmento de modelo visible a la cámara

- ✨ **Escribe un resumen en tus propias palabras de lo que se necesita para dibujar un triángulo en OpenGL.**
>
> Inicialmente necesitamos los objetos (El VAO, VBO y los Shaders) que están identificados con ID único para mayor practicidad. 
>
> Luego, necesitamos los datos de los vértices que le permite al computador comprender la ubicación exacta de lo que queremos hacer. 
>
> Después necesitamos los buffers que encapsula la información de los vértices y se hace binding. 
>
> También debemos indicar cómo están organizados los datos de los vértices con una función glVertexAttribPointer y un glEnanbleVertexAtribArray para activar sus atributos 
>
> Luego necesitamos el Vertex shader que proceda la posición de cada vértice y un fragment shader que define el color de cada píxel 
>
> Finalmente con glDrawArrays dibujar la figuras, pidiendo que se unan los 3 vértices para crear un triángulo

- ✨ **Escribe un resumen en tus propias palabras de lo que necesitas para poder usar un shader en OpenGL.**
>
> Los shaders son programas que se ejecutan en la GPU y esos procesan los vértices y los fragmentos. Para este ejemplo entonces se crea en el objeto una función que contiene el programa de los shaders. Y a está función se le agrega un ID gracias al celi es que se puede llamar más tarde en otros momentos dentro del programa.
>
> Entonces por este caso primero llamaba el shader de los vértices para verificar los errores, y después decía lo mismo con fragmentos. Eso con la intención de ver primero lo más sencillo y luego ir hacia lo más complejo. 
>
> Cuando te verifique que no hay ningún problema con los shaders simplemente se eliminan porque ya no son necesarios. Es decir, en realidad son una guía sin embargo no se elimina el objeto que contenía la información de los shaders, qué es el encargado de ejecutarlos en la Gpu
>
> Ahora podemos ver cada shader por separado: los de vértices reciben los datos de dos puntos respecto a su posición y lo convierte en un vector con esa información. En ese caso lo podés ver como el componente w lo asigna siempre como un 1 para que todas las coordenadas sean homogéneas. Después de lo que se ve esta como información debe traducirse a la pantalla en el viewport.
>
> Un paso importante en esta parte es establecer una localización para el Buffer de los atributos (o su espacio de memoria) que permite más tarde vincular los vértices al Buffer de vertices
>
> Ahora el shader de los fragmentos, es el encargado del color, que en este caso es un color fijo naranja que se establece con un vector de 4 componentes del RGBA

- ✨ **Implementa el código anterior en tu máquina y captura pantalla del resultado. Pero antes de hacerlo trata de predecir qué va a pasar.**
>
> EXPECTATIVA: dado que ahora vamos a ingresar 3 shaders... espero al menos 3 triángulos? pero no se que más esperar
>
> CÓDIGO:
```
#include <iostream>
#include <glad/glad.h>
#include <GLFW/glfw3.h>

// Callback: ajusta el viewport cuando cambie el tamaño de la ventana
void framebuffer_size_callback(GLFWwindow* window, int width, int height) {
	glViewport(0, 0, width, height);
}

// Procesa entrada simple: cierra con ESC
void processInput(GLFWwindow* window) {
	if (glfwGetKey(window, GLFW_KEY_ESCAPE) == GLFW_PRESS)
		glfwSetWindowShouldClose(window, true);
}

// Tamaño de ventana
const unsigned int SCR_WIDTH = 400;
const unsigned int SCR_HEIGHT = 400;

// --- SHADERS DE VÉRTICE ---

// Shader A: usa posición
const char* vertexShaderSrcA = R"glsl(
    #version 460 core
    layout(location = 0) in vec3 aPos;
    void main() {
        gl_Position = vec4(aPos, 1.0);
    }
)glsl";

// Shader B: usa color como posición “falsa”
const char* vertexShaderSrcB = R"glsl(
    #version 460 core
    layout(location = 1) in vec3 aColor;
    void main() {
        gl_Position = vec4(aColor * 0.5, 1.0);
    }
)glsl";

// Shader C: usa offset
const char* vertexShaderSrcC = R"glsl(
    #version 460 core
    layout(location = 2) in vec2 aOffset;
    void main() {
        gl_Position = vec4(aOffset, 0.0, 1.0);
    }
)glsl";

// Fragment shader (mismo para los tres)
const char* fragmentShaderSrc = R"glsl(
    #version 460 core
    out vec4 FragColor;
    void main() {
        FragColor = vec4(1.0, 0.5, 0.2, 1.0);
    }
)glsl";

// --- IDs globales ---
GLuint VAO, VBO;
GLuint shaderA, shaderB, shaderC;

// Función para compilar un programa shader completo (vertex + fragment)
unsigned int buildShaderProgram(const char* vtxSrc, const char* fragSrc) {
	int success;
	char log[512];

	unsigned int vs = glCreateShader(GL_VERTEX_SHADER);
	glShaderSource(vs, 1, &vtxSrc, nullptr);
	glCompileShader(vs);
	glGetShaderiv(vs, GL_COMPILE_STATUS, &success);
	if (!success) {
		glGetShaderInfoLog(vs, 512, nullptr, log);
		std::cerr << "ERROR VERTEX SHADER:\n" << log << "\n";
	}

	unsigned int fs = glCreateShader(GL_FRAGMENT_SHADER);
	glShaderSource(fs, 1, &fragSrc, nullptr);
	glCompileShader(fs);
	glGetShaderiv(fs, GL_COMPILE_STATUS, &success);
	if (!success) {
		glGetShaderInfoLog(fs, 512, nullptr, log);
		std::cerr << "ERROR FRAGMENT SHADER:\n" << log << "\n";
	}

	unsigned int prog = glCreateProgram();
	glAttachShader(prog, vs);
	glAttachShader(prog, fs);
	glLinkProgram(prog);
	glGetProgramiv(prog, GL_LINK_STATUS, &success);
	if (!success) {
		glGetProgramInfoLog(prog, 512, nullptr, log);
		std::cerr << "ERROR LINKING PROGRAM:\n" << log << "\n";
	}

	glDeleteShader(vs);
	glDeleteShader(fs);
	return prog;
}


void setupBuffers() {
	float vertices[] = {
		//   pos            color           offset
		-1.0f, -1.0f, 0.0f,   0.0f, 0.0f, 0.0f,   0.1f, 0.5f,
		 0.0f, -1.0f, 0.0f,   1.0f, 0.0f, 0.0f,   0.2f, 0.5f,
		-0.5f, -0.5f, 0.0f,   0.5f, 0.5f, 0.0f,   0.15f, 0.75f
	};

	glGenVertexArrays(1, &VAO);
	glGenBuffers(1, &VBO);

	glBindVertexArray(VAO);
	glBindBuffer(GL_ARRAY_BUFFER, VBO);
	glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);

	glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 8 * sizeof(float), (void*)(0));
	glEnableVertexAttribArray(0);

	glVertexAttribPointer(1, 3, GL_FLOAT, GL_FALSE, 8 * sizeof(float), (void*)(3 * sizeof(float)));
	glEnableVertexAttribArray(1);

	glVertexAttribPointer(2, 2, GL_FLOAT, GL_FALSE, 8 * sizeof(float), (void*)(6 * sizeof(float)));
	glEnableVertexAttribArray(2);

	glBindVertexArray(0);
}


int main()
{
	// 1) Inicializar GLFW
	if (!glfwInit()) {
		std::cerr << "Fallo al inicializar GLFW\n";
		return -1;
	}
	glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 4);
	glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 6);
	glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);

	// 2) Crear ventana
	GLFWwindow* mainWindow = glfwCreateWindow(SCR_WIDTH, SCR_HEIGHT, "Tres Shaders", nullptr, nullptr);
	if (!mainWindow) {
		std::cerr << "Error creando ventana\n";
		glfwTerminate();
		return -1;
	}

	glfwMakeContextCurrent(mainWindow);
	glfwSetFramebufferSizeCallback(mainWindow, framebuffer_size_callback);

	// 3) Cargar GLAD
	if (!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)) {
		std::cerr << "Fallo al cargar GLAD\n";
		return -1;
	}

	glfwSwapInterval(1); // V-Sync

	// 4) Compilar los tres programas
	shaderA = buildShaderProgram(vertexShaderSrcA, fragmentShaderSrc);
	shaderB = buildShaderProgram(vertexShaderSrcB, fragmentShaderSrc);
	shaderC = buildShaderProgram(vertexShaderSrcC, fragmentShaderSrc);

	// 5) Configurar buffers
	setupBuffers();

	// 6) Loop principal
	while (!glfwWindowShouldClose(mainWindow))
	{
		processInput(mainWindow);
		glfwPollEvents();

		glClearColor(0.2f, 0.3f, 0.3f, 1.0f);
		glClear(GL_COLOR_BUFFER_BIT);

		glBindVertexArray(VAO);


		glUseProgram(shaderA);
		glEnableVertexAttribArray(0);
		glDisableVertexAttribArray(1);
		glDisableVertexAttribArray(2);
		glDrawArrays(GL_TRIANGLES, 0, 3);


		glUseProgram(shaderB);
		glDisableVertexAttribArray(0);
		glEnableVertexAttribArray(1);
		glDisableVertexAttribArray(2);
		glDrawArrays(GL_TRIANGLES, 0, 3);


		glUseProgram(shaderC);
		glDisableVertexAttribArray(0);
		glDisableVertexAttribArray(1);
		glEnableVertexAttribArray(2);
		glDrawArrays(GL_TRIANGLES, 0, 3);

		glfwSwapBuffers(mainWindow);
	}

	// Limpieza
	glDeleteVertexArrays(1, &VAO);
	glDeleteBuffers(1, &VBO);
	glDeleteProgram(shaderA);
	glDeleteProgram(shaderB);
	glDeleteProgram(shaderC);
	glfwDestroyWindow(mainWindow);
	glfwTerminate();

	return 0;
}
```
> RESULTADO:
>
> <img width="425" height="457" alt="image" src="https://github.com/user-attachments/assets/95fd8a08-3499-48fd-9580-52839a17c887" />

## 🌟**ACTIVIDAD 05**🌟

- ✨ **Modifica el código del triángulo para que sea interactivo.**
>
```c++
#include <iostream>
#include <glad/glad.h>
#include <GLFW/glfw3.h>


// Callback: ajusta el viewport cuando cambie el tamaño de la ventana
void framebuffer_size_callback(GLFWwindow* window, int width, int height) {
	glViewport(0, 0, width, height);
}

// Procesa entrada simple: cierra con ESC
void processInput(GLFWwindow* window) {
	if (glfwGetKey(window, GLFW_KEY_ESCAPE) == GLFW_PRESS)
		glfwSetWindowShouldClose(window, true);
}

// Tamaño de las ventanas
const unsigned int SCR_WIDTH = 400;
const unsigned int SCR_HEIGHT = 400;

// Fuentes de los shaders
const char* vertexShaderSrc = R"glsl(
    #version 460 core

layout(location = 0) in vec3 aPos;
uniform vec2 offset;

void main() {
    vec3 newPos = aPos;
    newPos.x += offset.x;
    newPos.y += offset.y;
    gl_Position = vec4(newPos, 1.0);
}
)glsl";

const char* fragmentShaderSrc = R"glsl(
   #version 460 core

out vec4 FragColor;
uniform vec4 ourColor;

void main() {
    FragColor = ourColor;
}
)glsl";

// IDs globales
unsigned int VAO, VBO;
unsigned int shaderProg;

// Compila y linkea un programa de shaders, retorna su ID
unsigned int buildShaderProgram() {
	int success;
	char log[512];

	unsigned int vs = glCreateShader(GL_VERTEX_SHADER);
	glShaderSource(vs, 1, &vertexShaderSrc, nullptr);
	glCompileShader(vs);
	glGetShaderiv(vs, GL_COMPILE_STATUS, &success);
	if (!success) {
		glGetShaderInfoLog(vs, 512, nullptr, log);
		std::cerr << "ERROR VERTEX SHADER:\n" << log << "\n";
	}

	unsigned int fs = glCreateShader(GL_FRAGMENT_SHADER);
	glShaderSource(fs, 1, &fragmentShaderSrc, nullptr);
	glCompileShader(fs);
	glGetShaderiv(fs, GL_COMPILE_STATUS, &success);
	if (!success) {
		glGetShaderInfoLog(fs, 512, nullptr, log);
		std::cerr << "ERROR FRAGMENT SHADER:\n" << log << "\n";
	}

	unsigned int prog = glCreateProgram();
	glAttachShader(prog, vs);
	glAttachShader(prog, fs);
	glLinkProgram(prog);
	glGetProgramiv(prog, GL_LINK_STATUS, &success);
	if (!success) {
		glGetProgramInfoLog(prog, 512, nullptr, log);
		std::cerr << "ERROR LINKING PROGRAM:\n" << log << "\n";
	}

	glDeleteShader(vs);
	glDeleteShader(fs);
	return prog;
}

// Crea un VAO/VBO con los datos de un triángulo
void setupTriangle() {
	float vertices[] = {
  -0.5f, -0.5f, 0.0f,
   0.5f, -0.5f, 0.0f,
   0.0f,  0.5f, 0.0f
	};
	glGenVertexArrays(1, &VAO);
	glGenBuffers(1, &VBO);

	glBindVertexArray(VAO);
	glBindBuffer(GL_ARRAY_BUFFER, VBO);
	glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);
	glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 3 * sizeof(float), (void*)0);
	glEnableVertexAttribArray(0);
	glBindVertexArray(0);
}


int main()
{
	// 1) Inicializar GLFW
	if (!glfwInit()) {
		std::cerr << "Fallo al inicializar GLFW\n";
		return -1;
	}
	glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 4);
	glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 6);
	glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);

	// 2) Crear ventana
	GLFWwindow* mainWindow = glfwCreateWindow(SCR_WIDTH, SCR_HEIGHT, "Ventana", nullptr, nullptr);
	if (!mainWindow) {
		std::cerr << "Error creando ventana1\n";
		glfwTerminate();
		return -1;
	}

	// 3) Lee el tamaño del framebuffer
	int bufferWidth, bufferHeight;
	glfwGetFramebufferSize(mainWindow, &bufferWidth, &bufferHeight);

	// 4) Callbacks 
	glfwSetFramebufferSizeCallback(mainWindow, framebuffer_size_callback);


	// 5) Cargar GLAD y recursos en contexto de window1
	glfwMakeContextCurrent(mainWindow);

	if (!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)) {
		std::cerr << "Fallo al cargar GLAD (contexto1)\n";
		return -1;
	}

	// 6) Habilita el V-Sync
	glfwSwapInterval(1);

	// 7) Compila y linkea shaders
	shaderProg = buildShaderProgram();

	// 8) Genera el contenido a mostrar
	setupTriangle();

	// 9) Configura el viewport
	glViewport(0, bufferHeight, bufferWidth, bufferHeight);


	// 10) Loop principal
	while (!glfwWindowShouldClose(mainWindow))
	{
		// 11) Manejo de eventos
		glfwPollEvents();


		// 12) Procesa la entrada
		processInput(mainWindow);

		// 13) Configura el color de fondo y limpia el framebuffer
		glClearColor(0.2f, 0.3f, 0.3f, 1.0f);
		glClear(GL_COLOR_BUFFER_BIT);

		// 14) Indica a OpenGL que use el shader program
		glUseProgram(shaderProg);
		int offsetLocation = glGetUniformLocation(shaderProg, "offset");
		int colorLocation = glGetUniformLocation(shaderProg, "ourColor");

		// 15) Activa el VAO y dibuja el triángulo
		// Dibuja el triángulo
		double xpos, ypos;
		glfwGetCursorPos(mainWindow, &xpos, &ypos);

		// Normalizo las coordenadas del mouse
		float x = (float)xpos / (float)SCR_WIDTH;
		x < 0 ? x = 0 : x;
		x > 1 ? x = 1 : x;

		float y = (float)ypos / (float)SCR_HEIGHT;
		y < 0 ? y = 0 : y;
		y > 1 ? y = 1 : y;

		// Envio el color y la posición del triángulo
		float color[] = { x, y, 0.0f, 1.0f };
		glUniform4f(colorLocation, x, y, 0.0f, 1.0f);

		// Envio el offset del triángulo normalizado a NDC
		glUniform2f(offsetLocation, x * 2 - 1, 1 - y * 2);


		glBindVertexArray(VAO);
		glDrawArrays(GL_TRIANGLES, 0, 3);

		// Intercambia buffers y muestra el contenido
		glfwSwapBuffers(mainWindow);
	}

	// 17) Limpieza
	glfwMakeContextCurrent(mainWindow);
	glDeleteVertexArrays(1, &VAO);
	glDeleteBuffers(1, &VBO);
	glDeleteProgram(shaderProg);

	glfwDestroyWindow(mainWindow);
	glfwTerminate();
	return 0;
}
```
- ✨ **Incluye una captura de pantalla del triángulo interactivo funcionando en tu máquina.**
>
> CÓDIGO 1
>
> <img width="399" height="391" alt="Captura de pantalla 2025-10-11 023137" src="https://github.com/user-attachments/assets/17ab73ce-b32b-4afe-a2a1-8368bad312f2" />
> <img width="402" height="432" alt="Captura de pantalla 2025-10-11 023151" src="https://github.com/user-attachments/assets/3fed625e-bd00-445e-80d0-6f5b96c11d1f" />
> <img width="399" height="404" alt="Captura de pantalla 2025-10-11 023143" src="https://github.com/user-attachments/assets/d7446328-7fb9-49ad-9039-7d4e1c990260" />
>

- ✨ **Explica el proceso de normalización de las coordenadas del mouse y cómo se relaciona con el sistema de coordenadas de OpenGL.**
>
> la normalización es un proceso en cual se trasforma la información para entrar en un rango determinado, en este caso entre 0 y 1
>
> se relaciona con las coordenadas ya que permite establecer un limite que no genere un número muy grande y por ende optimiza la información

- ✨ **Explica el proceso de normalización a coordenadas de dispositivo (NDC) y cómo se relaciona con el sistema de coordenadas de OpenGL.**
>
> Es el proceso mediante el cual OpenGL transforma las posiciones de los vértices al rango estándar de -1 a 1 en cada eje (x, y, z) independientemente del tamaño del monitor 
Aquí, x es de izquierda a derecha, y de abajo a arriba y z de cerca a lejos 
>
> Todo lo que queda por fuera de los parámetros se recorta y no se muestra 
> 
> En este código del triángulo, más coordenadas del mouse se convierten a este rango para que el desplazamiento del triángulo sea visible
>
>En otras palabras, OpenGL utiliza el espacio NDC como puente antes de proyectar los vértices en coordenadas reales en pantalla

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

