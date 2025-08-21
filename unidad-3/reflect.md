# Unidad 3

## 🤔 Fase: Reflect

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 11 ༓☾∘∙•⋅⋅⊰⋅•⋅**

### [Parte 1]

1. Explica con tus propias palabras qué es el stack y qué es el heap en C++.    
El stack y el heap son dos conjutos en la memoria que contienen funciones y tipos de varibles diferentes. El Stack almacena las variables por funciones, por ende, una vez se usen dichas funciones y las varibles hayan terminado su labor, el stack libera o borra la memoria de dichas variables. El heap tiene cierta similitud pero al contrario. El heap almacena funciones y variables que hayan sido creadas manualmente con new y deben ser destruidas manualmnete con un destructor, lo que nos permiite llamar muchas veces algo y manipular manualmente su vida de uso

2. Describe las tres formas de pasar parámetros a una función en C++ (valor, referencia y puntero). Para cada una, explica qué sucede en memoria y cuándo usarías cada método.      
Estos tres métodos nos permite llamar y pasar valores o parametros de las variables por debajo de la mesa, por asi decirlo. Paso por valor nos permite crear una copia fantasma de nuestro parámetro y manipular dicha copia, Paso por referencia simplemente crea un alias o un apodo a la variable y se trabaja con dicho apodo pero estamos manipulando la variable origianl, finalmente esta Paso por Puntero, que implica la creadión de un puntero para acceder por medio de el a la informacion de la variable y manipularla. Siendo estas dos ultimas las que modifican directamente las variable que llamammos, mientras que la primera solo modifica un doble

3. ¿Qué diferencia hay entre una variable local, una variable global y una variable local estática? ¿En qué segmento del mapa de memoria se almacena cada una?    
Genuinamente no recuerdo acerca de las variables globales. Pero las locales son aquellas variables propias de una funcion dentro del stack si no recuerdo mal. Las estáticas son variables que siempre existen, nunca se destrruyen hasta que la aplicación termina. 

4. Explica qué es un objeto en C++ desde la perspectiva de memoria. ¿Dónde se almacenan los miembros de instancia y dónde los miembros estáticos?  
Los objetos estan en el stack. Los miembros de instancia viven en el stack, mientras mientras que los estaticos se guardan en las variables globales. 

### [Parte 2]

```C++
#include <iostream>
using namespace std;

class Enemigo {
public:
    static int totalEnemigos;
    int vida;
    int* armas;

    Enemigo(int v) : vida(v) {
        totalEnemigos++;
        armas = new int[3];
        armas[0] = 10; armas[1] = 15; armas[2] = 20;
    }
};

int Enemigo::totalEnemigos = 0;

void crearEscuadron() {
    for(int i = 0; i < 5; i++) {
        Enemigo soldado(100);
        soldado.vida -= 10;
    }
    cout << "Escuadrón creado. Total enemigos: " << Enemigo::totalEnemigos << endl;
}

int main() {
    crearEscuadron();
    crearEscuadron();
    return 0;
}
```
5. Análisis de problemas: identifica al menos dos problemas serios en este código relacionados con el manejo de memoria. Explica por qué cada uno es problemático.  
La verdad no estoy muy segura si esta bien, pero creo que los dos errorres es que ni la clase enemigo se libera ni los escuadrones de enemigos que se crean 2 veces, creando una fuga

6. Predicción de comportamiento: ¿Qué valor mostrará totalEnemigos después de ejecutar el programa? ¿Por qué ocurre esto?  
El total de enemigos se va sumando, debido a que como no se borran, entonces se crean primero 5 y luego se suman otros 5 con los que ya habian 

```c++
#include <iostream>
using namespace std;

class Enemigo {
public:
    static int totalEnemigos;
    int vida;
    int* armas;

    // Constructor
    Enemigo(int v) : vida(v) {
        totalEnemigos++;
        armas = new int[3]{10, 15, 20};  // inicialización directa
    }

    // Destructor
    ~Enemigo() {
        delete[] armas;    // liberar memoria
        totalEnemigos--;   // actualizar contador
    }
};

int Enemigo::totalEnemigos = 0;

void crearEscuadron() {
    for(int i = 0; i < 5; i++) {
        Enemigo soldado(100);
        soldado.vida -= 10;
    }
    cout << "Escuadrón creado. Total enemigos: " << Enemigo::totalEnemigos << endl;
}

int main() {
    crearEscuadron();
    crearEscuadron();
    return 0;
}
```

7. Propuesta de solución: escribe una versión corregida de la clase Enemigo que solucione los problemas identificados. Explica brevemente cada cambio que hiciste.    
Genuinamente considero  que las dos fugas de memoria que hay se pueden arreglar unica y exclusivamente con un solo destructor, pero cuando lo intente, aunque si bien elimina y libera lo que necesitamos, hace que los dos "crearEscuadron" no funcionen y no se que más podría intentar

### [Parte 3]

8. De todos los conceptos que exploraste en esta unidad (stack vs heap, paso de parámetros, ciclo de vida de objetos, etc.), ¿Cuál consideras que es el más crítico para evitar errores en programas reales? ¿Por qué?  
Posiblemente el del ciclo de vida de los objetos. No considero necesariamente relevante el saber en donde se almacenan y el por que, sino entender que ciertas funciones viven diferente y tenerlo siem pre en cuenta

9. ¿Cómo cambió tu comprensión sobre lo que realmente es un “objeto” después de comparar C++ con C#? ¿Qué implicaciones prácticas tiene esta diferencia?  
Cambió mucho en el sentido de la vida util del objeto. Admito que no aprendi muchgo en PDOO (programacion y diseño orientada a objetos) dado a que no soy fan del codigo y no me siento en la capacidad de podert desarrollar una correcta logica de programacion. Pero considero que aprendi principalmente que "Todo lo que se crea, se debe liberar"

10. Si tuvieras que explicar a un compañero de semestres anteriores por qué es importante entender la gestión de memoria en programación, ¿Qué le dirías en máximo 3 oraciones?  
"Todo lo que creas se debe destruir en algun momento o de una u otra forma, sino vas a crear una fuga de memoria"  
"Existen maneras diferentes de llamar parametros y variables. debes escoger la mejor para cada ocasion "  
"Es muy importante saber en que momento estas creando y destruyendo cosas, que no vaya a ser que usted llame algo que ya destruiste"  



