# Unidad 1
//esto es markdown// todo se guarda en .asm
## 🔎 Fase: Set + Seek

### Actividad 01
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
##### *¿Qué crees que haga este programa?
La verdad no estoy segura, pero juzgando por las letras, que asumo que son variables, parece como si se estuviese sumano lo mismo... 

#### Experimento [1]
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
##### *¿Qué sucede?  
la cpu, que parece ser un contador, aumenta a medida que vamos avanzando en las instrucciones. tambien descubri que que las instrucciones con @cambian el valor en A...  entonces en varias instrucciones cambia su valor en realidad.
##### *¿Qué valor se almacena en la dirección de memoria 16? 
se almacena un 3 en la dirección 16
##### *¿Por qué crees que es ese valor? 
por la linea que dice M=D, en la memoria se almacena un 3 (el valor de D) en la posicion 16 (el numero de A)
##### *¿Qué instrucciones se ejecutan en cada ciclo Fetch-Decode-Execute?
se recuperan los datos, se decodifican y fialmente ejecuta cada orden en cada una de las lineas
#####  *¿Qué cambios observas en el contenido de la memoria y los registros?
cambian de valor dependiendo de A y D, y asi mismo A y D cambian de valor dependiendo de las instrucciones que hay en cada linea.

#### Experimento [2]
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

#### Bitácora
##### *¿Qué diferencia hay entre los datos almancenados en la memoria ROM y en la RAM?
los datos almacenados en la mamoria RAM son termporales y los de ROM son permanentes.
