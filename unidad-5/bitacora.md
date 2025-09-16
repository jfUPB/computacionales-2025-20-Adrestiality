# Bitácora de aprendizaje de la unidad 5

# 1.  **Diagnóstico inicial** ༓☾∘∙•⋅⋅⊰⋅•⋅**

## 🐛**ACTIVIDAD 01**🐛
> [!WARNING]
> NOTA: Genuinamente esta clase de conceptos de programación orientada a objetos se me complican mucho. Mis clases de POO eran muy parchadas y gran parte de estos conceptos fueron exposiciones que hicieron los estudiantes de la clase, por lo que en realidad no las aplicamos... 

**═∘◦✧◦∘═ 🧩PARTE 1🧩 ═∘◦✧◦∘═**

-  ♻️ **¿Qué es el encapsulamiento para ti? Describe una situación en la que te haya sido útil o donde hayas visto su importancia**

> Según recuerdo era una especie de practica que nos permitía administrar de alguna manera la visibilidad o accesibilidad de los atributos o métodos
>
> La verdad no tengo ninguna situación en mente para el uso del encapsulamiento

-  🥦 **¿Qué es la herencia? ¿Por qué un programador decidiría usarla? Da un ejemplo simple**

> De todos los conceptos este es el unico que recuerdo bien. La herencia nos permite que una clase hija herede los atributos y metodos de una clase madre
>
> Por ejemplo, tenemos una clase hija llamada perro, con el atributo ladrar y otrso dos atributos heredados de la clase padre llamada animal, las cuales son comer y dormir

-  🦖 **¿Qué es el polimorfismo? Describe con tus palabras qué significa que un código sea “polimórfico”**

> Este creo que se refiere a diferentes comportamientos de un solo método. Esto hace que el código se vuelva versátil. Vamos a imaginar que tenemos una clase perro y otra clase gato, ambos con el método ladrar, no obstante el perro hace guau y el gato miau. pero ambos hacen uso del método ladrar
>
> Decimos que un código es polimórfico cuando usamos los métodos para diferentes comportamientos

**═∘◦✧◦∘═ 🧩PARTE 2🧩 ═∘◦✧◦∘═**

-  🍀 **Encapsulamiento**
> - Señala una línea de código que sea un ejemplo claro de encapsulamiento y explica por qué lo es
> 
>   La línea está encapsulando, de manera privada, el atributo nombre
> ```c#
> private string nombre;
>```
>
> - ¿Por qué crees que el campo nombre es private pero la propiedad Nombre es public? ¿Qué problema se evita con esto?
> 
>   Creo que esto nos permitía tener un acceso controlado de los valores del atributo nombre

-  🦕 **Herencia**
> - ¿Cómo se evidencia la herencia en la clase Circulo?
> 
>   La clase circulo hereda de de la clase padre Figura
> ```c#
> public class Circulo : Figura
> ```
> 
> - Un objeto de tipo Circulo, además de Radio, ¿Qué otros datos almacena en su interior gracias a la herencia?
> 
>   La clase Figura tiene un método llamado nombre, como la clase Circulo hereda de Figura, pues hereda tambien el método nombre ademas de su propio método radio

-  🐊 **Polimorfismo**
> - ¿Cómo crees que funciona esto “por debajo”?
> 
>   La verdad no estoy segura, pero antes de llamar a fig.Dibujar(), hacemos una lista con la clase Figura llamada misFiguras, la cual nos permite crear elementos y administrarlos
>
> Luego creamos 3 elementos para la lista y les dimos valores a cada uno. Dos circulos y un recatngulo
>
> Finalmente llamamos el foreach, el cual nos perite ejecutar la clase Dibujar por cada elemento de la lista

**═∘◦✧◦∘═ 🧩PARTE 3🧩 ═∘◦✧◦∘═**

-  🦎 **Memoria y herencia**
> - ¿Cómo te imaginas que se organizan esos tres datos en la memoria del computador para formar un solo objeto?
> 
>   Cuando creamos una clase, si o si debemos darle valores a los parámetros que creamos para la propia clase. Probablemente, los parametros y los valores de los parámetrso se guardan en lugares diferentes de la memoria, quizas entre heap y stack se guardan dichas lineas de codigo

-  🐢 **El mecanismo del polimorfismo**
> - ¿Cómo decide el programa, mientras se está ejecutando, si debe llamar al Dibujar del Circulo o al del Rectangulo?
> 
>   Porque el foreach va llamamndo s a los objetos creados en la lista uno por un y por orden de creación. En este caso, primero se creó un circulo, luego un rectangulo y luego otro circulo

