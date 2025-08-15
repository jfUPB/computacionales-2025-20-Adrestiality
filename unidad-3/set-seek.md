# Unidad 3

## 🔎 Fase: Set + Seek

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```c++
#include <iostream>

int sum(int a, int b)
{
    return a + b;
}

int main()
{
    int a = 5;
    int b = 7;
    std::cout << "La suma de " << a << " y " << b << " es " << sum(a, b) << "\n";
}
```
>-  [¿Para qué sirven los breakpoints?]  
> Nos permiten poner una especie de pausa a la hora de depurar nuestro código. Lo que a su vez, nos permite revisar en otra ventana la depuración paso a paso.

>-  [¿Para qué se usa la ventana de depuración Autos?]  
> Es una ventana donde podemos ver paso a paso lo que sucede con las variables en el código de c++. Es muy parecido al compilador de lenguaje ensamblador.

## **ACTIVIDAD 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```c++
#include <iostream>

using namespace std;

// Función que modifica el parámetro pasado por valor
void modificarPorValor(int n) {
    cout << "Dentro de modificarPorValor, valor inicial: " << n << endl;
    n += 5;
    cout << "Dentro de modificarPorValor, valor modificado: " << n << endl;
}

// Función que modifica el parámetro pasado por referencia
void modificarPorReferencia(int &n) {
    cout << "Dentro de modificarPorReferencia, valor inicial: " << n << endl;
    n += 5;
    cout << "Dentro de modificarPorReferencia, valor modificado: " << n << endl;
}

// Función que modifica el parámetro utilizando punteros
void modificarPorPuntero(int *n) {
    cout << "Dentro de modificarPorPuntero, valor inicial: " << *n << endl;
    *n += 5;
    cout << "Dentro de modificarPorPuntero, valor modificado: " << *n << endl;
}

int main() {
    int a = 10;
    int b = 10;
    int c = 10;

    cout << "Valor inicial de a (paso por valor): " << a << endl;
    cout << "Valor inicial de b (paso por referencia): " << b << endl;
    cout << "Valor inicial de c (paso por puntero): " << c << endl;

    cout << "\nLlamando a modificarPorValor(a)..." << endl;
    modificarPorValor(a);
    cout << "Después de modificarPorValor, valor de a: " << a << endl;

    cout << "\nLlamando a modificarPorReferencia(b)..." << endl;
    modificarPorReferencia(b);
    cout << "Después de modificarPorReferencia, valor de b: " << b << endl;

    cout << "\nLlamando a modificarPorPuntero(&c)..." << endl;
    modificarPorPuntero(&c);
    cout << "Después de modificarPorPuntero, valor de c: " << c << endl;

    return 0;
}
```
>- [Predicción: antes de ejecutar el programa, predice la salida de cada función y explica el resultado]  
> Viéndolo muy por encima, es claro que tratamos de modificar los valores de las variables a, b y c por medio de tres maneras diferentes.
>  1. "modificarPorValor" probablemente sea de tratar directamente las variables y modificarlas  
>
>  2. "modificarPorReferencia" quizas tengamos quecrear refrencias o variables que sirvan a modo de representación de las originales y que esas sean las que se modifiquen  
>
>  3. "modificarPorPuntero" evidentemente tratará del uso de punteros por los caules podremos acceder directamente a la variable y modificarla
>

>- [¿Qué diferencias observas en el comportamiento de a, b y c tras cada llamada?]
> Las 3 variables originalmente valen lo mismo. Entonces la diferencia debe estar en qué tipo de modificaciones u ocasiones se les suma o se les resta

>- [¿Por qué ocurre esta diferencia?]
> Debido a los modificadores. Todos realizan acciones diferentes que parecen implicar el uso directo de las variables o de copias de este

>- [[RESULTADOS DESPUÉS DE EJECUTAR EL CÓDIGO]]
> 1. Comprendí que "modificarPorValor" lo que hace es crear una copia de la variable y trabajar por encima de esa copia, dejando la variable original intacta  
> 2. También "modificarPorReferencia" lo que hace es crearle simplemente un alias a la variable pero se sigue trabajando con la misma variable. Solo es un apodo, nada más  
> 3. Finalmente, "modificarPorPuntero" si funcionaba tal cual como lo esperaba. Accede a traves del puntero al valor de la variable

```c++
#include <iostream>

using namespace std;

void swapPorValor(int a, int b) {

	int x = a;
	a = b;
	b = x;

	cout << "Dentro de swapPorValor (copias): a = " << a << ", b = " << b << endl;
}

