# Bitácora de aprendizaje de la unidad 8
## 🦐 ACTIVIDAD 1

- 🐡 **Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?**
>
> <img width="325" height="327" alt="Captura de pantalla 2025-10-26 201635" src="https://github.com/user-attachments/assets/ee3a7b55-bf2b-4745-b387-5a8585db939a" />
> <img width="854" height="518" alt="Captura de pantalla 2025-10-26 201629" src="https://github.com/user-attachments/assets/3c2568f4-156d-45d1-9ccd-4ee928829ee6" />
>
> Por mi parte tuve errores de compilacion. Parece que algo ha pasado con las versiones de openframeworks o visual studio. Por lo que una amiga me estara haciendo el favor de mostrame que esta sucediendo.
>
> La ventana tiene un circulo animado que va de izquierda a derecha, pero se congela deliberadamente cuando hacemos click y deslizamos con el mouse, par luego cambiar de tamaño.
>
> Aquí vemos dos posibles tamaños, el default y uno mas pequeños
>
> El motivo por el cual se congela es debido a la sobrecarga de tareas que hay

- 🐡 **Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?**
>
><a name="evidencia1"></a>
> <img width="786" height="412" alt="Captura de pantalla 2025-10-26 202534" src="https://github.com/user-attachments/assets/73ba70bc-e777-4256-b5dc-9ce2006fe3d8" />
> <img width="826" height="430" alt="Captura de pantalla 2025-10-26 202549" src="https://github.com/user-attachments/assets/a5003dac-d013-41d6-b0c0-c182157dd2c2" />
>
> Aqui en este nuevo codigo lo que hicimos fue crear hilos para las dos tareas diferentes que hay. un hilo se encarga de calcular el tamaño del nuevo circulo y el otro se encarga de mantener la animacion de este. Ya no se congela como antes

- 🐡 **Explica en tus propias palabras ¿Cómo puede presentarse la condición de carrera en este caso? ¿Qué es lo que está pasando? Te pido que propongas un ejemplo.**
>
> - CONCURRENCIA: Esto quiere decir que hay multiples tareas en cadena necesarias para cumplir un onjetivo o las diferentes fases para llegar a una meta. Es como hacer un pastel, primero mezclas los ingredientes, horneas, decoras...
>
> - PARALELISMO: Esto quiere decir que hya multiples tareas separadas que pueden ser realizadas por diferentes "personas" como las partes de un platillo. la preparación de la ensalada, la proteina, las bebidas... son cosas que se hacen por separado, como si fuesen independientes unas de otras
>
> Comprender esta diferencia es importante para estructurar los datos que se deben de calcular en los procesos y hacer cosas mas rapido

## 🦐 ACTIVIDAD 2

- 🐡 **¿En qué partes del código se está protegiendo el acceso a la variable circleSize? ¿Qué ocurre con el rendimiento del programa? ¿Es posible que el rendimiento se vea afectado por el uso de mutex? ¿Por qué?**
>
```
lock();
    ofSeedRandom();
    circleSize = ofRandom(20, 70);
    unlock();
```
> no estoy del todo segura si definitivamente es esta linea. pero lo que parece hacer es bloquear esta informacion del circulo
>
> Para el paralelismo, lo que hace es que las tareas solo puedan acceder y modificar el recurso uno a la vez. evitando asi el desorden y la informacion erronea

