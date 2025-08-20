# Unidad 3

## 🛠 Fase: Apply
─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

## **ACTIVIDAD 06 ༓☾∘∙•⋅⋅⊰⋅•⋅**

```c++
#include <iostream>
using namespace std;

class Punto {
public:
    int x;
    int y;

    // Constructor
    Punto(int _x, int _y) : x(_x), y(_y) {
        cout << "Constructor: Punto(" << x << ", " << y << ") creado." << endl;
    }

    // Destructor
    ~Punto() {
        cout << "Destructor: Punto(" << x << ", " << y << ") destruido." << endl;
    }

    // Método para imprimir valores
    void imprimir() {
        cout << "Punto(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    // Coloca un breakpoint en la siguiente línea
    Punto p(10, 20);

    // Muestra el contenido del objeto
    p.imprimir();

    // Utiliza el depurador para inspeccionar 'p', observa la dirección de memoria y el valor de x e y.
    return 0;
}
```

```c#
using System;

public class Punto
{
    public int x;
    public int y;

    public Punto(int _x, int _y)
    {
        x = _x;
        y = _y;
        Console.WriteLine($"Constructor: Punto({x}, {y}) creado.");
    }

    ~Punto()
    {
        Console.WriteLine($"Destructor: Punto({x}, {y}) destruido.");
    }

    public void Imprimir()
    {
        Console.WriteLine($"Punto({x}, {y})");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Punto p = new Punto(10, 20);
        p.Imprimir();
    }
}
```

>-  [Abre la calculadora de Windows y selecciona el modo de programador. Cambia a modo hexadecimal. Escribe 0a ¿Qué valor en decimal obtienes? Escribe 14 ¿Qué valor en decimal obtienes? ¿Qué observas?]  
<img width="330" height="538" alt="image" src="https://github.com/user-attachments/assets/17bec7a0-31d1-4ed1-8e09-a275d42a9904" />
<img width="320" height="533" alt="image" src="https://github.com/user-attachments/assets/5fc1d911-615e-453d-a023-8e0d4b75535a" />  

>-  [La mayoría de las arquitecturas modernas son little-endian. Si la arquitectura de tu computador fuera big-endian, ¿Cómo quedarían almacenados los bytes en la memoria de p?]    
Al parecer, un sistema big-endian almacena el byte más grande de una palabra en la dirección de memoria más pequeña y el byte menos significativo en la más grande. Si en liitle-endian la ubicación se veia así "0A 00 00 00 14 00 00 00", creo que en big-endian se vería así "00 00 00 0A 00 00 00 14"

>1.  [¿Cuál es la diferencia entre un constructor y un destructor en C++?]  
> Constructor: se ejecuta automáticamente al crear un objeto ya que su función es inicializar sus atributos  
> Destructor: su función es liberar memoria despues de usado el objeto  
>

>2.  [¿Cuál es la diferencia entre un objeto y una clase en C++?]  
> Clase: es el espacio donde se definen los objetos y sus características  
> Objeto: es una entidad concreta de una clase, con valores propios en memoria  

