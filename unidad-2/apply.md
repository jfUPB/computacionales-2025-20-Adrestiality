# Unidad 2


## 🛠 Fase: Apply

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**

```c++
int arr[] = {1,2,3,4,5,6,7,8,9,10};
int sum = 0;

for (int j = 0; j < 10; j++) {
    sum = sum + arr[j];
}
```
```.asm
// [ARREGLO] //

@1        // Carga el valor 1 en el registro A  
D=A       // Guarda el valor 1 en el registro D  
@16       // Apunta a la dirección de memoria 16 (primer elemento del arreglo)  
M=D       // Guarda el valor 1 en RAM[16]  

@2        // Carga el valor 2 en el registro A  
D=A       // Guardar el valor 2 en el registro D  
@17       // Apuntar a la dirección de memoria 17  
M=D       // Guardar el valor 2 en RAM[17]  

@3        // Cargar el valor 3 en el registro A  
D=A       // Guardar el valor 3 en el registro D  
@18       // Apuntar a la dirección de memoria 18  
M=D       // Guardar el valor 3 en RAM[18]  

@4        // Cargar el valor 4 en el registro A  
D=A       // Guardar el valor 4 en el registro D  
@19       // Apuntar a la dirección de memoria 19  
M=D       // Guardar el valor 4 en RAM[19]  

@5        // Cargar el valor 5 en el registro A  
D=A       // Guardar el valor 5 en el registro D  
@20       // Apuntar a la dirección de memoria 20  
M=D       // Guardar el valor 5 en RAM[20]  

@6        // Cargar el valor 6 en el registro A  
D=A       // Guardar el valor 6 en el registro D  
@21       // Apuntar a la dirección de memoria 21  
M=D       // Guardar el valor 6 en RAM[21]  

@7        // Cargar el valor 7 en el registro A  
D=A       // Guardar el valor 7 en el registro D  
@22       // Apuntar a la dirección de memoria 22  
M=D       // Guardar el valor 7 en RAM[22]  

@8        // Cargar el valor 8 en el registro A  
D=A       // Guardar el valor 8 en el registro D  
@23       // Apuntar a la dirección de memoria 23  
M=D       // Guardar el valor 8 en RAM[23]  

@9        // Cargar el valor 9 en el registro A  
D=A       // Guardar el valor 9 en el registro D  
@24       // Apuntar a la dirección de memoria 24  
M=D       // Guardar el valor 9 en RAM[24]

@10       // Cargar el valor 10 en el registro A  
D=A       // Guardar el valor 10 en el registro D  
@25       // Apuntar a la dirección de memoria 25  
M=D       // Guardar el valor 10 en RAM[25]  

// [SUMATORIA] //

@0        // Cargar el valor 0 en el registro A  
D=A       // Guardar el valor 0 en el registro D  
@26       // Apuntar a la dirección donde se almacenará la suma total  
M=D       // Inicializar RAM[26] = 0 (sumatoria = 0)

// [PUNTERO] //

@16       // Cargar dirección base del arreglo  
D=A       // Guardar 16 en el registro D  
@27       // Apuntar a la dirección del puntero (RAM[27])  
M=D       // Inicializar puntero en RAM[27] con 16

// [CONTADOR] //

@10       // Cargar el número de elementos del arreglo  
D=A       // Guardar 10 en el registro D  
@28       // Apuntar al contador (RAM[28])  
M=D       // Inicializar contador con 10  

// [LOOP] //

(LOOP)    // Etiqueta de inicio del bucle  

@28       // Apuntar al contador  
D=M       // Cargar el valor del contador en D  
@END      // Apuntar a la etiqueta END  
D;JEQ     // Si D == 0 (contador agotado), saltar a END  

@27       // Apuntar al puntero  
A=M       // A = valor del puntero (dirección del arreglo actual)  
D=M       // D = *puntero (valor del arreglo)  

@26       // Apuntar a sumatoria 
M=D+M     // sumatoria = sumatoria + *puntero  

@27       // Apuntar al puntero nuevamente  
M=M+1     // puntero = puntero + 1  

@28       // Apuntar al contador  
M=M-1     // contador = contador - 1  

@LOOP     // Volver al inicio del bucle  
0;JMP     // Salto incondicional a LOOP  

(END)     // Etiqueta de finalización  
@END      // Apuntar a END  
0;JMP     // Salto infinito para detener
```

### ** Explicación del código ** 𖤓 ☆ ☼ ⋆⋅**
-  [ARREGLO DE NÚMEROS]
Dentro del código de c++ podemos ver que lo primero que hacen es generar un array con un conjunto de números del 1 al 10. Para nosotros no es tan facil como simplemente ordenarle al compuatdor que los guarse, sino que aquí tenemos que guardarlos manualmente. Para ello empezamos a guardar cada uno de los números uno por uno en los espacios de la RAM, desde RAM [16] hasta RAM [25]

-  [SUMATORIA]
Luego de asignar nuestro conjunto de números, tenemos que asignar también un espacio de la RAM donde quedará nuestra suma final, tal como lo pide el código en c++. Para ello, ponemos un 0 en la RAM [26]

-  [PUNTERO]
Asignamos a otra valor de la RAM, en este caso RAM [27] nuestro puntero, con el primero valor de nuestro arreglo, es decir, con un 1. Más adelante, el contador trabajará de amno con el puntero. El puntero se encarga de ir sumano los números siguientes, el contador se encargará de la cantidad de números que faltan por usarse y el que determina si ya terminamos de sumar o no

-  [CONTADOR]
En la RAM [28] creamos nuestro contador, con la cantidad máxima de variables, es decir, 10 (Son 10 valores que van del 1 al 10). Cuando llegue al LOOP, el programa verificará si el contador es igual o diferente de 0. Si es igual a 0, quiere decir que el contador esta vacío y que ya no hay más numeros para sumar, sino, quiere decir que el contador aún tiene valores, así que deberá seguir

-  [LOOP]
Se encarga de verificar si RAM [28], es decir, el CONTADOR es igual o diferente de 0. Si es igual a 0, lo lleva a END, que es donde acaba todo en saltos infinitos, sino, no hace el salto, y el puntero seguira trayendo los valores del arreglos y sumandolos con el valor de SUMATORIA actual, y de igual manera al CONTADOR se le va a ir disminuyendo el valor