void swapPorReferencia(int& a, int& b) {

	int x = a;
	a = b;
	b = x;
}

void swapPorPuntero(int *a, int *b) {

	int x = *a;
	*a = *b;
	*b = x;
}

int main() {
	int a = 5;
	int b = 8;

	cout << "Valor inicial de a (swap por valor): " << a << endl;
	cout << "Valor inicial de b (swap por valor): " << b << endl;

	cout << "\nLlamando a swapPorvalor(a,b)..." << endl;
	swapPorValor(a, b);
	cout << "\nDespues de swapPorvalor, valor de (a): " << a << endl;
	cout << "Despues de swapPorvalor, valor de (b): " << b << endl;

	cout << "----------------------------------------------" << endl;

	cout << "\nValor inicial de a (swap por referencia): " << a << endl;
	cout << "Valor inicial de b (swap por refrencia): " << b << endl;

	cout << "\nLlamando a swapPorReferencia(a,b)..." << endl;
	swapPorReferencia(a, b);
	cout << "\nDespues de swapPorReferencia, valor de (a): " << a << endl;
	cout << "Despues de swapPorReferencia, valor de (b): " << b << endl;

	cout << "----------------------------------------------" << endl;

	cout << "\nValor inicial de a (swap por puntero): " << a << endl;
	cout << "Valor inicial de b (swap por puntero): " << b << endl;

	cout << "\nLlamando a swapPorPuntero(a,b)..." << endl;
	swapPorPuntero(&a, &b);
	cout << "\nDespues de swapPorPuntero, valor de (a): " << a << endl;
	cout << "Despues de swapPorPuntero, valor de (b): " << b << endl;

	return 0;
}
```
<img width="442" height="495" alt="image" src="https://github.com/user-attachments/assets/22f18fb9-4c47-448d-b104-461eb6951e38" />

>- [EXPLICACIÓN DEL CÓDIGO]  
> 1. La función "swapPorValor" basicamente crea una copia del valor de la variable y es la que modifica. Por ende cuando lo imprimimos en la consola, realmente lo que imprime son las variables normales sin modificar. En la línea "cout << "Dentro de swapPorValor (copias): a = " << a << ", b = " << b << endl;" imprimimos el valor de las copias de las variables que intercambiamos
>
> 2. La función "swapPorReferencia" es por así decirlo, la funcion más literal. Intercmbia los valores directamente y ya
>
> 3. la función "swapPorPuntero" , como lo dice su nombre, crea punteros que intercambian las dos variables. Eso sí, para este punto del código, las variables ya estaban intercambiadas por el "swapPorReferencia" por lo que los punteros simplemente reordenaron nuevamente los valores de las variables originales

## **ACTIVIDAD 03 ༓☾∘∙•⋅⋅⊰⋅•⋅**

```c++
#include <iostream>
#include <cstdlib>

using namespace std;

// Variables globales
int global_inicializada = 42;
int global_no_inicializada;

// Constante global
const char* const mensaje_ro = "Hola, memoria de solo lectura";

// Función de ejemplo que muestra la dirección de su variable local estática
void funcionConStatic() {
    static int var_estatica = 100;
    cout << "Dirección de var_estatica (static): " << &var_estatica << endl;
}

// Función que asigna memoria dinámica (heap)
int* crearArrayHeap(int tam) {
    int* arr = new int[tam];
    for (int i = 0; i < tam; i++) {
        arr[i] = i;
    }
    return arr;
}

// Una función simple para representar el código (se encontrará en la región de código)
int suma(int a, int b) {
    int c = a + b; // "c" es una variable local (stack)
    return c;
}

