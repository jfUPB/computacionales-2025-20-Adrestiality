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
Al parecer, un sistema big-endian almacena el byte más grande de una palabra en la dirección de memoria más pequeña y el byte menos significativo en la más grande  

>1.  [¿Cuál es la diferencia entre un constructor y un destructor en C++?]  
>
>

>2.  [¿Cuál es la diferencia entre un objeto y una clase en C++?]  
>
>

>3.  [¿Qué diferencia notas entre el objeto Punto en C++ y C#?]  
>
>

>4.  [¿Qué es p en C++ y qué es p en C#? (en uno de ellos p es un objeto y en el otro es una referencia a un objeto).]  
>
>

>5.  [¿En qué parte de memoria se almacena p en C++ y en C#?]  
>
>

>6.  [¿Qué observaste con el depurador acerca de p? Según lo que observaste ¿Qué es un objeto en C++?]  
>
>

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
>
>

>2.  [pStack ¿Es un objeto o una referencia a un objeto?]    
>
>

>3.  [pHeap ¿Es un objeto o una referencia a un objeto? Si es una referencia, ¿A qué objeto hace referencia?]   
>
>

>4.  [Observa en Memory1 (Debug->Windows->Memory->Memory1) el contenido de la dirección de memoria de pHeap, recuerda escribir en la entrada de texto de Memory1 la dirección de memoria de &pHeap y presionar Enter. Compara el contenido de memoria con el contenido de pHeap en la pestaña de Locals (Debug->Windows->Locals). ¿Qué observas? ¿Qué significa esto?]    
>
>

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
>
>

>2.  [¿Por qué original sigue existiendo luego de llamar cambiarNombre?]      
>
>

>3.  [¿En qué parte del mapa de memoria se encuentra original y en qué parte se encuentra p? ¿Son el mismo objeto?]     
>
>

```c++
///MODIFICAMOS LA FUNCIÓN CAMBIARNOMBRE//
void cambiarNombre(Punto& p, string nuevoNombre) {
  p.name = nuevoNombre;
}
```
>4.  [¿Qué ocurre ahora? ¿Por qué?]      
>
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
>
>

>6.  [En este caso ¿Cuál es la diferencia entre pasar un objeto por valor, por referencia y por puntero?]  
>
>

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
>
>

>-  [¿En dónde está almacenado el miembro valor y el miembro total de la clase Contador?]      
>
>

>1.  [¿Qué puedes concluir de los miembros estáticos y de instancia de una clase en C++? ¿Cómo se gestionan en memoria? ¿Qué ventajas y desventajas tienen? ¿Cuándo es útil utilizarlos?]    
>
>

>2.  [En el programa, en qué segmento de memoria se están almacenando c1, c2, c3 y Contador::total? Ten especial cuidado con la respuesta que das para el caso de c3, piensa de nuevo, qué es c3 y qué está almacenando. Ahora, responde de nuevo, en qué segmento de la memoria se está almacenando c3 y en qué segmento de la memoria se está almacenando el objeto al que apunta c3.]    
>
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
>
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
>
>

>3.  [Modifica el programa para declarar pBloque2 por fuera del bloque, pero inicializarlo dentro del bloque. ¿Qué ocurre? ¿Por qué?]  
>
>
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
>
>

>5.  [¿En qué parte de la memoria se almacena pBloque2?]  
>
>

>6.  [¿En qué parte de la memoria se almacena el objeto al que apunta pBloque2?]  
>
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
