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
> 0000 ADJUNTAR CAPTURAS

## 🎃**ACTIVIDAD 03**🎃 

-  🐯 **Antes de ejecutar el experimento, ¿Qué esperas ver en memoria (hipótesis)? Ejecuta el código y muestra una captura de pantalla del objeto en la memoria. ¿Qué puedes observar? ¿Qué información te proporciona el depurador? ¿Qué puedes concluir?**
>
> 000

-  🦧 **¿Qué puedes observar en la memoria? ¿Qué información te proporciona el depurador? ¿Qué puedes concluir?**
>
> 000

-  🦺 **Captura la _vtable de un objeto CircularExplosion, pega la imagen en tu bitácora, pero observa detenidamente la tabla de funciones. ¿Qué puedes observar?**
>
> 000 ADJUNTAR CAPTURAS

-  🏀 ** Observa de nuevo ambas tablas y compara. ¿Qué puedes ver? ¿Qué puedes concluir? ¿Qué relación existe entre la tabla de funciones y los métodos virtuales?**
>
> 0000

-  🧱 **¿Para qué crees que pueda servir una tabla de funciones virtuales?**
>
> 0000

-  🦋 **Nota que el método HacerSonido se llama dos veces, una vez para el perro y otra vez para el gato. ¿Cómo se logra esto? ¿Qué relación existe entre los métodos virtuales y el polimorfismo? Al llamar HacerSonido cómo sabe esta función sobre cuál objeto debe actuar?**
>
> 0000

## 👻**ACTIVIDAD 04**👻  

🐚🪽🦢🕊️🐇🐑🦙🐻‍❄️🐰🕸️🦴🦷🏐🥌⛸️🪩🎲🎼🪨💿

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

Ejecuta este código. Luego, descomenta las líneas que están comentadas y vuelve a compilar. ¿Qué sucede? ¿Por qué sucede esto? ¿Qué puedes concluir?

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

Compila el programa. ¿Qué pasa?

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
Compila el programa y ejecuta. ¿Qué puedes concluir?

En tus palabras, ¿Qué es el encapsulamiento? ¿Por qué es importante?

















## 4.  **Consolidación, autoevaluación y cierre:**
> [!CAUTION]
> Esta sección es OBLIGATORIA y central para tu evaluación