int main() {
    // Variable local (stack)
    int a = 10;
    int b = 20;
    int c = suma(a, b);

    cout << "Resultado de suma(a, b): " << c << endl;
    cout << "Dirección de variable local 'a': " << &a << endl;
    cout << "Dirección de variable local 'b': " << &b << endl;
    cout << "Dirección de la variable local 'c' (resultado): " << &c << endl;

    // Variables globales
    cout << "Dirección de 'global_inicializada': " << &global_inicializada << endl;
    cout << "Dirección de 'global_no_inicializada': " << &global_no_inicializada << endl;

    // Constante global (solo lectura)
    cout << "Dirección de 'mensaje_ro' (zona de solo lectura): " << static_cast<const void*>(mensaje_ro) << endl;

    // Llamada a función que tiene variable estática
    funcionConStatic();

    // Uso del Heap: asignación dinámica
    int tamArray = 10;
    int* arrayHeap = crearArrayHeap(tamArray);
    cout << "Dirección del primer elemento del array asignado en Heap: " << arrayHeap << endl;
    for (int i = 0; i < tamArray; i++) {
        cout << "arrayHeap[" << i << "] = " << arrayHeap[i]
            << " en " << (arrayHeap + i) << endl;
    }
    delete[] arrayHeap; // Liberamos la memoria dinámica

    return 0;
}
```
```cpp
+-----------------------------------------------------------------+
| [TEXT]                                                          |
|  main                                                           |
|  suma                                                           |
|  crearArrayHeap                                                 |
|  funcionConStatic                                               |
+-----------------------------------------------------------------+
| [VARIABLES GLOBALES Y ESTÁTICAS]                                |
| int global_inicializada = 42;                                   |
| int global_no_inicializada;                                     |
| const char* const mensaje_ro = "Hola, memoria de solo lectura"; |
| static int var_estatica = 100;  // en funcionConStatic()        |
+-----------------------------------------------------------------+
| [HEAP]                                                          | 
| int* arr = new int[tam];  // en crearArrayHeap()                |
+-----------------------------------------------------------------+
| [STACK]                                                         |
| int a = 10;                                                     |
| int b = 20;                                                     |
| int c = suma(a, b);                                             |
| int c = a + b;                                                  |
| int* arr;                                                       | 
| int i;                                                          |
+-----------------------------------------------------------------+
```
## **ACTIVIDAD 04 ༓☾∘∙•⋅⋅⊰⋅•⋅**
-	[EXPERIMENTO 1]
```c++
#include <iostream>
#include <cstdlib>

using namespace std;


int main() {
    // Variable local (stack)
    int a = 10;
    int b = 20;

    /**********************************************************
        EXPERIMENTO 1
    ***********************************************************/

    void* ptr = reinterpret_cast<void*>(&main);
    cout << "Voy a modificar la memoria en la dirección: " << ptr << endl;
    *reinterpret_cast<int*>(ptr) = 0;

    /********************************************************/

    return 0;
}
```
>- [¿Qué ocurre? ¿Por qué?]  
> Lo que planeta este código es tratar de poner un 0 en una dirección del main, que se encuentra en el bloque TEXT, que son solo de lectura y no pueden modificarse

-	[EXPERIMENTO 2]
```c++
#include <iostream>
#include <cstdlib>

using namespace std;

// Constante global
const char* const mensaje_ro = "Hola, memoria de solo lectura";


int main() {
    // Variable local (stack)
    int a = 10;
    int b = 20;


    /**********************************************************
        EXPERIMENTO 2
    ***********************************************************/

    char* ptr = (char*)&mensaje_ro;
    cout << "Voy a modificar la memoria en la dirección: " << ptr << endl;
    *ptr = 0;

    /********************************************************/

    return 0;
}
```
>- [¿Qué ocurre? ¿Por qué?]  
> En este código lo que se pretende es modificar la memoria de la dirección del mensaje de solo lectura. El problema esta en, valga la redundancia, que el texto está escrito en una funcion de solo lectura. Asi que el propio código trata de modificarla ilegalemnte con punteros pero acabamos llegando a una especie de funcion indefinida que genera error

-	[EXPERIMENTO 3]
```c++
#include <iostream>
#include <cstdlib>

using namespace std;

// Variables globales
int global_inicializada = 42;
int global_no_inicializada;


int main() {
    // Variable local (stack)
    int a = 10;
    int b = 20;

    /**********************************************************
        EXPERIMENTO 3
    ***********************************************************/

    cout << "global_inicializada: " << global_inicializada << endl;
    cout << "global_no_inicializada: " << global_no_inicializada << endl;


    global_inicializada = 69;
    global_no_inicializada = 666;

    cout << "global_inicializada: " << global_inicializada << endl;
    cout << "global_no_inicializada: " << global_no_inicializada << endl;

    /********************************************************/

    return 0;
}
```
>- [¿Qué ocurre? ¿Por qué?]  
>Este código nos muestra el como podemos manejar las variables globales. Cuando se ejecuta el código e inicializamos las variables, iniciamos una en 42, pero la segunda a la que no se le asignó un numero, se le asigna automáticamente a 0. Luego ambos valores son modificados a 69 y 666 respectivamente

-	[EXPERIMENTO 4]
```c++
#include <iostream>
#include <cstdlib>

using namespace std;

