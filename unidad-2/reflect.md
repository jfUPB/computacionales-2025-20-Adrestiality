# Unidad 2

## 🤔 Fase: Reflect
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

### [Parte 1]

1. Explica cómo se representa y manipula un puntero en el lenguaje ensamblador de Hack. Describe las operaciones equivalentes a p = &a (asignar dirección) y *p = 20 (escribir a través del puntero) usando instrucciones de ensamblador.

Dentro del lenguaje ensamblador Hack, no hay como tal una función puntero. Es mas bien el uso que nsosotros le damos a una ranura de la memoria RAM.
Para asignar una direccion en hack, simplemente es necesario llamar a la ranura del puntero y luego llamar otra dirección de la cual queremos usar o extraer algo. si queremos que el puntero apunte ""automaticamente o progresivamente en orden" basta con irle sumando al valor al que debe apuntar

2. ¿Cómo implementarías el acceso a un elemento de un arreglo, como arr[j], en lenguaje ensamblador? Describe el rol de la dirección base del arreglo y el índice j en esta operación.

Realmente lo que estamos haciendo constantemente es llamar y buscar ranuras de memoria RAM. La dirección base es donde empieza el arreglo y j seria la ubicación en la ram

### [Parte 2]

1. ¿Cuál fue el concepto más abstracto o difícil de “traducir” de C++ a ensamblador en esta unidad (punteros, ciclos, arreglos)? ¿Qué hiciste para lograr entenderlo?

Entender que necesitaba un contador y usar los punteros, además la lógica en general. Normalmente no em va bien en la programación, por lo que siempre debo acudir a segundo para poder entender y hacerme una idea de como debo aplicar la teoría que ya se a unas cuantas líneas de código.

2. En la Actividad 06 se sugirió construir el programa “PASO A PASO mediante pruebas”. ¿Cómo te ayudó este enfoque a manejar la complejidad del problema?

Fue una herramienta interesante. ya que me obligaba a documentar mis fallos y el cómo los mejoré. Lamentablemente perdí dicha información entre varias cosas. Pero la gran mayoría de capturas que había tomado era sobre cómo trataba de crear el arreglo de valores y que se asignaran respectivamente. Lo otro no tienía documentación ya que lo hice progresivamente con mis compañeros de clase.

3. Esta unidad fue el “puente” hacia C++. ¿Qué concepto de bajo nivel te sientes más seguro de poder identificar cuando lo veas implementado en C++?

Probablemnte los punteros. Son los más faciles de reconocer. Solo espero que c++ no tenga una lógica tan compleja...

### **ACTIVIDAD 08 ༓☾∘∙•⋅⋅⊰⋅•⋅**

**BITÁCORA DE CAROLINA GARCÍA ORTEGA**

```
@ARR
D=A
@0
M=D
@1
M=1
@2
M=0
(LOOP)
@1
D=M
@10
D=D-A
@END
D;JGT
@1
D=M
@0
A=M
M=D
//Almacenar la suma del arreglo
@2
M=D+M
@1
M=M+1
@0
M=M+1
@1
D=M
@LOOP
0;JMP
(END)
```
### [Resultados]

La actividad en la bitácor ad ecarolina me pareió bastante interesante. Aunque aun no acabo de entender los procesos que ella hizo. Hizo un código relativamente corto, Empleó la RAM [1] como lugar en el que iba a ir asiganando los valores de la sumatoria. tampoco hizo uso de un arreglo en si, sino que progresivamente se iban sumando los valores. Es interesante. Tengo que preguntarle bien como funciona lo que hizo allí

### **ACTIVIDAD 09 ༓☾∘∙•⋅⋅⊰⋅•⋅**

1. Continuar: ¿Qué actividad, problema o explicación de esta unidad te ayudó más a entender la conexión entre el bajo y el alto nivel? ¿Qué debería mantener sin cambios?

Siento que algunas clases son muy entretenidas, irónicamente entre más nos haces reír mas fácil te prestamos atención. También me gustan las explicaciones con los dibujitos y flechitas en el tablero. Reconozco que me gusta ver colores y se me hace m'as llamativo

2. Dejar de hacer: ¿Hubo alguna actividad o concepto que te pareció redundante, demasiado confuso o que aportó poco valor a tu aprendizaje? ¿Qué eliminarías o modificarías?

No veo necesidad de mejoras, siento que está bien. Aunque reconozco que algunas actividades de apply son un poco largas y contamos con 2 días para hacerlas ya que sigue la fase reflect... Dependiendo de la actividad de apply sería ideal dar un poco más de tiempo, ¿no?... apply es la fase más importante al fin y al cabo (Lo digo porque mi horario es demasiado pesado, lo que implica que tengo menos tiempo en semana)

3. Empezar a hacer: ¿Qué idea tienes para mejorar la próxima unidad? ¿Hay algún tipo de recurso que te habría ayudado a entender mejor los punteros o los arreglos?

Definitivamente siento que puedo ser mejor a la hora de programar. Siempre, SIEMPRE me ha dado dificultad toda clase de lógica de programación, y auqnue entienda ciertos conceptos, muchas veces acabo recurriendo a internet o IA cuando ya no soy capaz, para ver como lo hace la IA y a veces trato de replicarlo. En otras formas, me frustro muy facil

Con respecto a los punteros siento que fueron claros. Fueron más complejos en el ensamblador, pero en c++ no los veo taaaan mal... o quizas si los vea mal despues, jaja

4. Ritmo y Dificultad: en una escala del 1 (muy fácil/lento) al 5 (muy difícil/rápido), ¿Cómo calificarías el salto de dificultad de la Unidad 1 a la Unidad 2? ¿El ritmo fue adecuado? Justifica tu calificación.
probablemente un 3. Realmente los temas estaban faciles de entender, lo dificil fue aplicarlos al ensamblador con el ejercicio del arreglo y las sumas 

5. Comentario Adicional: ¿Alguna otra cosa que quieras compartir sobre cómo te sentiste aprendiendo estos conceptos?

No en realidad. Gracias por dejarme subir la actividad de apply por otro lado.
También me pregunto como es que consigues leer tantas "horrografías" en las bitácoras, dado que no cuentan con autocorrector. (Sé que yo tambien he puesto mis buenas horrografías tambien)
