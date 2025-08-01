# Unidad 2

## 🔎 Fase: Set + Seek

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```asm
@SCREEN
M=1
```
```c++
screen = 1;
```
<img width="374" height="34" alt="image" src="https://github.com/user-attachments/assets/efe25a5e-7c18-4855-8e06-337b7aa23766" />

-  **predice, ejecuta, observa y reflexiona** 𖤓 ☆ ☼ ⋆⋅**

**[PREDICE]** Gracias a la etiqueta SCREEN, el compuatdor debe iniciar la posición de la pantalla, es decir, 16384. Luego asignamos un 1 en uno de los 16 dígitos de la posición 16384

**[EJECUTA]** En efecto, ttras pasar el código a NAND2tetris, la etiqueta SCREEN se transporma en 16384, luego lo lee y A pasa a dicho valor. Luego M=1 asigna un valor al 16384 de RAM que acabamos de leer y asigna el 1 en el último valor de los 16 ceros que hay

**[OBSERVA]** El código funciona con normalidad. el pixel es super chiquito, pero funciona

**[REFLEXIONA]** No fue necesario usar un montón de líneas de código. Con solo una línea podíamos llamar a las ubicaciónes de la memoria que coincidían con la pantalla y otras sola líanea de código para rellenarla con un solo valor, 1

## **ACTIVIDAD 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```asm
@SCREEN
M=-1
```
```c++
screen = -1;
screen = 0xFFF;
```
<img width="358" height="30" alt="image" src="https://github.com/user-attachments/assets/fe1fd9e0-16af-4807-8311-1ef13ec75358" />

-  **predice, ejecuta, observa y reflexiona** 𖤓 ☆ ☼ ⋆⋅**

**[PREDICE]** Gracias a la etiqueta SCREEN, el compuatdor debe iniciar la posición de la pantalla, es decir, 16384. Luego asignamos un -1, el cual representa un numero enorme en positivos, y llena las 16 casillas de ese lugar 

**[EJECUTA]** En efecto, ttras pasar el código a NAND2tetris, la etiqueta SCREEN se transporma en 16384, luego lo lee y A pasa a dicho valor. Luego M=-1 asigna un valor al 16384 de RAM que acabamos de leer y llena todas las 16 casillas

**[OBSERVA]** Se ve claramente la linea con los 16 pixeles llenos

**[REFLEXIONA]** No es necesario llenar todas las 16 casillas una por una. Podemos poner un numero grande directamente. Recordemos que los números negativos dentro de el lenguaje ensamblador, se interpretan como números positivos demasiado grandes, lo cual cuando tratamos de rellenar los 16 pixeles, podemos poner simplemente esos 16 pixeles con un número enorme como el que representa el -1 

## ACTIVIDAD 03༓☾∘∙•⋅⋅⊰⋅•⋅**
```asm
@SCREEN
M=-1
@CONTADOR
M=0
 
(LEER)
 
 
@KBD
D=M
 
@100
D=D-A
@DERECHA
D;JEQ
 
 
@KBD
D=M
 
@105
D=D-A
@IZQUIERDA
D;JEQ
 
@LEER
0;JMP
 
 
(DERECHA)
@CONTADOR
D=M
@SCREEN
A=D+A
 
M=0
 
@CONTADOR
M=M+1
D=M
@SCREEN
A=D+A
 
M=-1
@LEER
0;JMP
 
 
(IZQUIERDA)
@CONTADOR
D=M
@SCREEN
A=D+A
M=0
 
@CONTADOR
M=M-1
D=M
@SCREEN
A=D+A
 
M=-1
 
@LEER
0;JMP
```
```c++

//NO ES C++
Memoria [SCREEN] = -1;
CONTADOR = 0;

