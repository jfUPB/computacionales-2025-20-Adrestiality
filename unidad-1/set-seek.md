# **Unidad 1**
//esto es markdown// todo se guarda en .asm
## 🔎 Fase: Set + Seek

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **Actividad 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@1
D=A
@2
D=D+A
@16
M=D
@END
(END)
0;JMP
```
-  ##### *¿Qué crees que haga este programa?*
La verdad no estoy segura, pero juzgando por las letras, que asumo que son variables, parece como si se estuviese sumano lo mismo... 

#### **Experimento [1]**
```
(START)
@1
D=A
@2
D=D+A
@16
M=D
@START
(END)
0;JMP
```
-  ##### *¿Qué sucede?*  
la cpu, que parece ser un contador, aumenta a medida que vamos avanzando en las instrucciones. tambien descubri que que las instrucciones con @cambian el valor en A...  entonces en varias instrucciones cambia su valor en realidad.
-  ##### *¿Qué valor se almacena en la dirección de memoria 16?* 
se almacena un 3 en la dirección 16
- ##### *¿Por qué crees que es ese valor?*
por la linea que dice M=D, en la memoria se almacena un 3 (el valor de D) en la posicion 16 (el numero de A)
- ##### *¿Qué instrucciones se ejecutan en cada ciclo Fetch-Decode-Execute?*
se recuperan los datos, se decodifican y fialmente ejecuta cada orden en cada una de las lineas
-  #####  *¿Qué cambios observas en el contenido de la memoria y los registros?*
cambian de valor dependiendo de A y D, y asi mismo A y D cambian de valor dependiendo de las instrucciones que hay en cada linea.

#### **Experimento [2]**
```
(START)
@5
D=A
@10
D=D+A
@20
M=D
@START
(END)
0;JMP
```
### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  ##### *¿Qué diferencia hay entre los datos almancenados en la memoria ROM y en la RAM?*
los datos almacenados en la mamoria RAM son termporales y los de ROM son permanentes.

### **Actividad 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**

#### **Experimento [1]**
```
@SCREEN
D=A
@i
M=D
(READKEYBOARD)
@KBD
D=M
@KEYPRESSED
D;JNE
@i
D=M
@SCREEN
D=D-A
@READKEYBOARD
D;JLE
@i
M=M-1
A=M
M=0
@READKEYBOARD
0;JMP

(KEYPRESSED)
@i
D=M
@KBD
D=D-A
@READKEYBOARD
D;JGE
@16
A=M
M=-1
@i
M=M+1
@READKEYBOARD
0;JMP
```
-  ##### *¿Qué crees que iba a suceder?*
Esperaba otro ejercicio de sumas y restas y ubicaciones en la RAM con algunos saltos y ciclos
-  ##### *¿Por qué tu predicción no fue correcta?* 
Muy genuinamente, no tenía idea de que se podía "pintar" con pixeles, y menos que fuese bajo la condición de una tecla constantemente presionada. Fué chistoso descubrirlo.

### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  ##### *Identifica una instrucción que use la ALU y explica qué hace*
```
@i
D=M
@SCREEN
D=D-A
```
Estas líneas usan la ALU para restar el valor de A al valor de D, y guarda el resultado en D nuevamente.
-  ##### *¿Para qué sirve el registro PC?*
El registro PC es el encargador de guardar la dirección de la siguiente instrucción a ejecutar
-  ##### * ¿Cuál es la diferencia entre @i y @READKEYBOARD?*
@i es una variable que se creapara guardar la posición en la pantalla
@READKEYBOARD es un marcador para un lugar en el código
-  ##### * Describe qué se necesita para leer el teclado y mostrar información en la pantalla*
Se accede a la dirección KBD. Si el valor es diferente de 0, es porque hay una tecla presionada
-  ##### * Identifica un bucle en el programa y explica su funcionamiento*
```
(READKEYBOARD)
...
@READKEYBOARD
0;JMP
```
Gracias a este bucle el programa se repite constantemente, ya que verifica si hay una tecla presionada, y dependiendo del valor crea pixeles y avanza o los borra y va para atrás
-  ##### * Identifica una condición en el programa y explica su funcionamiento*
```
@KBD
D=M
@KEYPRESSED
D;JNE
```
Aquí se pregunta si el valor del teclado es diferente de cero. Si sí hay una tecla presionada, salta a KEYPRESSED... Si no, continúa borrando la pantalla.
