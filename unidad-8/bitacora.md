# Bitácora de aprendizaje de la unidad 8
🦐

## 🦐 ACTIVIDAD 1

- 🐡 **Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?**
>
> 00

- 🐡 **Ejecuta el programa y haz clic en la ventana. Observa lo que sucede. ¿Qué es lo que ves? ¿Qué es lo que esperabas ver? ¿Por qué crees que sucede esto?**
>
> 00

- 🐡 **Explica en tus propias palabras ¿Cómo puede presentarse la condición de carrera en este caso? ¿Qué es lo que está pasando? Te pido que propongas un ejemplo.**
>
> 00

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
