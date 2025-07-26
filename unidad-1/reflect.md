# Unidad 1

## 🤔 Fase: Reflect

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 05 ༓☾∘∙•⋅⋅⊰⋅•⋅**

### [Parte 1]

-  #### Describe con tus palabras las tres fases del ciclo Fetch-Decode-Execute. ¿Qué rol juega el Program Counter (PC) en este ciclo?
Fetch: Busca, Decode:decodifica, Execute:Ejecuta. En otras palabras, ante cada línea de código, el computador busca lo que necesita, decodifica lo que debe hacer y lo ejecuta finalmente.
 
-  #### ¿Cuál es la diferencia fundamental entre una instrucción-A (que empieza con @) y una instrucción-C (que involucra D, M, A, etc.) en el lenguaje ensamblador de Hack? Da un ejemplo de cada una.

INSTRUCCIÓN A: Carga un valor numérico en A; @5
INSTRUCCIÓN C: Operaciones o saltos; 0;JMP

-  #### Explica la función de los siguientes componentes del computador Hack: el registro D, el registro A y la ALU.
REGISTRO A: Almacenamos un número o dirección de la RAM
REGISTRO D: Es como un acumulador que usamos usualmente para operaciones
ALU: Operaciones matemáticas

-  #### ¿Cómo se implementa un salto condicional en Hack? Describe un ejemplo (p. ej., saltar si el valor de D es mayor que cero).
Los saltos funcionan con diferentes condiciones pero siempre igualando cierto valor, (por ejemplo el valor de D) con 0.
Existen diferentes códigos que nos permiten comprar las variables ya sea siendo mayor a 0. mayor o igual a 0, menor a 0 menor o igual a 0 y siendo equivalente a 0

-  #### ¿Cómo se implementa un loop en el computador Hack? Describe un ejemplo (p. ej., un loop que decremente un valor hasta que llegue a cero).
Los loops se implementan gracias a los saltos y las etiquetas. Las etiquetas nos permiten, valga la redundancia, etiquetar ciertas lineas de código que sabemos que hacen cosas especificas. Dico código dentro de las etiquetas deben contener alguna serie de instrucciones que menjen de cierta menra las variables, de modo en que cuando llegamos a un salto, el salto pueda "decidir" (recordemos que solo se comparar a 0) si el loop debe repetirse nuevamente o si ya no es necesario que se siga repitiendo ya que obtuvimos los números que necesitabamos

-  #### ¿Cuál es la diferencia entre la instrucción D=M y la instrucción M=D?
D=M: Hacemos que D ontenga un valor específico de la RAM
M=D: Hacemos que un valor de la RAM ontenga el mismo valor de D

-  #### Describe brevemente qué se necesita para leer un valor del teclado (KBD) y para “pintar” un pixel en la pantalla (SCREEN).

### [Parte 2]

-  #### ¿Cuál fue el concepto o actividad más desafiante de esta unidad para ti y por qué?
Probablemente el entender como funciona M, en que momentos se llama una dirección de RAM o un valor... Y DEFINITIBAMENTE el tema de tratar de programar. aunque entiendo mayoritariamente la logica, me cuesta aplicarla aún

-  #### La metodología de “predecir, ejecutar, observar y reflexionar” fue central en nuestras actividades. ¿En qué momento esta metodología te resultó más útil para entender algo que no tenías claro?
Sobretodo en las dos últimas actividades. Comencé a analizar línea por línea que hace cada cosa y que efecto puede tener en las próximas líneas

-  #### Describe un momento “¡Aha!” que hayas tenido durante estas dos semanas. ¿Qué estabas haciendo cuando ocurrió?
Cuando entendí el por qué la computadora asocia las variables que creamos con ubicaciones a partir de la 16... No sabia que los primeros 15 espacios se reservaban normalmente para otras cosas. 
También cuando entendí los números negativos

-  #### Pensando en la próxima unidad, ¿Qué harás diferente en tu proceso de estudio para aprender de manera más efectiva?
No haría algo en si muy diferente. Sino que trataría de implementar mucho más lo de “predecir, ejecutar, observar y reflexionar". me ayuda a entender mucho más.

### **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**

[BITÁCORA DE CAROLINA GARCÍA]

[ACTIVIDAD 1]
Me parece que tiene una defición bastante elegante pero concisa acerca de las fases fetch-decode-execute, el funcionamiento de las operaciones básicas y la diferencia entre la memoria ROM y RAM.
Siento que hace unas definiciones algo sofisticadas pero no pierde su mensaje

[ACTIVIDAD 2]
Explica en su totalidad el funcionamiento del pc, las instrucciones ALU y el como se aplican. Tambien deja muy en claro como funcionan los bucles y las etiquetas, ya que hace uso de ellas de manera correcta en sus programas

[ACTIVIDAD 3]
Su código en lenguaje ensamblador está correcto y completo. Además incluye una explicación paso a paso de lo que hace el programa 

[ACTIVIDAD 4]
Me parece que es un código bastante completo. Incluye etiquetas, saltos y loops donde es necesario, demostrando que la estudiante comprendió correctamente dichos temas. Así mismo el ccódigo está explicado paso por paso, hasta que finalmente cumple su cometido que es guardar un valor en la posición 12 de la RAM

### **ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  #### Continuar: ¿Qué aspecto de las actividades, las explicaciones o la dinámica de la clase te ha resultado más útil o te ha gustado más y debería seguir haciendo?
Me gustaría que existiese la manera de hacer las clases un poco más llamativas. Quizás asi a las personas no les de tanto sueño y  no se distraigan. 
Aunque en general me gusta la actividad de interpretar cada linea código

-  #### Dejar de hacer: ¿Qué aspecto de la unidad te ha resultado confuso, poco útil o frustrante? ¿Hay algo que crees que debería eliminar o cambiar drásticamente?
No considero que haya que cambiar algo de manera drástica. pero si seria ideal hacer un poco más intoductorio el tema del lenguaje ensamblador, ya que nadie lo conoce y jam´s habíamos hecho uso de el

-  #### Empezar a hacer: ¿Qué te habría gustado que hiciéramos que no hicimos? ¿Tienes alguna idea para una actividad o un recurso que podría mejorar el aprendizaje en la próxima unidad?
Me gustaría seguir implementando lo de analizar línea por línea. Siento que es más fácil digerir la información del lenguaje ensamblador así ya que su lógica es muy compleja para mi

-  #### Ritmo y Dificultad: en una escala del 1 (muy fácil/lento) al 5 (muy difícil/rápido), ¿Cómo calificarías el ritmo y la dificultad general de esta unidad? ¿Por qué?
 3... No es demasiado rápido, pero tampoco tan lento. siento que estamos bien así...

-  #### Comentario Adicional: ¿Hay algo más que te gustaría compartir sobre tu experiencia de aprendizaje en esta unidad?
No tengo comentarios adicionales