- 🐡 **Ejecuta el código y observa el resultado. ¿Qué ocurre si cambias el valor de la variable useLock? ¿Por qué crees que ocurre esto?**
>
> <a name="evidencia2"></a>
> ![Imagen de WhatsApp 2025-10-26 a las 21 17 07_09ebfde2](https://github.com/user-attachments/assets/71dcc35b-a408-4cc2-a3a7-8af03692545e)
> ![Imagen de WhatsApp 2025-10-26 a las 21 17 25_c56b85a4](https://github.com/user-attachments/assets/7b5e6d78-4dd3-4f5d-8396-4078b0713ef0)
>
> Cuando cambiamos las variables observamos lo que respondiamos en la pregunta anterior. El no tener el lock hace que las variables cambien  tofo a la vez sin oportunidad de refrescar los datos. por lo que cuando tenemos la ventana sin el lock los valores cambian rapidamente a numeros muy aleatorios y extraños. mientras que cuando la tenemos activada los valores aumentan profgresivamente de manera ordenada

- 🐡 **Explica en tus propias palabras ¿Cómo puede presentarse la condición de carrera en este caso? ¿Qué es lo que está pasando? Te pido que propongas un ejemplo.**
>
> Es facil, la condicion de carrera es cuando dos o mas hilos tratan de acceder al material y modificarlo al mismo tiempo. Vamos a suponer que tenemos varias personitas y un numero inicial en el centro.
>
>Las personitas deberan sumar uno por uno los valores en orden
>
>si el valor inicial es un 3, pues la primera persona suma uno, quedando 4, la siguiente deberia quedarle 5, luego 6, luego 7 y asi sucesivamente. porque despues de que cada persona modifique su numero e otro sigue. Pues bueno, la condicion de carrera es como si todos hubiesen accedido al 3 a la vez y a todos les diera 4... por lo que la suma se vuelve un desorden porque nadie lo hace en orden

## 🦐 ACTIVIDAD 3

- 🐡 **Ejecuta el código y observa el resultado**
>
> CODIGO SECUENCIAL:
>
> ![Imagen de WhatsApp 2025-10-26 a las 21 33 15_9f56bfb4](https://github.com/user-attachments/assets/f8830246-0565-42d5-af93-89ce9b567324)
>
> CODIGO PARALELISMO:
>
> ![Imagen de WhatsApp 2025-10-26 a las 21 41 29_ca740747](https://github.com/user-attachments/assets/f68fc805-66cf-4562-bf97-681f3f8907f5)
>

- 🐡 **Analiza el código y estudia detenidamente su funcionamiento. En la fase de aplicación tendrás que retomar este código para resolver un reto**
>
> Ambos codigos nos muestran exactamente el mismo escenario, las diferencias radican en que el primero es solo un hilo y se demora un poquito, mientras que el segundo tiene 16 hilos pero es mucho mas rapido
>
> En otras palabras, mas hilos significan mayor rapidez


- 🐡 **Experimenta modificando, PERO, no olvides cómo investigamos en este curso:**
>
> - 🦑 Realiza cambios pequeños y específicos
>
> voy a modficar la cantidad de iteraciones y color
>
> - 🦑 Lanza una hipótesis sobre lo que crees que va a pasar
>
> Con las iteraciones espero poder cambiar la forma en la que se perciben las figuras, mientras que con el colo, bueno, espero modificar el color
>
> - 🦑 Ejecuta el código y observa lo que ocurre.
>
> sucede esto son las iteraciones
>
> - Iteraciones en 40:
<a name="evidencia3"></a>
> ![Imagen de WhatsApp 2025-10-26 a las 21 50 06_8927c970](https://github.com/user-attachments/assets/c1e9ce0e-dac9-425a-a764-501910dd6316)
>
> - Iteraciones en 10:
> ![Imagen de WhatsApp 2025-10-26 a las 21 50 59_3e1efd1e](https://github.com/user-attachments/assets/f5108c73-f23a-49af-85f2-c6a6c0b158af)
>
> y suecde esto con los colores
>
> ![Imagen de WhatsApp 2025-10-26 a las 21 57 28_be208bb0](https://github.com/user-attachments/assets/7d8bc965-cc49-45c5-8084-ebed6364a2eb)
>
> - 🦑 ¿Tu hipótesis era correcta? ¿Por qué crees que ocurre esto?
>
> Sip. ya que las iteraciones son para mi las repeticiones por lo que si las bajo, las figuras deben de ser menos complejas y mas abstractas... y con el color, basco con modificar uno de los valores del hue en el App.h

- 🐡 **¿Qué ocurre si cambias el número de hilos? ¿Por qué crees que ocurre esto?**
>
> Dado a que no puedo aumentar el numero de hilos dada las limitaciones del computador, trate de disminuirlos. Lo mas probable es que se haga un pelin mas lento el calculo
>
> ![Imagen de WhatsApp 2025-10-26 a las 22 06 09_143e3c22](https://github.com/user-attachments/assets/5ed883c8-640d-4043-8f5c-39615c95b1bb)
>
> En efecto, el tiempo auemnto cuando baje los hilos de 16 a 11

## 🦐 ACTIVIDAD 4

primero veamos lo que salio de amnos codigos

SIN HILOS:
![Imagen de WhatsApp 2025-10-26 a las 22 18 16_08fdb90b](https://github.com/user-attachments/assets/a05d8bda-be5a-4ff9-80ca-64dc11ad9dbc)

CON HILOS:
<a name="evidencia4"></a>
![Imagen de WhatsApp 2025-10-26 a las 22 21 08_ce484593](https://github.com/user-attachments/assets/07b42f99-8744-46e4-bb98-a7adab629144)

Ambos van igual de lentos, lo cual es bastante curioso, esperaba que fuese mas rapido con todos los hilos

- 🐡 **¿Cuál es la estructura de datos principal que contiene la información de todos los boids y que es accedida por múltiples hilos (el hilo principal para dibujar, el hilo trabajador para actualizar)?**
>
> la estructura de datos principal con la informacion es un vector llamado boids que almacena la informacion de todos los boid y es por el cual se accede por medio de los hilos

- 🐡 **Observa la función Flock::threadedFunction() donde el hilo trabajador calcula el movimiento. ¿Qué operaciones realizan sobre el vector de boids compartido?**
>
> La operacion que realiza es lo que hablabamos hace un momento de bloquer y desbloquear el acceso y edicion de dicha informacion compartida

- 🐡 **Observa la función ofApp::draw(). ¿Qué operación realiza sobre el vector compartido?**
>
>  esta funcion primero bloquea el vector y luego dibuja o que se encuentre en el flock para poderdespues desbloquer el vector y que usen otros hilos

- 🐡 **Observa Flock::addBoid() y ofApp::mouseDragged(). ¿Qué operación realizan?**
>
> la funcion Flock::addBoid() basicamente le añade nuevos boids a el vector usando como referencia la posicion del mouse, para que despues la funcion fApp::mouseDragged() active esta funcion y aparescan nuevos boids al arrastrar el mouse 

- 🐡 **Describe un escenario específico y concreto donde la falta de sincronización podría causar un problema**
>
> Creo que aqui seria lo mismo con el tema de las condiciones de carrera, habria un error ahi. ya que el hilo x esta leyendo el boid que ya hay mientras que se esta creando otro y lee lo que no es. Aqui incluso podriamos volover con el ejemplo del juego de las personitas sumando numeros progresivamente

- 🐡 **Localiza todas las llamadas a lock() y unlock() dentro de la clase Flock (o donde se acceda al vector compartido)**
>
> el lock y unlock se llama en tres lugares diferentes...
>
> En el addBoid, en el draw, threadedFunction

- 🐡 **¿Puedes intuir por qué tener muchos hilos esperando para adquirir un lock sobre el mismo vector (alta contención) podría limitar el beneficio de rendimiento del paralelismo en este caso? Justifica tu respuesta**
>
> cuando es aplicado el paralelismo a esta clase de programas con el fin de aumentar su eficiencia, la idea es que la información fluya mas rapido, sin embarg, locks impiden el flujo por un momento por lo que el proceso vuelve a ser lento asi que lo vuelve un poco contradictorio con la idea inicial

- 🐡 **¿Qué pasaría si tuviéramos varios hilos que calculan el movimiento de los boids? ¿Cómo podrías implementar esto? ¿Qué problemas crees que podrían surgir? ¿Cómo podrías solucionarlos?**
>
> si se utilizaran otros hilos para hacer calculos de la posicion, los problemas serian muy similares a los que se veian en los ejemplos anteriores donde era necesario agregarle blosqueos a la informacion para evitar los problemas de eficiencia, pero asi mismo, con los bloqueos surge el problema de que disminuye la velocidad con la que se ejecuta el programa, pero en estos casos ya no se prioriza la velocidad... tal y como el ejemplo de la simulacion de poblaciones... con hilos o sin hilos, no habia demasiado cambio

- 🐡 **Analiza el código del Flocking sin hilos y el Flocking con hilos. ¿Qué diferencias encuentras? ¿Por qué crees que es importante la sincronización en el segundo caso?**
>
> al revisar ambos codigos, las principales diferencias que se evidenciaron son la de la falta de bloqueos en el primer codigo, que es el que no tiene hilos, ya que no hay probabilidades de que hayan desfaces de la informacion y que se altere el programa, mientras que el segundo si las tiene.
>
> La segunda diferencia es que cuando se usan hilos hay varias funciones encargadas de que los propios hilos inicien su ejecucion, esperen al otro y finalicen sus funciones

- 🐡 **¿Por qué al añadir un nuevo boid la simulación se ralentiza? ¿Qué ocurre si añades muchos boids?**
>
> Añadir mas boids implica aumentar la cantidad de informacion que hay en el vector, por lo que son mas cosas para procesar, haciendo que se ralentice

- 🐡 **Notaste que la versión con hilos tiene un sleep(5) en el hilo trabajador. ¿Por qué crees que se ha añadido? ¿Qué pasaría si lo eliminamos?**
>
> hicimos el experimento de eliminar el sleep(5), lo que sucedio es que todo se ralentizo de manera increible. por ende, creo que la funcion del sleep es filtrar y hacer que toda la informacion vaya en una filita para que se procese una por una y no todas a la vez

- 🐡 **Compara el rendimiento de ambos enfoques. ¿Cuál crees que es más eficiente? ¿Por qué?**
>
> hmm... depende de por donde veamos el lado de la eficiencia
>
>ambos codigos tuvieron una capacidad de respuesta casi igual y se sobrecargaban casi con el mismo nivel de informacion
>
>por ende, si la eficiencia va desde el sentido del programador y del codigo, la primera version con un solo hilo es la mas indicada, ya que contiene menos lineas y cosas diferentes que programar.
>
> pero si la eficiencia va por el lado del pc entonces la segunda es la mejor dado a que hay una amplia distribucion de las gtareas y hay mas constrol

- 🐡 **¿Qué pasaría si no se usaran? ¿Cómo afectaría esto al comportamiento del programa? (No olvides por favor que las condiciones de carrera son difíciles de reproducir, así que no te preocupes si no puedes verlas en acción)**
>
> Pasaria lo mismo que uno de los ejercicios con el circulo. la informacion vendria pormontones y no se podriaq leer en orden, por lo que si tenemos una escala del 1 al 10, se leerian los datos a lazar ya que estarian sobrepuestos uno sobre el otro. En este ejemplo de aqui probablemente la posicion de cada particula sera completamente aleatoria cada vez que pueda cargar si quiera

- 🐡 **¿Qué ocurre si mientras el hilo trabajador está calculando el movimiento de los boids, el hilo principal intenta añadir un nuevo boid? ¿Se congelará la aplicación? ¿Por qué?**
>
> Aqui es mas de lo mismo, el hilo trabajador leeria la informacion del ultimo boid que habia antes de la actualizacion del otro.. por lo que leeria un dato erroneo y sin actualzar. asi que la posicion que procesaria estaria erronea

## 🦐 ACTIVIDAD 5

- 🐡 **Pega la parte clave de tu función modificada que calcula el píxel para el conjunto de Julia. Recuerda utilizar un bloque cpp.**

ofApp.h
```
#pragma once

#include "ofMain.h"
#include "ofThread.h"

class MandelbrotThread : public ofThread {
public:
	MandelbrotThread(int startY, int endY, int width, int height, int maxIter, ofPixels& pixelsRef, glm::vec2 juliaK)
		: startRow(startY)
		, endRow(endY)
		, imgWidth(width)
		, imgHeight(height)
		, maxIterations(maxIter)
		, pixels(pixelsRef)
		, vecK(juliaK) {
	}

	void threadedFunction() override {
		for (int y = startRow; y < endRow && isThreadRunning(); ++y) {
			for (int x = 0; x < imgWidth; ++x) {
				int iterations = calculateMandelbrotPixel(x, y);
				pixels.setColor(x, y, mapIterationsToColor(iterations));
			}
		}

		ofLogVerbose("MandelbrotThread") << "Hilo para filas " << startRow << "-" << endRow << " terminado.";
	}

private:
	int startRow, endRow;
	int imgWidth, imgHeight;
	int maxIterations;
	ofPixels& pixels;
	glm::vec2 vecK;

	int calculateMandelbrotPixel(int x, int y) {
		//float cx = ofMap(x, 0, imgWidth, -2.0, 1.0);
		//float cy = ofMap(y, 0, imgHeight, -1.5, 1.5);

		float zx = ofMap(x, 0, imgWidth, -2.0, 1.0);
		float zy = ofMap(y, 0, imgHeight, -1.5, 1.5);
		int iterations = 0;
		while (zx * zx + zy * zy < 4.0 && iterations < maxIterations) {
			float tempX = zx * zx - zy * zy + vecK.x;
			zy = 2.0 * zx * zy + vecK.y;
			zx = tempX;
			iterations++;
		}
		return iterations;
	}

	ofColor mapIterationsToColor(int iterations) {
		if (iterations == maxIterations)
			return ofColor::black;
		else {
			float hue = ofMap(iterations, 0, maxIterations, 0, 255);
			float brightness = ofMap(iterations, 0, maxIterations, 100, 255);
			float saturation = 200;
			return ofColor::fromHsb(hue, saturation, brightness);
		}
	}
};

class ofApp : public ofBaseApp {

public:
	void setup();
	void update();
	void draw();
	void exit();
	void keyPressed(int key);
	void startCalculation();
	void mouseDragged(int x, int y, int button);

	ofPixels pixels;
	ofTexture texture;

	int imgWidth;
	int imgHeight;
	int maxIterations;
	int numThreads;

	vector<MandelbrotThread*> threads;

	float startTime;
	float calculationTime;
	bool calculating;
	string statusMessage;
	int runningThreads;
};
```
ofApp.cpp
```
#include "ofApp.h"
#include <thread>

glm::vec2 juliaK;

//--------------------------------------------------------------
void ofApp::setup() {

	ofSetWindowTitle("Mandelbrot Paralelo (ofThread)");
	ofSetFrameRate(60);
	ofBackground(30);

	imgWidth = ofGetWidth();
	imgHeight = ofGetHeight();
	maxIterations = 100;

	numThreads = std::thread::hardware_concurrency();

	if (numThreads == 0) numThreads = 4; // Fallback si no se puede detectar
	ofLogNotice() << "Usando " << numThreads << " hilos.";

	pixels.allocate(imgWidth, imgHeight, OF_PIXELS_RGB);
	texture.allocate(pixels);

	calculating = false;
	calculationTime = 0.0f;
	runningThreads = 0;
	statusMessage = "Listo. \nPresiona ESPACIO para calcular.";
}

//--------------------------------------------------------------
void ofApp::startCalculation() {
	if (calculating) {
		ofLogWarning() << "Ya se está calculando, espera a que termine.";
		return;
	}
	calculating = true;
	runningThreads = 0; // Reseteamos contador antes de lanzar nuevos
	statusMessage = "Calculando con " + ofToString(numThreads) + " hilos...";

	ofLogNotice() << statusMessage;
	startTime = ofGetElapsedTimef();

	if (!threads.empty()) {
		ofLogVerbose() << "Limpiando hilos anteriores...";
		for (auto& thread : threads) {
			thread->waitForThread(true);
			delete thread;
		}
		threads.clear();
		ofLogVerbose() << "Hilos anteriores limpiados.";
	}

	int rowsPerThread = imgHeight / numThreads;
	for (int i = 0; i < numThreads; ++i) {
		int startY = i * rowsPerThread;
		int endY = (i == numThreads - 1) ? imgHeight : (i + 1) * rowsPerThread; // Asegura que el último hilo llegue hasta el final

		MandelbrotThread* newThread = new MandelbrotThread(startY, endY, imgWidth, imgHeight, maxIterations, pixels, juliaK);
		threads.push_back(newThread);
		runningThreads++;
		threads.back()->startThread(); // Inicia la ejecución de threadedFunction
		ofLogVerbose() << "Lanzado hilo " << i << " para filas " << startY << "-" << endY;
	}
	ofLogNotice() << runningThreads << " hilos lanzados.";
}

//--------------------------------------------------------------
void ofApp::update() {

	juliaK.x = ofMap(mouseX, 0, imgWidth, -1.5f, 1.5f);
	juliaK.y = ofMap(mouseY, 0, imgHeight, -1.5f, 1.5f);

	bool allThreadsFinished = true;
	if (!threads.empty()) { // Solo comprobar si hay hilos
		for (const auto& thread : threads) {
			if (thread->isThreadRunning()) {
				allThreadsFinished = false;
				break; // Si uno sigue corriendo, no necesitamos comprobar los demás
			}
		}
	}
	else {
		// Si no hay hilos en el vector, definitivamente no están corriendo
		allThreadsFinished = true;
	}

	if (allThreadsFinished && calculating) {
		calculationTime = ofGetElapsedTimef() - startTime;
		calculating = false;
		runningThreads = 0;
		statusMessage = "Cálculo completado. \nPresiona ESPACIO para recalcular.";
		ofLogNotice() << statusMessage << " Tiempo: " << calculationTime << " s";
		texture.loadData(pixels);
	}
}

//--------------------------------------------------------------
void ofApp::draw() {
	ofSetColor(255);
	texture.draw(0, 0, ofGetWidth(), ofGetHeight());

	stringstream ss;
	ss << "Version: Paralelo (ofThread)" << endl;

	ss << "Status: " << statusMessage << endl;
	if (!calculating && calculationTime > 0.0f) {
		ss << "Ultimo Tiempo: " << ofToString(calculationTime, 3) << " s" << endl;
	}
	ss << "Hilos Usados: " << numThreads << endl;
	// ss << "Hilos Corriendo: " << runningThreads << endl; // Podría fluctuar rápido

	ss << "Max Iteraciones: " << maxIterations << endl;
	ss << "Resolucion: " << imgWidth << "x" << imgHeight << endl;
	ss << "FPS: " << ofToString(ofGetFrameRate(), 0);

	ofSetColor(0, 180);
	ofDrawRectangle(10, 10, 350, 120); // Un poco más grande
	ofSetColor(255);
	ofDrawBitmapString(ss.str(), 20, 30);
}

//--------------------------------------------------------------
void ofApp::exit() {
	ofLogNotice() << "Saliendo, esperando a los hilos...";
	for (auto& thread : threads) {
		thread->waitForThread(true); // Espera bloqueante hasta que el hilo termine
		delete thread; // Liberar memoria
	}
	threads.clear();
	ofLogNotice() << "Hilos detenidos y limpiados. Adiós.";
}

//--------------------------------------------------------------
void ofApp::keyPressed(int key) {
	if (key == ' ') {
		maxIterations += 1;
		startCalculation();
	}
	if (key == 'n') {
		maxIterations = 0;
		startCalculation();
	}
}

void ofApp::mouseDragged(int x, int y, int button) {

	startCalculation();
}
```
- 🐡 **Muestra cómo mapeaste la posición del mouse a la constante k.**
```
MandelbrotThread(int startY, int endY, int width, int height, int maxIter, ofPixels& pixelsRef, glm::vec2 juliaK)
	: startRow(startY)
	, endRow(endY)
	, imgWidth(width)
	, imgHeight(height)
	, maxIterations(maxIter)
	, pixels(pixelsRef)
	, vecK(juliaK) {
}
```
```
int calculateMandelbrotPixel(int x, int y) {
	//float cx = ofMap(x, 0, imgWidth, -2.0, 1.0);
	//float cy = ofMap(y, 0, imgHeight, -1.5, 1.5);

	float zx = ofMap(x, 0, imgWidth, -2.0, 1.0);
	float zy = ofMap(y, 0, imgHeight, -1.5, 1.5);
	int iterations = 0;
	while (zx * zx + zy * zy < 4.0 && iterations < maxIterations) {
		float tempX = zx * zx - zy * zy + vecK.x;
		zy = 2.0 * zx * zy + vecK.y;
		zx = tempX;
		iterations++;
```
>
> Para ello creamos el vector JuliaK en el consttructor con sus variables vecK, y ya en la funcion de calcular el pixel (olvide cambiar el nombre de mandelbrot a julia) reemplace las c que habian por veck.x, veck.y

- 🐡 **Describe brevemente cómo reutilizaste la estructura de hilos de la versión Mandelbrot. ¿Tuviste que cambiar mucho esa parte?**
````
MandelbrotThread* newThread = new MandelbrotThread(startY, endY, imgWidth, imgHeight, maxIterations, pixels, juliaK);
threads.push_back(newThread);
runningThreads++;
threads.back()->startThread(); // Inicia la ejecución de threadedFunction
ofLogVerbose() << "Lanzado hilo " << i << " para filas " << startY << "-" << endY;
````
>
> No en realidad, solamente habia que añadir el nuevo vector, JuliaK

- 🐡 **¿Cómo te aseguraste de que la imagen se recalculara cuando el mouse se movía?**
````
void ofApp::mouseDragged(int x, int y, int button) {

	startCalculation();
}
````
>
> La parte del codigo encargada del mouse es esta. Es una funcion simple que llama al calculo constantemente. Crei que iba a tener que ponerle mas cosas, pero funciono asi. MiYa en pantalla, mientaras tienes presionado el espacio, la posicion se actualiza con el mouse

- 🐡 **Incluye al menos dos capturas de pantalla que muestren diferentes fractales de Julia generados al mover el mouse en tu aplicación.**

<a name="evidencia5"></a>
<img width="1029" height="771" alt="Captura de pantalla 2025-10-28 222550" src="https://github.com/user-attachments/assets/31ce6b42-a5d9-4176-bd63-103a50edffef" />
<img width="1029" height="771" alt="Captura de pantalla 2025-10-28 222619" src="https://github.com/user-attachments/assets/3c7537aa-a46e-4f3b-bb1f-72c53f0aae7a" />
<img width="1027" height="766" alt="Captura de pantalla 2025-10-28 222608" src="https://github.com/user-attachments/assets/75595c40-1a2e-43b4-bbd5-40ed4494efb1" />


- 🐡 **¿Encontraste algún desafío particular al implementar la interacción o modificar el cálculo?**
>
> En realidad el trabajo era una bobada increible. Simplemente no estabamos seguras de por donde empezar ni como segurarnos de que todo estuviera conectado. Eso ignorando de que se me olvido como leer y comparar AJAJAJ
>
> Pero una vez medio entendiamos como iba la cosa, se logro... solo habian quedado una pendejadita de errores de ortografía por ahi sueltos

## 🦐 AUTOEVALUACION

- 🐡 **NOTA PROPUESTA: 5.0**
- 🐡 **DEFENSA**

ACTIVIDAD 01
El estudiante ejecuta los codigos base y entiende el concepto base de un hilo y la importancia de sus usos para la distribucion de tareas
[evidencia actividad 1](#evidencia1)

ACTIVIDAD 02
El estudiante analiza a profundidad la condicion de carrera y sus caracteristicas
[evidencia actividad 1](#evidencia2)

ACTIVIDAD 03
El estudiante analiza las ecuaciones de mandelbrot y experimenta con el codigo para modificar su previsualización
[evidencia actividad 1](#evidencia3)

ACTIVIDAD 04
El estudiante estudia los comportamientos de los boids y flocks
[evidencia actividad 1](#evidencia4)

ACTIVIDAD 05
El estudiante modifica las ecuaciones de mandelbort para convertirlas en julia y que se acualice con la posicion del mouse
[evidencia actividad 1](#evidencia5)
