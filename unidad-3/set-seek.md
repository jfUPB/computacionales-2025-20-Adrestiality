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

