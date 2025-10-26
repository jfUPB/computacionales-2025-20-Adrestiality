# Bitácora de aprendizaje de la unidad 8
🦐

## 🦐 ACTIVIDAD 1

- 🐡 **Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?**
>
> No me abre nada... La verdad me asuste bastante cuando vi el error de compilacion. genuinamente desconozco el motivo... la variable mas extraña es la que dice "heavyComputation"...

- 🐡 **Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?**
>
> En algunas líneas del codigo sale cosas relacionados a circulos... por lo que esperaba un circulo enorme o algo asi... pero... Sigue saliendo error y no se que haceeeer
>
> <img width="444" height="168" alt="image" src="https://github.com/user-attachments/assets/730a3ad0-959a-4642-9c47-8f10781a126b" />
>
> Al parecer hay un error en esta linea del ofApp.h
>
> <img width="264" height="28" alt="image" src="https://github.com/user-attachments/assets/891bb90e-b20b-441f-b087-cd102a578d30" />

- 🐡 **Explica en tus propias palabras ¿Cómo puede presentarse la condición de carrera en este caso? ¿Qué es lo que está pasando? Te pido que propongas un ejemplo.**
>
> CONCURRENCIA: son muchas tareas que se hacen al mismo tiempo y en el mismo lugar... es como si un equipo de enanos ser encargara de hacer 100 regalos a la vez
>
> PARALELISMO: son muchas tareas que se hacen al mismo tiempo pero en diferentes lugares... como si 10 equipos de 2 enanitos hicieran 100 regalos en total. donde cada uno de los 10 equipos se encarga de hacer de a 10 regalos

## 🦐 ACTIVIDAD 2

- 🐡 **¿Qué ocurre con el rendimiento del programa? ¿Es posible que el rendimiento se vea afectado por el uso de mutex? ¿Por qué?**
>
> 00

- 🐡 **Ejecuta el código y observa el resultado. ¿Qué ocurre si cambias el valor de la variable useLock? ¿Por qué crees que ocurre esto?**
>
> 00

- 🐡 **Explica en tus propias palabras ¿Cómo puede presentarse la condición de carrera en este caso? ¿Qué es lo que está pasando? Te pido que propongas un ejemplo.**
>
> 00

## 🦐 ACTIVIDAD 3

- 🐡 **Ejecuta el código y observa el resultado**
>
> 00

- 🐡 **Analiza el código y estudia detenidamente su funcionamiento. En la fase de aplicación tendrás que retomar este código para resolver un reto**
>
> 00

- 🐡 **Experimenta modificando, PERO, no olvides cómo investigamos en este curso:**
>
> - 🦑 Realiza cambios pequeños y específicos
>
> 000
>
> - 🦑 Lanza una hipótesis sobre lo que crees que va a pasar
>
> 000
>
> - 🦑 Ejecuta el código y observa lo que ocurre.
>
> 000
>
> - 🦑 ¿Tu hipótesis era correcta? ¿Por qué crees que ocurre esto?
>
> 000

- 🐡 **Te dejo una idea para comenzar a experimentar: ¿Qué ocurre si cambias el número de hilos? ¿Por qué crees que ocurre esto?**
>
> 00

## 🦐 ACTIVIDAD 4

- 🐡 **¿Cuál es la estructura de datos principal que contiene la información de todos los boids y que es accedida por múltiples hilos (el hilo principal para dibujar, el hilo trabajador para actualizar)?**
>
> 000
- 🐡 **Observa la función Flock::threadedFunction() donde el hilo trabajador calcula el movimiento. ¿Qué operaciones realizan sobre el vector de boids compartido?**
>
> 000
- 🐡 **Observa la función ofApp::draw(). ¿Qué operación realiza sobre el vector compartido?**
>
> 000
- 🐡 **Observa Flock::addBoid() y ofApp::mouseDragged(). ¿Qué operación realizan?**
>
> 000
- 🐡 **Describe un escenario específico y concreto donde la falta de sincronización podría causar un problema**
>
> 000
- 🐡 **Localiza todas las llamadas a lock() y unlock() dentro de la clase Flock (o donde se acceda al vector compartido)**
>
> 000
- 🐡 **Justificación: para uno de los escenarios problemáticos que describiste arriba, explica cómo las llamadas a lock()/unlock() en las secciones de código relevantes evitan que ocurra ese problema específico**
>
> 000
- 🐡 **¿Puedes intuir por qué tener muchos hilos esperando para adquirir un lock sobre el mismo vector (alta contención) podría limitar el beneficio de rendimiento del paralelismo en este caso? Justifica tu respuesta**
>
> 000
- 🐡 **¿Qué pasaría si tuviéramos varios hilos que calculan el movimiento de los boids? ¿Cómo podrías implementar esto? ¿Qué problemas crees que podrían surgir? ¿Cómo podrías solucionarlos?**
>
> 00
- 🐡 **Analiza el código del Flocking sin hilos y el Flocking con hilos. ¿Qué diferencias encuentras? ¿Por qué crees que es importante la sincronización en el segundo caso?**
>
> 00
- 🐡 **¿Por qué al añadir un nuevo boid la simulación se ralentiza? ¿Qué ocurre si añades muchos boids?**
>
> 00
- 🐡 **Notaste que la versión con hilos tiene un sleep(5) en el hilo trabajador. ¿Por qué crees que se ha añadido? ¿Qué pasaría si lo eliminamos?**
>
> 00
- 🐡 **Compara el rendimiento de ambos enfoques. ¿Cuál crees que es más eficiente? ¿Por qué?**
>
> 00
- 🐡 **¿Qué pasaría si no se usaran? ¿Cómo afectaría esto al comportamiento del programa? (No olvides por favor que las condiciones de carrera son difíciles de reproducir, así que no te preocupes si no puedes verlas en acción)**
>
> 00

- 🐡 **¿Qué ocurre si mientras el hilo trabajador está calculando el movimiento de los boids, el hilo principal intenta añadir un nuevo boid? ¿Se congelará la aplicación? ¿Por qué?**
>
> 00

## 🦐 ACTIVIDAD 5