int tmp;
while(1)
{
tmp = KBD;
if(tmp == 100){
  //DERECHA
}
else if (tmp == 105){
  //IZQUIERDA
}

Memoria[CONTADOR+SCREEN] = 0;
CONTADOR = CONTADOR +1;

Memoria[CONTADOR+SCREEN] = -1;
```
-  **predice, ejecuta, observa y reflexiona** 𖤓 ☆ ☼ ⋆⋅**

**[PREDICE]** Ambos códigos deberían poder leer las teclas presionadas y asignarles a la memoria diferentes valores. de modo en que cuando el código deba decidir que línea ejecutar (ya sea el de la derecha o el de la izquierda) solo deba hacer operaciones con los números asignados previamente y relacionarlo con sus condiciones

**[EJECUTA]** Básicamente en este código ensamblador estamos diciendo que dependiendo del valor de la variable D, se hagan saltos y se ejecute las líneas de código de la derecha e izquierda. Se cumple eso gracias a los saltos condicionales, cuando se presiona la tecla D se asigna un 100 y bajo cierta operación, si da igual a 0 se ejecuta el código de la derecha, mientras que si presionamos la tecla I, el código le asignará un 105 y bajo otra operación, se realizará un salto al código de la izquierda, encargado de seguir coloreando filas de pixeles

Ya en este código de c++, se crea una variable tmp que supuestamente le permite programar y computar a la par qque el código , encargada de leer las teclas y, asi mismo asignarles 100 a la D y 105 a la I. Con los condicionales if y else if, podemos asegurarnos que si en efecto la lectura de la tecla D es 100 (o si la lectura de la tecla I es 105) se le sume al contador y a la pantalla, o que le reste

**[OBSERVA]** En el código ensamblador hack es necesario hacer reiteradas verificaciones y saltos condicionales para que el computador pueda mover y verificar si hay o no una tecla presionada. Cuando empieza, verifica la tecla presionada, si no hay nada presionado, eventualmente en las operaciones no va a concordar nada y debera volver a verificar si hay alguna tecla presionada hasta que pueda asignar algun valor. Ya sea que presionemos la tecla D o I, el computador asignará los respectivos valores y hara operaciones y saltos con ellos, llevándolos a sus respectivas líneas de código para que se pinte la barrita de pixeles en el lugar deseado, luego vuelve y verifica si hay una tecla presionada, si no la hay, pues vuelve al bucle de constantes verificaciones hasta recibir una tecla y poder signar un valor, si en efecto hay algo presionado ejecuta la respectiva linea de código y asi hasta que paremos el código

En el código de c++ podría decirse que es lo mismo, no obstante aquí no es necesario hacer tantas operaciones con los valores asignados a D o I, ya que basta con igualarlos en su respectivo valor, es decir, si en efecto en D hay 100, o si en efecto en I hay 105, pues se pinta una linea en cierto lugar y vuelve al inicio

**[REFLEXIONA]** Aun me cuetsa entender por qué en el código de c++ debemos usar un tmp. De hecho aun no me queda claro que es. Tampoco me queda muy claro como es que su código se reinicia, o se si es solo propiedad de los condicionales como el while o si hay algo más

### ACTIVIDAD 04༓☾∘∙•⋅⋅⊰⋅•⋅**

```c++
//Adds 1+...+100.
 int i=1;
 int sum=0;

 while(i <=100){
    sum+= i;
    i++;
 }
```
```c++
//Adds 1+...+100.
int sum=0;
for(int i = 1; i <=100; i++){
   sum+= i;
}
```
```asm
@i
M=1

@sum
M=0

(WHILE)

@I
D=M
@100
D=D-A
@END
D;JGT

@i
D=M // D=i
@sum
M=D+M // sum=sum+i
@i
M=M+1 // i=i+1


@WHILE
0;JMP


```
**[CONCLUSIONES]** Aquí podemos entender que el for y el while son lo mismo, por ende este código en lenguaje ensamblaro también replican lo mismo que los dos códigos de c++

```c++
int a = 10;
int* p;
p = &a;
*p = 20;
```
```c++
int a = 10;
int b = 5;
int *p;
p = &a;
b = *p;
```

### ACTIVIDAD 05༓☾∘∙•⋅⋅⊰⋅•⋅**
> ¿Qué es un puntero?
Es una variable que busca almacenar la dirección de la memoria de otra variable (o mejor dicho, apuntan a la direccion de cierta variable). Ojo, solo almacena la DIRECCIÓN, no su valor en si como variable 

> ¿Cómo se declara un puntero?
Los punteros se declaran, o se llaman inicialmente con int* p; en c++, 


> ¿Cómo se define el puntero en C++?
Los punteros se definen como p(no necesariamente se llama p, es el nombre de nuestra variable puntero) = &(variable a apuntar). 

> ¿Cómo se almacena en C++ la dirección de memoria de una variable?
Usamos "&" por que es lo que nos permite almacenar la dirección de memoria en otra variable

> ¿Cómo se escribe el contenido de la variable a la que apunta un puntero?
Recordemos que el puntero solo guarda direcciones de las variables, mas no el valor de las variables en si. si quisieramos acceder para hacer uso de la variable a la que el puntero esta apuntando, hacemos uso del *

[Código 1]
```c++
int a = 10;
int b = 5;
int *p;
p = &a;
b = *p;
```
-  **predice, ejecuta, observa y reflexiona** 𖤓 ☆ ☼ ⋆⋅**

**[PREDICE]** El código debería poder leer y reemplazar algunos valores entre a y b

**[EJECUTA]** El código tiene dos variables, a = 10 y b = 5. El puntero se declara y apunta a la variable a guardando su direccion, y luego, gracias al "*", hace que b adquiera mismo valor que a, es decir b = 10

**[OBSERVA]** Es bastante facil reemplazar las variables

**[REFLEXIONA]** Es bastante util el uso del "*" con los punteros porque nos deja acceder constantemente a las variables sin necesidad de llamarlas

>Las siguientes lineas de código son una simulación de este mismo código en lenguaje ensamblador

```.asm
@10
D=A
@a
M=D

@a
D=A
@p
M=D

@20
D=A
@p
A=M
M=D
```
[Código 2]
```c++
int a = 10;
int* p;
p = &a;
*p = 20;
```
-  **predice, ejecuta, observa y reflexiona** 𖤓 ☆ ☼ ⋆⋅**

**[PREDICE]** El código parece leer y apuntar una variable para luego modificarla

**[EJECUTA]** El código tiene la variable a = 10, el puntero se declara y apunta a la variable a, para luego, gracias al "*" pódamos acceder al valor de la variable a, es decir, el 10 y modificarlo en la última línea. haciendo que quede a = 20

**[OBSERVA]** No sabia que se podian alterar directamente las variables, es facil de hacer. Tengo que acostumbrarme a leer bien el orden de las variables por que a veces me confunco

**[REFLEXIONA]** Es bastante util detalle de poder alterar directamente el valor de las variables sin siquiera llamarlas directamente