-  🐸 **La barrera del encapsulamiento**
> - ¿Cómo crees que el compilador logra que no puedas acceder a un miembro private desde fuera de la clase? ¿Es algo que se revisa cuando escribes el código, o es una protección que existe mientras el programa se ejecuta? ¿Por qué piensas eso?
> 
>   porque la hicimos privada, por lo que solamente podemos modificarla en su propio "habitat" y con la línea indicada que nos permite modificar su valor

**═∘◦✧◦∘═ 🧩PARTE 4🧩 ═∘◦✧◦∘═**

-  🦠 **RUTA SELECCIONADA:**
> Tomaré la ruta guiada... aunque espero tener la oportunidad en algunos momentos tener exploraciones personales. La verdad, aunque siento que me he dado casi que por vencida con el codigo, siento que aun puedo seguirle intentando

## 2.  **La pregunta inicial** ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  ✨ **¿Que tan efectivas son las medidas de encapsulamiento para evitar el hackeo, modificación o robos de datos en el código?** 

## 3.  **Registro de exploración:** 
> Aquí documentas cada ciclo de pregunta -> hipótesis -> experimento -> hallazgo -> reflexión.
> Debe ser rico en evidencia visual (código, capturas del depurador con anotaciones, diagramas).

## 🪼**ACTIVIDAD 02**🪼  

-  👾 **Analiza el código de la aplicación y trata de explicar en tus propias palabras qué está haciendo**
>
> - Primero analicemos la parte de App.h
> 
>      En breves palabras, en App.h el codigo tiene una clase de particulas con los metodos basicos para que se le     pueda asignar color, obtener su posicion, si esta proximas a morir,etc.. para luego crear otra clase que hereda de     la clase particula, que tiene más metodos como la vida, pero tambien le asigna una velocidad a la particula y     una condicion de explosion, de modo en que cuando llegue a cierto punto la pantalla este proxima a explotar.
Luego tenemos una clase que establece la explosion de la particula, que luego da paso a tres clases diferentes que   establecen los diferentes tipos de explosiones que hay. Primero la de particulas circulares que le asigna valores     aleatorios a las velocidades de las particulas que salen de la explsión. Segundo, la de particula aleatorias y     tercero, la explosion de estrella que tiene bastantes operaciones con angulos.
>
> - Segundo analicemos la parte de App.cpp
>    
>    Ahora aquí, empezamos a actualizar constantemente el valor de las partoculas, y si llegan al punto en el que     deben explotar se les asigna aleatoriamente un tipo de explosion al azar y luego borra las particulas de la     explosion, Luego tenemos la seccíon que se encarga de crear y llenar todos los metodos de la clase que se encarga     del nacimiento de las particulas y darle direcciones y angulos aleatorios. Finalmente asignamos algunos comandos,     como por ejemplo que cuando presionas 'space' salen millones de bolitas a explotar a la vez o que con la 's' tomas     capturas en png y luego borramos todos los restantes y volvemos a empezar.
> <img width="1020" height="761" alt="Captura de pantalla 2025-09-15 204159" src="https://github.com/user-attachments/assets/2c2c22a8-2d30-4c07-85ca-5e7bfb52510a" />
> <img width="1019" height="756" alt="Captura de pantalla 2025-09-15 204149" src="https://github.com/user-attachments/assets/196d10e5-55f0-4dd3-ad0c-d44ac05bf67f" />
> <img width="1006" height="742" alt="Captura de pantalla 2025-09-15 204331" src="https://github.com/user-attachments/assets/dade169e-41f2-43cf-81d2-9b8828ee5c4e" />

## 🎃**ACTIVIDAD 03**🎃 

-  🐯 **Antes de ejecutar el experimento, ¿Qué esperas ver en memoria (hipótesis)? Ejecuta el código y muestra una captura de pantalla del objeto en la memoria. ¿Qué puedes observar? ¿Qué información te proporciona el depurador? ¿Qué puedes concluir? ¿Qué puedes observar en la memoria? ¿Qué información te proporciona el depurador? ¿Qué puedes concluir?**
> 
> Inicialmente esperaba encontrar una serie de bytes en hexadecimal, aunque m elleve con la sorpresa de que todo estaba lleno de signos de interrogacion "?". siento que estoy haciendo algo mal
>
> <img width="920" height="303" alt="Captura de pantalla 2025-09-15 221447" src="https://github.com/user-attachments/assets/1874f04f-f312-480e-acbd-8d9d1949da8b" />
>
> Efectivamente, AJAJ estaba haciendo todo mal, aqui esta el objeto en la memoria
>
> <img width="601" height="536" alt="image" src="https://github.com/user-attachments/assets/759366d6-22c0-4975-98e3-c03c9fa850b8" />
><img width="919" height="289" alt="image" src="https://github.com/user-attachments/assets/44c62583-c3bd-4313-a955-3eaaf70c9286" />
>
> hablando un poco con mi relacion toxica (osea chaGPT) parece que el motivo por el cual la mamoria se veia von ??? es porque no podia acceder desde cualquier direccion arbitraria, sino desde el puntero this. me recuerda al encapsulamiento

