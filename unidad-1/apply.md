# Unidad 1

## 🛠 Fase: Apply

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 03 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@5	// cargamos el valor 5 en A
D=M	// cargamos cargamos D con el valor del registro de la RAM 5 
@10	// cargamos el valor 10 en A
D=D-A	// restamos el valor de A, es decir, 10; con D, es decir, 5; y lo guardamos nuevamente en D. D = -10 

@MENOR	// etiqueta MENOR
D;JLT	// Si D es menor que 0, seguimos en la etiqueta MENOR
(MAYOREQ)// Si no saltamos en el paso anterior seguimos aqui, es porque D era mayor que 0, es decir, D no es negativo...
@7	// cargamos el valor 7 en A
M=0	// guardamos un 0 en la ubicacion 7
@LOOP	// etiqueta LOOP
0;JMP	// salto simple

(MENOR)	// etiqueta MENOR
@7	// cargamos el valor 7 en A
M=1	// guardamos un 1 en la ubicacion 7
@LOOP	// etiqueta LOOP
0;JMP	// salto simple
```
### **ACTIVIDAD 04 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@1      // cargamos el valor 1 en A
D=A     // guardamos el 1 en el registro D
@i      // direccionamos a una posición libre de la RAM, variable i (@16)
M=D     // guardamos 1 en i, i = 1    
@0	// cargamos el valor 0
D=A	// guardamos el 0 en el registro D
@sum	// direccionamos a una posición libre de la RAM, variable sum (@17)
M=D     // guardamos 0 en sum, sum = 1        

(LOOP)	// etiqueta inicio del loop
@i	// llamamos la variable i = 1 
D=M	// cargamos D con el valor de i, D = 1


@sum	// llamamos la variable sum = 0
D=D+M	// sumamos sum y D, y su valor se guarda nuevamente en D, 0 + 1 = 1


@sum	// llamamos la variable sum = 0
M=D	// actualizamos el valor de sum con el nuevo valor de D, sum = 1


@i	// llamamos la variable i
M=M+1	// sumamos 1 al valor de la memoria, es decir, i = 1 + 1, i = 2


@i	// llamamos la variable i = 2
D=M	// cargamos D con el valor de i, D = 2 
@6	// cargamos el valor 6 en A. lo hacemos para comparar si ya superó 5
D=D-A   // restamos el valor de A, es decir, 6 con el valor de D, es decir, i; y lo reemplazamos      
@LOOP	// etiqueta fin del loop
D;JLT   // evaluamos el registro D, es decir, i. si su valor es menor que 0, saltamos a jump, sino, seguimos. 

@sum	// llamamos la variable sum
D=M	// cargamos D con el valor de sum, D = 1
@12	// cargamos el valor 12 en A
M=D	// guardamos en la memoria el 12

(END)	// etiqueta fin programa
@END	// etiqueta fin programa
0;JMP  // saltamos infinitamente en END para que el programa no se siga ejecutando si ya termino.
```
