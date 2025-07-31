# Unidad 2

## 🔎 Fase: Set + Seek

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@SCREEN
M=1
```
```c++
screen = 1;
```
<img width="388" height="38" alt="image" src="https://github.com/user-attachments/assets/40d4efa1-15a2-46c0-b22a-d35c1e588f41" />

### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  *predice, ejecuta, observa y reflexiona*

PREDICE: Gracias a la etiqueta SCREEN, el compuatdor debe iniciar la posición de la pantalla, es decir, 16384. Luego asignamos un 1 en uno de los 16 dígitos de la posición 16384

EJECUTA: En efecto, ttras pasar el código a NAND2tetris, la etiqueta SCREEN se transporma en 16384, luego lo lee y A pasa a dicho valor. Luego M=1 asigna un valor al 16384 de RAM que acabamos de leer y asigna el 1 en el último valor de los 16 ceros que hay

OBSERVA: El código funciona con normalidad. el pixel es super chiquito, pero funciona

REFLEXIONA:

### **ACTIVIDAD 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@SCREEN
M=-1
```
```c++
screen = -1;
screen = 0xFFF;
```
<img width="358" height="30" alt="image" src="https://github.com/user-attachments/assets/fe1fd9e0-16af-4807-8311-1ef13ec75358" />

### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  *predice, ejecuta, observa y reflexiona*
PREDICE: Gracias a la etiqueta SCREEN, el compuatdor debe iniciar la posición de la pantalla, es decir, 16384. Luego asignamos un -1, el cual representa un numero enorme en positivos, y llena las 16 casillas de ese lugar 

EJECUTA: En efecto, ttras pasar el código a NAND2tetris, la etiqueta SCREEN se transporma en 16384, luego lo lee y A pasa a dicho valor. Luego M=-1 asigna un valor al 16384 de RAM que acabamos de leer y llena todas las 16 casillas

OBSERVA: Se ve claramente la linea con los 16 pixeles llenos

REFLEXIONA: No es necesario llenar todas las 16 casillas una por una. podemos poner un numero grande directamente 

### ACTIVIDAD 03༓☾∘∙•⋅⋅⊰⋅•⋅**
```
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

Memoria[ CONTADOR+SCREEN] = 0;
CONTADOR = CONTADOR +1;

Memoria[ CONTADOR+SCREEN] = -1;
```
### ACTIVIDAD 03༓☾∘∙•⋅⋅⊰⋅•⋅**

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
```
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
### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  *Conclusiones*

### ACTIVIDAD 04༓☾∘∙•⋅⋅⊰⋅•⋅**

-  *¿Cómo se declara un puuntero?*
-  *¿Cómo se define el puntero en C++?
-  *¿Cómo se almacena en C++ la dirección de memoria de una variable? Con el operador &*
-  *¿Cómo se escribe el contenido de la variable a la que apunta un puntero? Con el operador "*"*

### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  *predice, ejecuta, observa y reflexiona*

PREDICE:

EJECUTA:

OBSERVA:

REFLEXIONA:


////
PUNTERO: 
  ++++En esa variable se guardan direcciones

Int i;
  i es una variable 
  En i se guarda un valor --> un entero 
  
int* ptr; ---> Declaro puntero: ptr
  ptr es una variable que guarda direcciones de otras variables
  declaro la variable

& definicion de la  variable

se puede leer con el puntero
int j = ptr;

int j = *ptr; guardamos en j el valor de la variable a la qque estamos apuntando





///
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
///

HACES HASTA LA ACTIVIDAD 5 
YOU HAVE A LOT OF THINGS TO DO 