-  🦺 **Captura la _vtable de un objeto CircularExplosion, pega la imagen en tu bitácora, pero observa detenidamente la tabla de funciones. ¿Qué puedes observar?**
>
> <img width="1312" height="411" alt="image" src="https://github.com/user-attachments/assets/2e2acbec-8776-4881-a6e6-945c180a1f15" />
>
> Podemos observar los metodos, tanto propias como heredadas, dela explosion circular, explosion de particula y de la propia particula

-  🦧 **Ahora, captura en memoria la _vtable de un objeto StarExplosion, pega la imagen en tu bitácora y observa detenidamente la tabla de funciones.**
>
> <img width="1313" height="459" alt="image" src="https://github.com/user-attachments/assets/804a3f29-8d99-44c0-894a-42d4f842432b" />

-  🏀 ** Observa de nuevo ambas tablas y compara. ¿Qué puedes ver? ¿Qué puedes concluir? ¿Qué relación existe entre la tabla de funciones y los métodos virtuales?**
>
>Creo que aqui se evidencia un poco el polimorfismo, ya que considero que tienen los mismos metodos pero algunos de estos vienen de las clases circulo o estrella mientras el resto vienen de las clases bases de las cuales hereda

-  🧱 **¿Para qué crees que pueda servir una tabla de funciones virtuales?**
>
> Considero que es til para todo lo que cabamos de hacer, evidenciar la herencia y el polimorfismo

-  🦋 **Nota que el método HacerSonido se llama dos veces, una vez para el perro y otra vez para el gato. ¿Cómo se logra esto? ¿Qué relación existe entre los métodos virtuales y el polimorfismo? Al llamar HacerSonido cómo sabe esta función sobre cuál objeto debe actuar?**
>
> Es como el ejercicio de la actividad 1 con el circulo y el rectangulo. Creamos una lista y hacemos que llamamos el sonido por cada objeto que creamos en la lista (es decir, el foreach) 

## 👻**ACTIVIDAD 04**👻  
```
class AccessControl {

private:
    int privateVar;

protected:
    int protectedVar;

public:
    int publicVar;
    AccessControl() : privateVar(1), protectedVar(2), publicVar(3) {}
};

int main() {
    AccessControl ac;
    ac.publicVar = 10; // Válido
    // ac.protectedVar = 20; // Error de compilación
    // ac.privateVar = 30; // Error de compilación
    return 0;
}
```

- 🪽 **Ejecuta este código. Luego, descomenta las líneas que están comentadas y vuelve a compilar. ¿Qué sucede? ¿Por qué sucede esto? ¿Qué puedes concluir?**
>
><img width="558" height="82" alt="image" src="https://github.com/user-attachments/assets/ee7c464d-6bd1-47d8-b7b6-0d63da06a917" />
>
> Aqui se evidencia el concepto de encapsulamiento. Ya que al descomentar las lineas, nos da un error de que las cosas a las que le queremos poner valores especificos no se puede porque no se pueden modificar en ese contexto, ni acceder en ese contexto

```
#include <iostream>

class MyClass {
private:
    int secret1;
    float secret2;
    char secret3;

public:
    MyClass(int s1, float s2, char s3) : secret1(s1), secret2(s2), secret3(s3) {}

    void printMembers() const {
        std::cout << "secret1: " << secret1 << "\n";
        std::cout << "secret2: " << secret2 << "\n";
        std::cout << "secret3: " << secret3 << "\n";
    }
};


int main() {
    MyClass obj(42, 3.14f, 'A');
    // Esta línea causará un error de compilación
    std::cout << obj.secret1 << std::endl;

    obj.printMembers();  // Método público para mostrar los valores
    return 0;
}
```

- 🥌 **Compila el programa. ¿Qué pasa?**
>
><img width="501" height="82" alt="image" src="https://github.com/user-attachments/assets/b3a15ec0-a8c4-4d31-86b4-c54e25c8ab04" />
><img width="549" height="83" alt="image" src="https://github.com/user-attachments/assets/fbb5dca3-60f6-4a9c-8cec-805ce11c64a4" />
>
> Pasa lo mismo de hace un momento, no podemos acceder a secret.1

