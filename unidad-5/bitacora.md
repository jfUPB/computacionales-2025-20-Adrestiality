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

# 2.  **La pregunta inicial** ༓☾∘∙•⋅⋅⊰⋅•⋅**

-  🦑 Ya que decidí irme por la ruta guiada, asi que tus preguntas serán las mías también

# 3.  **Registro de exploración:** ༓☾∘∙•⋅⋅⊰⋅•⋅**
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
> <a name="captura1"></a>
> <img width="601" height="536" alt="image" src="https://github.com/user-attachments/assets/759366d6-22c0-4975-98e3-c03c9fa850b8" />
><img width="919" height="289" alt="image" src="https://github.com/user-attachments/assets/44c62583-c3bd-4313-a955-3eaaf70c9286" />
>
> hablando un poco con mi relacion toxica (osea chaGPT) parece que el motivo por el cual la mamoria se veia con ??? es porque no podia acceder desde cualquier direccion arbitraria, sino desde el puntero this. me recuerda al encapsulamiento

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
```c#
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
><img width="549" height="83" alt="image" src="https://github.com/user-attachments/assets/fbb5dca3-60f6-4a9c-8cec-805ce11c64a4" />
>
> Aqui se evidencia el concepto de encapsulamiento. Ya que al descomentar las lineas, nos da un error de que las cosas a las que le queremos poner valores especificos no se puede porque no se pueden modificar en ese contexto, ni acceder en ese contexto

```c++
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
>
> Pasa lo mismo de hace un momento, no podemos acceder a secret.1

