# Bitácora de aprendizaje de la unidad 5

# 1.  **Diagnóstico inicial** ༓☾∘∙•⋅⋅⊰⋅•⋅**

## 🐛**ACTIVIDAD 01**🐛
> [!WARNING]
> NOTA: Genuinamente esta clase de conceptos de programación orientada a objetos se me complican mucho. Mis clases de POO eran muy parchadas y gran parte de estos conceptos fueron exposiciones que hicieron los estudiantes de la clase, por lo que en realidad no las applicamos... 

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
>   0000

-  🐢 **El mecanismo del polimorfismo**
> - ¿Cómo decide el programa, mientras se está ejecutando, si debe llamar al Dibujar del Circulo o al del Rectangulo?
> 
>   0000

-  🐸 **La barrera del encapsulamiento**
> - ¿Cómo crees que el compilador logra que no puedas acceder a un miembro private desde fuera de la clase?
> 
>   0000
> - ¿Es algo que se revisa cuando escribes el código, o es una protección que existe mientras el programa se ejecuta?
> 
>   0000
> - ¿Por qué piensas eso?
> 
>   0000

**═∘◦✧◦∘═ 🧩PARTE 4🧩 ═∘◦✧◦∘═**

-  🦠 **RUTA SELECCIONADA:**
> 000

## 2.  **La pregunta inicial** ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  🐍 **00** 

## 3.  **Registro de exploración:** 
> Aquí documentas cada ciclo de pregunta -> hipótesis -> experimento -> hallazgo -> reflexión.
> Debe ser rico en evidencia visual (código, capturas del depurador con anotaciones, diagramas).

## 4.  **Consolidación, autoevaluación y cierre:**
> [!CAUTION]
> Esta sección es OBLIGATORIA y central para tu evaluación