```
#include <iostream>

class MyClass {
private:
    int secret1;
    float secret2;
    char secret3;

public:
    MyClass(int s1, float s2, char s3) : secret1(s1), secret2(s2), secret3(s3) {}

    void printMembers() const {
        std::cout << "secret1: " << secret1 << "\n";
        std::cout << "secret2: " << secret2 << "\n";
        std::cout << "secret3: " << secret3 << "\n";
    }
};

int main() {
    MyClass obj(42, 3.14f, 'A');

    // Usando reinterpret_cast para violar el encapsulamiento
    int* ptrInt = reinterpret_cast<int*>(&obj);
    float* ptrFloat = reinterpret_cast<float*>(ptrInt + 1);
    char* ptrChar = reinterpret_cast<char*>(ptrFloat + 1);

    // Accediendo y mostrando los valores privados
    std::cout << "Accediendo directamente a los miembros privados:\n";
    std::cout << "secret1: " << *ptrInt << "\n";       // Accede a secret1
    std::cout << "secret2: " << *ptrFloat << "\n";     // Accede a secret2
    std::cout << "secret3: " << *ptrChar << "\n";      // Accede a secret3

    return 0;
}
```
- 🦴**Compila el programa y ejecuta. ¿Qué puedes concluir?**
>
> La verdad tuve que consultar un poco lo que era "reinterpret_cast", pero al parecer funciona como una especie de puntero durante el tiempo real de la ejecucion, lo que nos permite acceder y modificar cosas cuando teoricamente no podemos

- 🐚**En tus palabras, ¿Qué es el encapsulamiento? ¿Por qué es importante?**
>
> Es un primcipio de poo, que nos permite ocultar los detalles internos de una clase y exponer lo necesario. Es importante porque protege los datos de ser modificados por segundos

## 🪼**ACTIVIDAD 05**🪼 
- 🐳 **captura de nuevo la memoria que ocupa el objeto CircularExplosion compara la jerarquía de clases con los campos en memoria del objeto. ¿Qué puedes observar? ¿Qué información te proporciona el depurador? ¿Qué puedes concluir?**
>
> <img width="1312" height="411" alt="image" src="https://github.com/user-attachments/assets/d5b8a6fa-b2d7-4e22-ac23-c350eb709c0a" />
> Exactamente lo mismo que hace un momento, podemos evidenciar como una cadenita de metodos. Los de particle, explosionpaarticle y del mismo circularexplosion. Todo fue heredado 

- 🐠 **¿Cómo se implementa la herencia en C++?**
>
> De lo que he visto, tiene la herencia normal, multiple, si hay metodos virtuales se crea un puntero escondido en la vtable

- 🔷 **C++ permite hacer algo que C# no: herencia múltiple. Realiza un experimento que te permita ver cómo se objeto en memoria cuya clase base tiene herencia múltiple.**
>
> Ya sabia que visual studio no tenia opcion para la herencia multiple, pero jamas la habia evidenciado en c++. Para ello le pedi a una ia que hiciera un ejemplo sencillo. Veamos
````
#include <iostream>

class A {
public:
    int a;
};

class B {
public:
    int b;
};

class C : public A, public B {
public:
    int c;
};

int main() {
    C obj;
    obj.a = 10;
    obj.b = 20;
    obj.c = 30;

    // Punto de parada para inspeccionar en memoria
    std::cout << "Detén aquí y revisa 'obj' en el depurador\n";

    return 0;
}
````
> La propia IA me indico poner un breakpoint y revisar la vtable. veamos que hay
> 
> <img width="969" height="119" alt="image" src="https://github.com/user-attachments/assets/85eac5d5-19bb-4263-af36-81b4506f95d0" />

## 👑**ACTIVIDAD 06**👑 

- ✨ **Realiza un dibujo con el cuál expliques cómo se implementa el polimorfismo en tiempo de ejecución. Utiliza el concepto de métodos virtuales y la tabla de funciones virtuales. ¿Qué puedes concluir?**
>
><img width="755" height="482" alt="image" src="https://github.com/user-attachments/assets/2df1ca24-d50e-412b-9817-2227b45410f2" />

>000 HACER DIBUJO

- 🐥 **¿Qué relación existe entre los métodos virtuales y el polimorfismo?**
>
> Los metodos virtuales le Indican al compilador que las llamadas deben resolverse en tiempo de ejecución, mientars que el Polimorfismo el comportamiento que nace de ese mecanismo: un mismo mensaje (update) produce diferentes respuestas dependiendo del tipo real del objeto.

## 4.  **Consolidación, autoevaluación y cierre:**
> [!CAUTION]
> Esta sección es OBLIGATORIA y central para tu evaluación