>3.  [¿Qué diferencia notas entre el objeto Punto en C++ y C#?]  
> En C++, 2Punto p(10, 20);" crea el objeto directamente en stack  
> En C#, "Punto p = new Punto(10, 20);" crea el objeto en heap y p es solo una referencia al objeto  

>4.  [¿Qué es p en C++ y qué es p en C#? (en uno de ellos p es un objeto y en el otro es una referencia a un objeto).]  
> En C++, p es el propio objeto  
> En C#, p es una referencia, como una especie de puntero al objeto en heap  

>5.  [¿En qué parte de memoria se almacena p en C++ y en C#?]  
> En C++, p está en el stack  
> En C#, la variable p (la referencia que deciamos hace un momento) está en el stack, pero el objeto Punto se guarda en heap  

>6.  [¿Qué observaste con el depurador acerca de p? Según lo que observaste ¿Qué es un objeto en C++?]  
> p tiene una dirección de memoria fija, donde estaán los valores de X y Y 
> En C++ un objeto es una zona de memoria concreta que contiene directamente sus atributos, no solo una referencia como en C#

## **ACTIVIDAD 07 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```c++
#include <iostream>
using namespace std;

class Punto {
public:
    int x;
    int y;

    // Constructor
    Punto(int _x, int _y) : x(_x), y(_y) {
        cout << "Constructor: Punto(" << x << ", " << y << ") creado." << endl;
    }

    // Destructor
    ~Punto() {
        cout << "Destructor: Punto(" << x << ", " << y << ") destruido." << endl;
    }

    // Método para imprimir valores
    void imprimir() {
        cout << "Punto(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    // Objeto en el stack
    Punto pStack(30, 40);
    pStack.imprimir();

    // Objeto en el heap
    Punto* pHeap = new Punto(50, 60);
    pHeap->imprimir();

    // Coloca breakpoints en la creación de pStack y pHeap
    // Inspecciona las direcciones de memoria de ambos objetos:
    // - pStack: dirección obtenida directamente.
    // - pHeap: la variable pHeap es un puntero que contiene la dirección del objeto en el heap.

    // Recuerda liberar la memoria del heap
    delete pHeap;

    return 0;
}
```
>1.  [Explicación de la diferencia entre objetos creados en el stack y en el heap.]    
> - Stack: la memoria se le asigna automáticamente cuando se entra a un bloque de código, asi mismo, se libera automáticamente al terminar su función. También tienen un tamaño limitado  
> - Heap: la memoria se debe asignar con una función new, así mismo, solo se puede liberar con la función delete. También tiene un tamaño muchisimo mayor a comparación al stack  

>2.  [pStack ¿Es un objeto o una referencia a un objeto?]    
> pStack es un objeto
>

>3.  [pHeap ¿Es un objeto o una referencia a un objeto? Si es una referencia, ¿A qué objeto hace referencia?]   
> pHeap es una referencia, como un puntero. Lo que guarda es la dirección del objeto real que vive en el heap
>

>4.  [Observa en Memory1 (Debug->Windows->Memory->Memory1) el contenido de la dirección de memoria de pHeap, recuerda escribir en la entrada de texto de Memory1 la dirección de memoria de &pHeap y presionar Enter. Compara el contenido de memoria con el contenido de pHeap en la pestaña de Locals (Debug->Windows->Locals). ¿Qué observas? ¿Qué significa esto?]    
> Al inspeccionar &pHeap se ve la dirección de memoria en el heap, donde esta el objeto punto  

## **ACTIVIDAD 08 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```c++
#include <iostream>
#include <string>
using namespace std;

class Punto {
public:
  string name;
    int x;
    int y;

    // Constructor
    Punto(string _name, int _x, int _y) : name(_name),x(_x), y(_y) {
        cout << "Constructor: Punto "<< name <<" (" << x << ", " << y << ") creado." << endl;
    }

    // Destructor
    ~Punto() {
        cout << "Destructor: Punto " << name << "(" << x << ", " << y << ") destruido." << endl;
    }

    // Método para imprimir valores
    void imprimir() {
        cout << "Punto "<< name << "(" << x << ", " << y << ")" << endl;
    }
};

void cambiarNombre(Punto p, string nuevoNombre) {
  p.name = nuevoNombre;
}

int main() {
    // Objeto original
    Punto original("original",70, 80);
    original.imprimir();
    cambiarNombre(original, "cambiado");
    original.imprimir();
    return 0;
}
```
>1.  [¿Qué ocurre después de llamar a la función cambiarNombre? ¿Por qué aparece el mensaje Destructor: Punto cambiado(70, 80) destruido.?]      
> Cuando llamas la funcion cambiarNombre, se crea una copia del Punto original, incluso cambiando su nombre. Asi mismo, este es detruido al terminar su función
>

>2.  [¿Por qué original sigue existiendo luego de llamar cambiarNombre?]      
> Porque el unico que se destruye es la copia. La copia del objeto no afecta al original
>

>3.  [¿En qué parte del mapa de memoria se encuentra original y en qué parte se encuentra p? ¿Son el mismo objeto?]     
> Ambos están en stack, pero son dos variables independientes con sus propios valores
>

```c++
///MODIFICAMOS LA FUNCIÓN CAMBIARNOMBRE//
void cambiarNombre(Punto& p, string nuevoNombre) {
  p.name = nuevoNombre;
}
```
>4.  [¿Qué ocurre ahora? ¿Por qué?]      
> Aquí ya no se hace una copia del objeto, sino un alias del objeto original. es decir, aunque llame al objeto desde el alias, se va a modificar el objeto original
>

```c++
///MODIFICAMOS CAMBIARNOMBRE Y EL MAIN///
void cambiarNombre(Punto* p, string nuevoNombre) {
  p->name = nuevoNombre;
}

int main() {
    // Objeto original
    Punto original("original",70, 80);
    original.imprimir();

    cambiarNombre(&original, "cambiado");
    original.imprimir();

    return 0;
}
```
>5.  [¿Qué ocurre ahora? ¿Por qué?]  
> Basicamente creamos p como un puntero hacia al mismo objeto original, es decir, cualquier cambio desde el puntero es un camcio directo a la variable original. En otras palabras, lo mismo que el punto anterior pero con punteros
>

>6.  [En este caso ¿Cuál es la diferencia entre pasar un objeto por valor, por referencia y por puntero?]  
> Realmente la definición no cambia, independientemente si trabajamos con objetos o no  
> Objeto por valor: Creamos copias independientes y se modifica dicha copia independiente  
> Objeto por referencia y por puntero: Se crea un alias o un puntero que modifica directamente la variable original  

## **ACTIVIDAD 09 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```c++
#include <iostream>
using namespace std;

class Contador {
public:
    int valor;
    static int total;

    // Constructor
    Contador(int v = 0) : valor(v) {
        total++;
        cout << "Contador creado. total de Contadores = " << total << endl;
    }

    // Destructor
    ~Contador() {
        cout << "Contador destruido. valor = " << valor << endl;
    }

    // Método para incrementar el contador de instancia
    void incrementar() {
        valor++;
    }
};

// Definición e inicialización del miembro estático
int Contador::total = 0;

int main() {
    // Crea varios objetos en el stack
    Contador c1(5);
    Contador c2(10);

    // Inspecciona con el depurador las direcciones de c1 y c2.
    // Observa que 'total' es compartido entre todos los objetos.

    c1.incrementar();
    c2.incrementar();

    cout << "c1.valor = " << c1.valor << endl;
    cout << "c2.valor = " << c2.valor << endl;
    cout << "Contador::total = " << Contador::total << endl;

    // Puedes también crear un objeto dinámico para comparar:
    Contador* c3 = new Contador(15);
    c3->incrementar();
    cout << "c3->valor = " << c3->valor << endl;

    // Coloca breakpoints en la creación de cada objeto y en las llamadas a 'incrementar()'
    // Observa cómo el miembro estático 'total' se comparte y no se almacena en el stack de cada objeto.

    delete c3;
    return 0;
}
```

>-  [Observa el contenido de los objetos en memoria (Debug->Windows->Memory->Memory 1). Recuerda escribir la dirección de memoria de cada objeto como &c1 por ejemplo. ¿Puedes observar el valor de los miembros valor y total?]      
> Si se escribe &c1 o &c2 se veran los datos de los miembros de la instancia valor, pero no se vera el ttal dentro de c1 o c2, ya que e,l total no forma parte del objeto, es un miembro estático. Así mismo, si se escribe la dirección en c3, se verán los valores del miembro del objeto en el heap
>

>-  [¿En dónde está almacenado el miembro valor y el miembro total de la clase Contador?]      
> Valor: es una instancia, por lo que está dentro de cada objeto (stack para c1 y c2, heap para c3)  
> Total: es un miembro estático, se guarda una sola vez donde están los datos estáticos del programa, es decir, junto con las variables globales  
>

>1.  [¿Qué puedes concluir de los miembros estáticos y de instancia de una clase en C++? ¿Cómo se gestionan en memoria? ¿Qué ventajas y desventajas tienen? ¿Cuándo es útil utilizarlos?]    
> Miembros Estáticos: Solo existen una vez para toda la clase y se guardan en las variables globales    
> Miembros de instancia: Aquí, cada objeto tiene su propia copia, donde se gestionan la memoria del objeto en stack, donde funcionan como datos propios de cada objeto
>

>2.  [En el programa, en qué segmento de memoria se están almacenando c1, c2, c3 y Contador::total? Ten especial cuidado con la respuesta que das para el caso de c3, piensa de nuevo, qué es c3 y qué está almacenando. Ahora, responde de nuevo, en qué segmento de la memoria se está almacenando c3 y en qué segmento de la memoria se está almacenando el objeto al que apunta c3.]    
> c1: objeto en stack  
> c2: objeto en  stack  
> c3: puntero en el stack  
> *c3 (el objeto al que apunta): en el heap  
> Contador::total: en el segmento de datos estáticos (compartido entre todas las instancias)  
>

## **ACTIVIDAD 10 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```c++
#include <iostream>
using namespace std;

class Punto {
public:
    int x;
    int y;

    // Constructor
    Punto(int _x, int _y) : x(_x), y(_y) {
        cout << "Constructor: Punto(" << x << ", " << y << ") creado." << endl;
    }

    // Destructor
    ~Punto() {
        cout << "Destructor: Punto(" << x << ", " << y << ") destruido." << endl;
    }

    // Método para imprimir valores
    void imprimir() {
        cout << "Punto(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    {
        cout << "Inicio del bloque" << endl;
        Punto pBloque(100, 200);
        // Coloca un breakpoint aquí para ver 'pBloque' en el stack.
        pBloque.imprimir();
    }
    // Al salir del bloque, el destructor de 'pBloque' se invoca.
    cout << "Fuera del bloque" << endl;

    // Creación dinámica:
    Punto* pDinamico = new Punto(300, 400);
    pDinamico->imprimir();
    // 'pDinamico' sigue existiendo hasta que se libere manualmente.
    // Coloca un breakpoint aquí y observa la dirección de memoria.
    delete pDinamico;
    // Después de 'delete', el destructor se llama y la memoria se libera.

    return 0;
}
```

>1.  [Explica el ciclo de vida de un objeto en el stack versus uno en el heap.]  
> Objeto en stack (pBloque): Este se construye al entrar en el bloque y se destruye automáticamente al salir del bloque, además de que su memoria se gestiona sola  
> Objeto en heap (pDinamico): Se construye manualmente con new y se destruye solo cuando se llama delete, asi mismo, su memoria es manipulada manualmente, ya que si no se libera la memoria puede haber una fuga de memoria
>

```c++
///MODIFICAMOS///
#include <iostream>
using namespace std;

class Punto {
public:
    int x;
    int y;

    // Constructor
    Punto(int _x, int _y) : x(_x), y(_y) {
        cout << "Constructor: Punto(" << x << ", " << y << ") creado." << endl;
    }

    // Destructor
    ~Punto() {
        cout << "Destructor: Punto(" << x << ", " << y << ") destruido." << endl;
    }

    // Método para imprimir valores
    void imprimir() {
        cout << "Punto(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    {
        cout << "Inicio del bloque" << endl;
        Punto pBloque(100, 200);
        pBloque.imprimir();
        // Coloca un breakpoint aquí para ver 'pBloque' en el stack.
    }
    // Al salir del bloque, el destructor de 'pBloque' se invoca.
    cout << "Fuera del bloque" << endl;
    // Creación dinámica:
    Punto* pDinamico = new Punto(300, 400);
    pDinamico->imprimir();
    // 'pDinamico' sigue existiendo hasta que se libere manualmente.
    // Coloca un breakpoint aquí y observa la dirección de memoria.
    delete pDinamico;
    // Después de 'delete', el destructor se llama y la memoria se libera.

  {
    cout << "Inicio del bloque 2" << endl;
    Punto* pBloque2 = new Punto(500, 600);
    pBloque2->imprimir();
    }
    pBloque2->imprimir();
    delete pBloque2;

    return 0;
}
```
>2.  [¿Compila? ¿Por qué ocurre esto?]  
> Ni siquiera compila, ya que pBloque2 se declara dentro del bloque y y se destruye al terminar el bloque. Así que, al intentar usar pBloque2 fuera del bloque, el compilador no lo reconoce, pues ya se eliminó
>

>3.  [Modifica el programa para declarar pBloque2 por fuera del bloque, pero inicializarlo dentro del bloque. ¿Qué ocurre? ¿Por qué?]  
>Para ello, la variable pBloque2 debería vivir en el stack durante la ejecución de main, de modo en que despues de que se ejecute su bloque, siga existiendo en todo el main ya que la variable abarcaría todo el main
>

```c++
//MODIFICAMOS NUEVAMENTE//
#include <iostream>
using namespace std;

class Punto {
public:
    int x;
    int y;

    // Constructor
    Punto(int _x, int _y) : x(_x), y(_y) {
        cout << "Constructor: Punto(" << x << ", " << y << ") creado." << endl;
    }

    // Destructor
    ~Punto() {
        cout << "Destructor: Punto(" << x << ", " << y << ") destruido." << endl;
    }

    // Método para imprimir valores
    void imprimir() {
        cout << "Punto(" << x << ", " << y << ")" << endl;
    }
};

int main() {
    {
        cout << "Inicio del bloque" << endl;
        Punto pBloque(100, 200);
        // Coloca un breakpoint aquí para ver 'pBloque' en el stack.
        pBloque.imprimir();
    }

    Punto* pBloque2 = nullptr;
    {
        cout << "Inicio del bloque 2" << endl;
        pBloque2 = new Punto(500, 600);
        pBloque2->imprimir();
    }
    pBloque2->imprimir();
    delete pBloque2;

    return 0;
}
```

>4.  [¿Por qué el objeto pBloque se destruye al salir del bloque y pBloque2 no?
Recuerda de nuevo, pBloque2 es un objeto o es una referencia a un objeto?]  
> pBloque: es un objeto en stack, de modo en que su ciclo de vida esta condenado al bloque. Al salir, se destruye  
> pBloque2: es un puntero en stack, pero apunta a un objeto creado con new en el heap. Cuando termina el bloque, el puntero sigue existiendo, pero el objeto al que apunta sigue vivo en el heap. Solo se destruye cuando haces delete pBloque2.
>

>5.  [¿En qué parte de la memoria se almacena pBloque2?]  
> pBloque2 está en el stack
>

>6.  [¿En qué parte de la memoria se almacena el objeto al que apunta pBloque2?]  
> El objeto está en el heap
>

-	**Bitácora** 𖤓 ☆ ☼ ⋆⋅**
```c++
#include <iostream>
#include <string>

class Personaje {
public:
    std::string nombre;
    int* estadisticas;

    Personaje(std::string n, int vida, int ataque, int defensa) {
        nombre = n;
        estadisticas = new int[3];
        estadisticas[0] = vida;
        estadisticas[1] = ataque;
        estadisticas[2] = defensa;
        std::cout << "Constructor: nace " << nombre << std::endl;
    }

    void imprimir() {
        std::cout << "Personaje " << nombre
            << " [Vida: " << estadisticas[0]
            << ", ATK: " << estadisticas[1]
            << ", DEF: " << estadisticas[2]
            << "]" << std::endl;
    }
};

void simularEncuentro() {
    std::cout << "\n--- Iniciando encuentro ---" << std::endl;
    Personaje heroe("Aragorn", 100, 20, 15);

    Personaje copiaHeroe = heroe;
    copiaHeroe.nombre = "Copia de Aragorn";

    std::cout << "Saliendo del encuentro..." << std::endl;
}

int main() {
    simularEncuentro();
    std::cout << "\nSimulación terminada." << std::endl;
    return 0;
}
```
-  [¿Cuál es el error?]      

-  [¿Por qué ocurre? Explica el mecanismo a nivel de memoria (stack, heap, punteros)]      

-  [¿Cuál es su consecuencia?]

-  [corrección código] 