```c++
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
> Ya sabia que visual studio no tenia opcion para la herencia multiple, pero jamas la habia evidenciado en c++. Para ello le pedi a una IA que hiciera un ejemplo sencillo. Veamos
````C++
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

- 🐥 **¿Qué relación existe entre los métodos virtuales y el polimorfismo?**
>
> Los metodos virtuales le Indican al compilador que las llamadas deben resolverse en tiempo de ejecución, mientars que el Polimorfismo el comportamiento que nace de ese mecanismo: un mismo mensaje (update) produce diferentes respuestas dependiendo del tipo real del objeto.

## 🦩**ACTIVIDAD 06**🦩 

> Lo que realicé para esta actividad, fueron dos tipos de partículas que rebotaban en las paredes, una siendo un cuadrado que variaba de tamaño y otra siendo un pentátono, y finalmente un tipo de explosión con partículas en forma de hectágono.
>
> Veamos el código

**ofApp.h**
```` c#
#pragma once
#include "ofMain.h"
#include <vector>

// -------------------------------------------------
// Clase base abstracta: Particle
// -------------------------------------------------
class Particle {
public:
	virtual ~Particle() {}
	virtual void update(float dt) = 0;
	virtual void draw() = 0;
	virtual bool isDead() const = 0;
	virtual bool shouldExplode() const { return false; }
	virtual glm::vec2 getPosition() const { return glm::vec2(0, 0); }
	virtual ofColor getColor() const { return ofColor(255); }
};

// -------------------------------------------------
// RisingParticle
// -------------------------------------------------
class RisingParticle : public Particle {
protected:
	glm::vec2 position;
	glm::vec2 velocity;
	ofColor color;
	float lifetime;
	float age;
	bool exploded;

public:
	RisingParticle(const glm::vec2& pos, const glm::vec2& vel, const ofColor& col, float life)
		: position(pos)
		, velocity(vel)
		, color(col)
		, lifetime(life)
		, age(0)
		, exploded(false) {
	}

	void update(float dt) override {
		position += velocity * dt;
		age += dt;
		velocity.y += 9.8f * dt * 8;
		float explosionThreshold = ofGetHeight() * 0.15 + ofRandom(-30, 30);
		if (position.y <= explosionThreshold || age >= lifetime) {
			exploded = true;
		}
	}

	void draw() override {
		ofSetColor(color);
		ofDrawCircle(position, 10);
	}

	bool isDead() const override { return exploded; }
	bool shouldExplode() const override { return exploded; }
	glm::vec2 getPosition() const override { return position; }
	ofColor getColor() const override { return color; }
};

// -------------------------------------------------
// PARTICULA NUEVA 1: BouncingSquareParticle
// -------------------------------------------------
class BouncingSquareParticle : public Particle {
private:
	glm::vec2 position;
	glm::vec2 velocity;
	ofColor color;
	float age;
	float lifetime;
	bool exploded;

public:
	BouncingSquareParticle(const glm::vec2& pos, const glm::vec2& vel, const ofColor& col)
		: position(pos)
		, velocity(vel)
		, color(col)
		, age(0)
		, lifetime(ofRandom(2, 4))
		, exploded(false) {
	}

	void update(float dt) override {
		position += velocity * dt;
		age += dt;

		// Rebote en los bordes de la ventana
		if (position.x <= 0 || position.x >= ofGetWidth()) velocity.x *= -1;
		if (position.y <= 0 || position.y >= ofGetHeight()) velocity.y *= -1;

		if (age >= lifetime) {
			exploded = true;
		}
	}

	void draw() override {
		ofSetColor(color);
		ofDrawRectangle(position, position.x/10, position.y/10);
	}

	bool isDead() const override { return exploded; }
	bool shouldExplode() const override { return exploded; }
	glm::vec2 getPosition() const override { return position; }
	ofColor getColor() const override { return color; }
};

// -------------------------------------------------
// PARTICULA NUEVA 2: BouncingPentagonParticle
// -------------------------------------------------
class BouncingPentagonParticle : public Particle {
private:
	glm::vec2 position;
	glm::vec2 velocity;
	ofColor color;
	float age;
	float lifetime;
	bool exploded;

public:
	BouncingPentagonParticle(const glm::vec2& pos, const glm::vec2& vel, const ofColor& col)
		: position(pos)
		, velocity(vel)
		, color(col)
		, age(0)
		, lifetime(ofRandom(2, 4))
		, exploded(false) {
	}

	void update(float dt) override {
		position += velocity * dt;
		age += dt;

		// Rebote en los bordes de la ventana
		if (position.x <= 0 || position.x >= ofGetWidth()) velocity.x *= -1;
		if (position.y <= 0 || position.y >= ofGetHeight()) velocity.y *= -1;

		if (age >= lifetime) {
			exploded = true;
		}
	}

	void draw() override {
		ofSetColor(color);

		float centerX = position.x;
		float centerY = position.y;
		float radius = 35;
		int sides = 5;
		
		ofSetLineWidth(3);
		
		ofPolyline pentagon;

		for (int i = 0; i < sides; ++i) {
			float angle = ofDegToRad(i * (360.0 / sides));

			float x = centerX + radius * cos(angle);
			float y = centerY + radius * sin(angle);

			pentagon.addVertex(x, y);
		}
		pentagon.draw();
	}

	bool isDead() const override { return exploded; }
	bool shouldExplode() const override { return exploded; }
	glm::vec2 getPosition() const override { return position; }
	ofColor getColor() const override { return color; }
};

// -------------------------------------------------
// ExplosionParticle (base)
// -------------------------------------------------
class ExplosionParticle : public Particle {
protected:
	glm::vec2 position;
	glm::vec2 velocity;
	ofColor color;
	float age;
	float lifetime;
	float size;

public:
	ExplosionParticle(const glm::vec2& pos, const glm::vec2& vel, const ofColor& col, float life, float sz)
		: position(pos)
		, velocity(vel)
		, color(col)
		, age(0)
		, lifetime(life)
		, size(sz) {
	}

	void update(float dt) override {
		position += velocity * dt;
		age += dt;
		float alpha = ofMap(age, 0, lifetime, 255, 0, true);
		color.a = alpha;
	}

	bool isDead() const override { return age >= lifetime; }
};

// -------------------------------------------------
// CircularExplosion
// -------------------------------------------------
class CircularExplosion : public ExplosionParticle {
public:
	CircularExplosion(const glm::vec2& pos, const ofColor& col)
		: ExplosionParticle(pos, glm::vec2(0, 0), col, 1.2f, ofRandom(16, 32)) {
		float angle = ofRandom(0, TWO_PI);
		float speed = ofRandom(80, 200);
		velocity = glm::vec2(cos(angle), sin(angle)) * speed;
	}

	void draw() override {
		ofSetColor(color);
		ofDrawCircle(position, size);
	}
};

// -------------------------------------------------
// StarExplosion
// -------------------------------------------------
class StarExplosion : public ExplosionParticle {
public:
	StarExplosion(const glm::vec2& pos, const ofColor& col)
		: ExplosionParticle(pos, glm::vec2(0, 0), col, 1.3f, ofRandom(20, 40)) {
		float angle = ofRandom(0, TWO_PI);
		float speed = ofRandom(90, 180);
		velocity = glm::vec2(cos(angle), sin(angle)) * speed;
	}

	void draw() override {
		ofSetColor(color);
		int rays = 5;
		float outerRadius = size;
		float innerRadius = size * 0.5;
		ofPushMatrix();
		ofTranslate(position);
		for (int i = 0; i < rays; i++) {
			float theta = ofMap(i, 0, rays, 0, TWO_PI);
			float xOuter = cos(theta) * outerRadius;
			float yOuter = sin(theta) * outerRadius;
			float xInner = cos(theta + PI / rays) * innerRadius;
			float yInner = sin(theta + PI / rays) * innerRadius;
			ofDrawLine(0, 0, xOuter, yOuter);
			ofDrawLine(xOuter, yOuter, xInner, yInner);
		}
		ofPopMatrix();
	}
};

// -------------------------------------------------
// RandomExplosion
// -------------------------------------------------
class RandomExplosion : public ExplosionParticle {
public:
	RandomExplosion(const glm::vec2& pos, const ofColor& col)
		: ExplosionParticle(pos, glm::vec2(0, 0), col, 1.5f, ofRandom(16, 32)) {
		velocity = glm::vec2(ofRandom(-200, 200), ofRandom(-200, 200));
	}

	void draw() override {
		ofSetColor(color);
		ofDrawRectangle(position.x, position.y, size, size);
	}
};

// -------------------------------------------------
// NUEVA EXPLOSIÓN [HectagonExplosion]
// -------------------------------------------------
class HectagonExplosion : public ExplosionParticle {
public:
	HectagonExplosion(const glm::vec2& pos, const ofColor& col)
		: ExplosionParticle(pos, glm::vec2(0, 0), col, 1.5f, ofRandom(16, 32)) {
		velocity = glm::vec2(ofRandom(-200, 200), ofRandom(-200, 200));
	}

	void draw() override {
		ofSetColor(color);

		float centerX = position.x;
		float centerY = position.y;
		float radius = size;
		int sides = 8;

		ofPolyline Hectagon;

		for (int i = 0; i < sides; ++i) {
			float angle = ofDegToRad(i * (360.0 / sides));

			float x = centerX + radius * cos(angle);
			float y = centerY + radius * sin(angle);

			Hectagon.addVertex(x, y);
		}
		Hectagon.draw();

	}
};

// -------------------------------------------------
// ofApp
// -------------------------------------------------
class ofApp : public ofBaseApp {
public:
	void setup();
	void update();
	void draw();
	void mousePressed(int x, int y, int button);
	void keyPressed(int key);

	std::vector<Particle*> particles;
	~ofApp();

private:
	void createRisingParticle();
};
````
**ofApp.cpp**
````c#
#include "ofApp.h"

// --------------------------------------------------------------
void ofApp::setup() {
	ofSetFrameRate(60);
	ofBackground(0);
}

// --------------------------------------------------------------
void ofApp::update() {
	float dt = ofGetLastFrameTime();

	for (int i = 0; i < particles.size(); i++) {
		particles[i]->update(dt);
	}

	for (int i = particles.size() - 1; i >= 0; i--) {
		if (particles[i]->shouldExplode()) {
			int explosionType = (int)ofRandom(4);
			int numParticles = (int)ofRandom(20, 30);
			for (int j = 0; j < numParticles; j++) {
				if (explosionType == 0) {
					particles.push_back(new CircularExplosion(particles[i]->getPosition(), particles[i]->getColor()));
				}
				else if (explosionType == 1) {
					particles.push_back(new RandomExplosion(particles[i]->getPosition(), particles[i]->getColor()));
				}
				else if (explosionType == 2) {
					particles.push_back(new StarExplosion(particles[i]->getPosition(), particles[i]->getColor()));
				}
				else {
					particles.push_back(new HectagonExplosion(particles[i]->getPosition(), particles[i]->getColor()));
				}
			}
			delete particles[i];
			particles.erase(particles.begin() + i);
		}
		else if (particles[i]->isDead()) {
			delete particles[i];
			particles.erase(particles.begin() + i);
		}
	}
}

// --------------------------------------------------------------
void ofApp::draw() {
	for (int i = 0; i < particles.size(); i++) {
		particles[i]->draw();
	}
}

// --------------------------------------------------------------
void ofApp::createRisingParticle() {
	// Generar desde la mitad de la pantalla
	float minX = ofGetWidth() * 0.35;
	float maxX = ofGetWidth() * 0.65;
	float spawnX = ofRandom(minX, maxX);
	glm::vec2 pos(spawnX, ofGetHeight() * 0.5);

	glm::vec2 target(ofGetWidth() / 2 + ofRandom(-300, 300), ofGetHeight() * 0.10 + ofRandom(-30, 30));
	glm::vec2 direction = glm::normalize(target - pos);
	glm::vec2 vel = direction * ofRandom(250, 350);

	ofColor col;
	col.setHsb(ofRandom(255), 220, 255);
	float lifetime = ofRandom(1.5, 3.5);

	float choice = ofRandom(1.0);
	if (choice < 0.5) {
		particles.push_back(new RisingParticle(pos, vel, col, lifetime));
	}
	else if (choice < 0.75) {
		particles.push_back(new  BouncingPentagonParticle(pos, vel, col));
	}
	else {
		particles.push_back(new BouncingSquareParticle(pos, vel, col));
	}
}

// --------------------------------------------------------------
void ofApp::mousePressed(int x, int y, int button) {
	createRisingParticle();
}

// --------------------------------------------------------------
void ofApp::keyPressed(int key) {
	if (key == ' ') {
		for (int i = 0; i < 1000; i++) {
			createRisingParticle();
		}
	}
	if (key == 's') {
		ofSaveScreen("screenshot_" + ofToString(ofGetFrameNum()) + ".png");
	}
}

// --------------------------------------------------------------
ofApp::~ofApp() {
	for (int i = 0; i < particles.size(); i++) {
		delete particles[i];
	}
	particles.clear();
}
````

- 🧁 ** ¿Cómo y por qué de la implementación de los conceptos de encapsulamiento, herencia y polimorfismo en tu código? **
>
> - El encapsulamiento se evidencia en como en las propias clases hay atributos privados, como position, velocity, color, lifertime... pero podemos acceder a su información gracias a otros metodos publicos como detposition, getColor
>
> - La herencia se evidencia en como las clases de diferentes explosiones heredan de la explosion base y la explosion base de particula, asi mismo, los tipos de particulas diferentes heredan de particula tambien. Lo que me permitio jugar constantemente con los mismo valores, pero diferentes en cada clase
>
> - El polimorfismo me parece que aqui esta en tiempo de ejecucion. hay algunos punteros por ahi, que supongo que son los encargados de estar dando los valores a los metodos. adicionalemente se actualiza constantemente, lo que creo que nos permite trabajar con muchas particulas a la vez

- 🧼 ** Explica cómo verificaste que cada una de las extensiones funciona correctamente, muestra capturas de pantalla del depurador donde evidencias lo anterior, en particular el polimorfismo en tiempo de ejecución.**
>
> Siempre ejecutaba el codigo despues de añadir si quiera una sola linea de codigo. Me gusta siempre experimentar y tratar de ser consiente que cuales son las lineas que hacen cosas que yo no quiero y como debo modificarlas para que cumplan su cometido.
>
>Honestamente no tome ninguna captura en el proceso de realizacion del codigo puesto que eran casi las 12 y tenia demasiado sueño, en otras palabras, lo olvide. pero te hare una descripción de como fue mi proceso
>
>Primero, decidi crear la nueva explosion, pues es de lo que mas habia referencias para inspirarme. Queria hacer una explosión con contornos de cuadraditos pero no funciono. Pedi ayuda a la IA pero tampoco sirvió. Aquí descarte por completo cualquier uso con IA
>
>En este momento, creo que el motivo por el cual no funicionaba es porque siempre usaba la funcion ofDrawRectangle al cual trataba de ponerle ofnoFill y LineWidth y no se modificaba. Considero que debia usar la funcion ofPolyLine y darle la funcion de la figura y la estructura de sus lados
>
>Luego, al ver que no funcionaba nada, trate con otra figura, quise un pentagono. pero no encontraba una funcion llamada ofDrawPentagon o parecido, asi que busque en internet y encontre un codigo que fue mi base para crear las particulas. Tras entender como funcionaba el pentagono, lo adapte y estaba lista la explosion
>
>Segundo, era momento de crear las particulas. Para ello use un codigo que tenia meisser en su bitacora, donde su particula era un cuadradito que se creaba y rebotaba por los muros hast explotar. me parecia interesante asi que lo use tambien. La primera particula es muy parecida, solo que no se genera cuadritos tan pequeños sino que eran mas medianos y cambiaban de tamaño constantemente. me gusta pensar que da la impresion de que cambia de tamaño tras impactar con los muros.
>
>Para la otra particula implemente exactamente lo mismo, pero nuevamente, con un pentagono. Me gusta el contraste porque ahora la particula era particularmente diferente a las otras. Tras esto, decidi cambiar nuevamente la explosion pentagono por una con un heptagono, para que asi fueran figuras diferentes

> <img width="1024" height="768" alt="screenshot_1377" src="https://github.com/user-attachments/assets/5ffd901d-5c51-4c05-af09-b03dba625402" />
> <img width="1024" height="768" alt="screenshot_1230" src="https://github.com/user-attachments/assets/b54cfbde-1b5c-4fd3-a396-54bdcbe8e362" />
> <img width="1024" height="768" alt="screenshot_1092" src="https://github.com/user-attachments/assets/86610345-eb8f-4d00-acaf-f56936f67641" />
> <img width="1024" height="768" alt="screenshot_1024" src="https://github.com/user-attachments/assets/83113bbc-a759-45bf-ab8e-db8a18991d75" />
> <img width="1024" height="768" alt="screenshot_906" src="https://github.com/user-attachments/assets/4ff4cacc-317d-4788-8acc-3d349b635963" />
> <img width="1024" height="768" alt="screenshot_886" src="https://github.com/user-attachments/assets/e6480a92-fa1c-442e-bfa6-39a0d979e3de" />
> <img width="1024" height="768" alt="screenshot_636" src="https://github.com/user-attachments/assets/7fc794a0-07d5-4018-b701-f398ac9bc2ab" />
> <img width="1024" height="768" alt="screenshot_1665" src="https://github.com/user-attachments/assets/9050a9e0-2c41-45ca-a7a2-203719a4235e" />
> <img width="1024" height="768" alt="screenshot_1656" src="https://github.com/user-attachments/assets/b6c45e05-ee72-4406-bc70-e0f6a7fe72aa" />
> <img width="1024" height="768" alt="screenshot_1649" src="https://github.com/user-attachments/assets/72fe7795-51eb-422e-bd70-f8a6fdb13d1b" />
> <img width="1024" height="768" alt="screenshot_1638" src="https://github.com/user-attachments/assets/7f233f15-72fb-47ae-8c8a-1dc344b84e19" />
> <img width="1024" height="768" alt="screenshot_1616" src="https://github.com/user-attachments/assets/c08f5fc0-723f-4ba5-8375-f41779fe7c25" />
> <img width="1024" height="768" alt="screenshot_1471" src="https://github.com/user-attachments/assets/7d1de28f-d802-478a-9d9b-96b485fbe167" />


# 4.  **Consolidación, autoevaluación y cierre:** ༓☾∘∙•⋅⋅⊰⋅•⋅**

- 🪶**Mi nota propuesta: 4.0** 

- 🦇 **Justificación general**
> Siento que en esta ocasion me forcé lo que mas pude a evitar el uso de la IA para la realización de las actividades, y solamente implementarla para explicaciones generales de cosas que no entendia tan facilmente. Pero es por ese mismo motivo por el cual siento que mi rendimiento aun no es perfecto. Se que hay otrso compañeros lo suficientemente inteligentes como para lograr entender, encontrar y deducir todo lo que necesitan, y aun no consigo ese resultado.
> 
> Tambien me gusto esta unidad porque tuve de vuelta las preguntas para responder ademas de la posibilidad de las rutas. admito que me siento mas tranquila y comoda en un proceso guiado con preguntas pequeñas que ayuda a gente pendejita, como yo, a sentir que estan entendiendo asi sea un poco. aunque me frustro y siempre acabo rindiendome nuevamente con la programacion, estas actividades para mi son como un reinicio, un nuevo intento. Siento que en esta actividad avance un poquito, espero pueda seguir asi en las unidades que siguen

- 🦅 **Mapeo de evidencias según la rúbrica**

| Criterio                       | Autoevaluación | Justificación / Evidencias |
|--------------------------------|----------------|-----------------------------|
| **Profundidad de la Indagación** | Logrado    | Siento que hice lo posible por indagar por mi cuenta e implementar las cosas que encontraba a mi paso. aunque se que hay cosas que aun no entiendo mas especificas como algunas lineas o funciones de los codigos, al igual que el tema de la herencia multiple, siento que hice un buen trabajo investigando lo necesario |
| **Calidad de la Experimentación** | En desarollo      | Aun me cuesta mucho darle ese toque personal a mis codigos, pues normalmente siempre voy por lo facil. No me considero ser capaz de hacer cosas mas complejas o geniales. No siento tener esa logica de programacion que es necesaria para hacer codigo. Ejemplo del profe: como muestra esta [evidencia](#captura1) |
| **Calidad del análisis y la reflexión** | Logrado     | Reconozco que me gusta jugar mucho con los valores en las lineas de codigo o probar que pasa si borro o pongo una nueva linea con cualquier cosa que siento que puede complementar en algo. En muchas ocasiones esto no servia de nada, pero me ayudaba a  entender que hacian algunas de las funciones y como debia modificarlas, pero otras jamas las entendi |
| **Apropiación y articulación de conceptos** | En desarollo    | La verdad no tuve la mas minima idea de como hacer un dibujo sobre el polimorfismo en tiempo de ejecucion, pero siento que esta unidad me ayudo a aprender los terminos que nunca o cai¿si nunca use en POO.  |