// Función de ejemplo que muestra la dirección de su variable local estática
void funcionConStatic() {
    static int var_estatica = 100;
    cout << "Dirección de var_estatica (static): " << &var_estatica << endl;
}


int main() {
    // Variable local (stack)
    int a = 10;
    int b = 20;

    /**********************************************************
        EXPERIMENTO 4
    ***********************************************************/

    var_estatica = 42;

    cout << "var_estatica: " << var_estatica << endl;

    /********************************************************/
    return 0;
}
```
>- [¿Qué ocurre? ¿Por qué?]  
>Este código ni siquiera ejecuta, debido a que estamos tratando de modificar el valor de una variable estática que no se puede llamar o modificar desde el main
>- [¿Qué pasa con las variables locales estáticas?]  
> Estas solo se pueden modificar dentro de la funcion o bloque donde están declaradas. De resto no podremos ni llamarla desde el main, ya no está ni siquiera en el stack, esta en las variables globales realmente

-	[EXPERIMENTO 5]
```c++
#include <iostream>
#include <cstdlib>

using namespace std;

// Función de ejemplo que muestra la dirección de su variable local estática
void funcionConStatic() {
    static int var_estatica = 100;
    cout << "var_estatica: " << var_estatica << endl;
    var_estatica++;
}

void funcionSinStatic() {
    int var_no_estatica = 100;
    cout << "var_no_estatica: " << var_no_estatica << endl;
    var_no_estatica++;
}


int main() {
    // Variable local (stack)
    int a = 10;
    int b = 20;

    /**********************************************************
        EXPERIMENTO 5
    ***********************************************************/

    for (int i = 0; i < 5; i++) {
        cout << "Iteración " << i << endl;
        funcionSinStatic();
        funcionConStatic();
    }

    /********************************************************/

    return 0;
}
```
>- [¿Qué ocurre? ¿Por qué?]  
>Este código nos muestra las diferencias entre las variables estáticas y no estáticas. Para ello podemos ver como la varia estática, dado a que no se destruye en cada llamado y el contador le sigue sumando, mientras que la no estática se destruye en cada llamado, y aunque se le aplique el contador, se destruye al salir del bloque
>- [Ves alguna diferencia entre las variables locales estáticas y no estáticas?]  
> Las estáticas no se destruyen despues de cada función, las no estáticas si
>- [¿Qué pasa con las variables cada que entras y sales de la función?]  
>  Las no estáticas se destruyen y es como si no le hubiesen aplicado nada. Las estáticas permanecen

-	[EXPERIMENTO 6]
```c++
#include <iostream>
using namespace std;

int main() {
    // Tamaño del arreglo dinámico
    int tam = 5;

    // Asignar memoria en el Heap para un arreglo de enteros
    int* arrayHeap = new int[tam];

    // Inicializar y mostrar los valores y direcciones de memoria
    for (int i = 0; i < tam; i++) {
        arrayHeap[i] = (i + 1) * 10;
        cout << "arrayHeap[" << i << "] = " << arrayHeap[i]
            << " en dirección " << (arrayHeap + i) << endl;
    }

    // Liberar la memoria asignada en el Heap
    delete[] arrayHeap;

    /**********************************************************
        EXPERIMENTO 6
    ***********************************************************/

    cout << arrayHeap[0] << endl;
	//LINEA ERRONEA. ESTAMOS LLAMANDO UN PUNTERO A UNA MEMORIA QUE BORRAMOS EN LA LÍNEA ANTERIOR


    /********************************************************/


    return 0;
}
```
>- [¿Qué ocurre? ¿Por qué?]    
>Basicamente creamos un arreglode tamaño 5, le asignamos memoria y valores, luego liberamos la memoria y finalmente tratamos de llamar por medio de un puntero una memoria que acabamos de borrar, lo que genera error
>- [¿Qué diferencias notas entre el comportamiento y la gestión del Heap en comparación con el Stack?]    
>  Noto que el Stack se libera automáticamente despues de terminada cada función, mientras que el Heap, aunque parece tener más capacidad, se debe borrar automáticamente
>- [¿Qué consecuencias tendría no liberar la memoria reservada con new?]  
>  Podríamos quedarnos sin memoria
>- [¿Qué pasa con las variables cada que entras y sales de la función?]  
>  Siguen existiendo hasta que las borremos o liberemos
>- [¿Por qué es importante usar delete[] al liberar memoria asignada para un arreglo?]  
>  Para liberar la memoria y que no se ocupe

## **ACTIVIDAD 05 ༓☾∘∙•⋅⋅⊰⋅•⋅**

