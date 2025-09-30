## 🐔 **ACTIVIDAD 01** 🐔

<a name="evidencia1"></a>
-  🦢 **¿Cómo puedes interactuar con la aplicación? Menciona específicamente las teclas y qué efecto parecen tener sobre las partículas.**

> La interacción del usuario con el programa se lmita al uso de las teclas EN MINUSCULAS y la ubicación del mouse. Las teclas son las siguientes:
> 
> **'s'** congela el frame actual de las particulas, por lo que todo queda estático
> **'a'** atrae las particulas hacia la ubicación del mouse. El mouse puede guiarlas ya que siempre se van a mover hacia su ubicación actual
> **'r'** repele y aleja las particulas con respecto la unicación del mouse. Tambien aqui dependiendo de la ubicación del mouse se repelan las partículas dejando un trazo vacío
> **'n'** vuelve a dejar a las particulas en su comportamiento original. moviendose a lugares aleatorios hasta que se presiona alguna de las teclas

- 🦷 **¿Observas los diferentes tipos de “partículas”? ¿Se comportan todas igual inicialmente?**
>
> Parecen haber 3 tipos de particulas, las cuales se diferencian por color (rojo, verde azul) y tamaño (las rojas son las mas pequeñas, las verdes son las medianas, las azules son las mas grandes) pero de resto todas parecen comportarse igual. es como si fuesen convocadas al mismo comportamiento pese a ser distintas. Como un polimorfismo... No obstante en velocidad, no se si es impresion mia pero creo que las particulas rojas se mueen mas rapido

- 🐻‍❄️ **Toma algunas capturas de pantalla de la aplicación en diferentes momentos (estado inicial, después de presionar ‘a’, ‘r’, ‘s’, ‘n’) y añádelas a tu bitácora.**
>
> ESTADO INICIAL:
> <img width="1027" height="774" alt="image" src="https://github.com/user-attachments/assets/9377ccd7-c3cb-4b40-ad23-2f64f37d13d1" />
> <img width="1023" height="770" alt="image" src="https://github.com/user-attachments/assets/238fc819-869c-4e48-a651-8fc3f49dfc8d" />
>
> ESTADO S:
> <img width="1024" height="766" alt="image" src="https://github.com/user-attachments/assets/7fe82dfb-6d69-4392-ae30-32c07819f825" />
>
> ESTADO A:
> <img width="1016" height="756" alt="image" src="https://github.com/user-attachments/assets/b2b1db8a-dabf-4acc-9a0c-28ce2f376839" />
>
> ESTADO R:
> <img width="1025" height="753" alt="image" src="https://github.com/user-attachments/assets/22d7db16-48db-470d-98c2-3c9c5adefd2c" />
>
> ESTADO N:
> <img width="1004" height="763" alt="image" src="https://github.com/user-attachments/assets/86de9ca2-38e8-42ed-8b77-a2de0515e4fb" />

- 🐰 **¿Qué crees que está pasando “detrás de cámaras” cuando presionas las teclas? Formula una hipótesis inicial sobre cómo la aplicación cambia el comportamiento de las partículas.**
>
> Dentro del codigo hay algo llamado notify, que convoca a las particulas cuando hay cambios de estado

## 🐺 **ACTIVIDAD 02** 🐺

<a name="evidencia2"></a>
- 🦝 **Explica con tus propias palabras el propósito del patrón Observer. ¿Qué problema resuelve?** 🦝
>
> Lo que hacemos aquí es hacer que cada una de las partículas se suscriba a un super mega plan que les notifica cada vez que debe haber un cambio en el comportamiento y cada partícula decide como reaccionar
>
> El subject no tiene que saber que hace cada observador, cada suscriptor, simplemente emite el mensaje y genera un efecto
>
> en palabras aun mas cristianas, es como cuando te llega la alerta de sismos de google, google solo emite la advertencia, tu ya decides como sales de la casa por la emergencia

- 🦾 **Dibuja un diagrama que muestre la relación entre Subject, Observer, ofApp y Particle en el caso de estudio, indicando quién es el Sujeto y quiénes los Observadores.**

> <img width="1630" height="617" alt="image" src="https://github.com/user-attachments/assets/0ea80b34-4716-4958-817e-701f6e12f6d2" />

- 🦿 **Construye un diagrama de secuencia que muestre cómo funciona el patrón Observer al presionar una tecla**

> <img width="1455" height="349" alt="image" src="https://github.com/user-attachments/assets/22555d55-a7ed-4d1d-9ea2-6220bcda6c59" />

- 🔧 **¿Qué ventajas crees que ofrece usar el patrón Observer en esta aplicación en comparación con, por ejemplo, que ofApp::update recorriera todas las partículas y les dijera directamente que cambien su comportamiento basado en una variable global? Piensa en términos de acoplamiento y extensibilidad.**
>
> Lo primero que pienso es que si usaramos ofApp::update tendriamos que estar cambiando constantemente el codigo por nueva particula que querramos agregar. Ademas de que tandria que saber los comportamientos de cada particula. Diferente de este nuevo patron, que solamente manda mensajes si necesidad de saber que hace cada cosa y es muy facil de reutilizar porque no hay que estarlo actulizando con cada cosa nueva que se haga

## 🦨 **ACTIVIDAD 03** 🦨

<a name="evidencia3"></a>
- 🦍 **Explica con tus propias palabras el propósito del patrón Factory Method (o Simple Factory, en este caso). ¿Qué problema principal aborda en la creación de objetos?**
>
> El factory method es literalmente una especie de plantilla que crea objetos que se van a personalizar más adelante. es decir, todos los objetos tienen unas bases especificas y mas adelante se le dan el resto de especificaciones como cuantas se deben de crear y como se deben aplicar segun el tipo. Es bastante util porque asi se ahorra mucho lo de estar creando clases y herencias innecesarias para crear objetos que son relativamente parecidos entre si, por lo que es muy reutilizable

- 🐃 **¿Qué ventajas aporta el uso de ParticleFactory en ofApp::setup en comparación con instanciar y configurar las partículas directamente allí? Piensa en términos de organización del código (SRP - Single Responsibility Principle), legibilidad y facilidad para añadir nuevos tipos de partículas en el futuro.**
>
> Particle factory aporta mucha legibilidad en el odigo y agrupa la creación iy configuraciones en un solo lugar sin necesidad de estarlo haceindo repetidamente en cada una de las clases

- 🦡 **Imagina que quieres añadir un nuevo tipo de partícula llamada "black_hole" que tiene tamaño grande, color negro y velocidad muy lenta. Describe los pasos que necesitarías seguir para implementar esto utilizando la ParticleFactory existente. ¿Tendrías que modificar ofApp::setup? ¿Por qué sí o por qué no?**
>
> Primero añadimos el tipo de particula black_hole en ParticleFactory::createParticle y le damos color tamaño y velocidad
>
> Luego, en efecto, se tiene que modificar el ofApp::setup, ya que alli es donde decimos cuantas particulas de cada tipo queremos. si no lo actualizamos, no se crear. en otras palabras, alli decimos si en definitiva si se va a crear si quiera un tipo de esta particula o no

- ⚫ **El método createParticle en el ejemplo es estático. ¿Qué implicaciones (ventajas/desventajas) tiene esto comparado con tener una instancia de ParticleFactory y un método de instancia createParticle()?.**
>
> La ventaja principal que veo es que al ser estatico no hay que estar instanciando en todos lados, entonces es mas eficaz... pero siento que puede ser muy limitante con los parametros, ademas de que no consigo imaginarme siquiera si se puede mazclar esto con herencias o herencias multiples

## 🐦‍⬛ **ACTIVIDAD 04** 🐦‍⬛

<a name="evidencia4"></a>
- 🌑 **Explica con tus propias palabras el propósito del patrón State. ¿Cuándo es útil aplicarlo?**
>
> El proposito de esta funcion es basucamente ahorrarnos un monton de if/else ne l codigo y simplemente establecemos estados y variables que nos permitan decidir en ellas

- 🕷️ **Dibuja un diagrama de estados simple para la clase Particle. Muestra los diferentes estados (Normal, Attract, Repel, Stop) como nodos y las transiciones entre ellos como flechas etiquetadas con el evento que las causa (p. ej., la tecla presionada: ‘n’, ‘a’, ‘r’, ‘s’).**
>
> <img width="873" height="792" alt="image" src="https://github.com/user-attachments/assets/31eb9088-f478-4dcd-986a-fee2b18e40bd" />


- 🐜**Describe las ventajas de usar el patrón State en Particle en lugar de tener un miembro std::string estadoActual y usar un gran if/else if/else o switch dentro de Particle::update() para cambiar el comportamiento. Piensa en cohesión, extensibilidad (añadir nuevos estados) y el Principio Abierto/Cerrado (Open/Closed Principle).**
>
> Principalmente, todo se veria mas limpio ya que no tenemos que estra llenando todo de condicionales, ademas de que si quiero nuevos estados no necesito modificar tantas cosas

- 🎱 **¿Qué responsabilidad tienen los métodos onEnter y onExit en el patrón State? Proporciona un ejemplo de por qué podrían ser útiles (incluso si no se usan mucho en todos los estados de este caso de estudio). Por ejemplo, ¿Qué podrías hacer en onEnter para AttractState o en onExit para StopState?**
>
> onEnter: inicializa las variables, animaciones
>
> onExit: limpia recursos, detiene animaciones y guarda el estado anterior

## 🐶 **ACTIVIDAD 05** 🐶

<a name="evidencia5"></a>
> <img width="1020" height="756" alt="Captura de pantalla 2025-09-30 082907" src="https://github.com/user-attachments/assets/315857a1-9b2f-4f3a-8a78-6ec8339592a0" />
> <img width="1019" height="764" alt="Captura de pantalla 2025-09-30 082842" src="https://github.com/user-attachments/assets/e24406f1-378a-4542-8d0d-f6a3a626e9cb" />
> <img width="1020" height="765" alt="Captura de pantalla 2025-09-30 082829" src="https://github.com/user-attachments/assets/0fa946b9-0bf0-438a-bc04-3ddc8204c185" />
> <img width="1023" height="770" alt="Captura de pantalla 2025-09-30 082815" src="https://github.com/user-attachments/assets/5d163d2f-a1a9-43cb-ab78-598f71a0b0eb" />


- 🙈**Código fuente de openframeworks**

ofApp.cpp
````c#
#include "ofApp.h"
#include <algorithm>

void Subject::addObserver(Observer* observer) {
    if (!observer) return;
    if (std::find(observers.begin(), observers.end(), observer) == observers.end()) {
        observers.push_back(observer);
    }
}

void Subject::removeObserver(Observer* observer) {
    if (!observer) return;
    observers.erase(std::remove(observers.begin(), observers.end(), observer), observers.end());
}

void Subject::notify(const std::string& event) {
    for (Observer* observer : observers) {
        observer->onNotify(event);
    }
}

Particle::Particle()
    : state(nullptr) {
    position = ofVec2f(ofRandomWidth(), ofRandomHeight());
    velocity = ofVec2f(ofRandom(-0.5f, 0.5f), ofRandom(-0.5f, 0.5f));
    size = ofRandom(2.0f, 5.0f);
    color = ofColor(255);

    state = new NormalState();
    state->onEnter(this);
}

Particle::~Particle() {
    if (state) {
        state->onExit(this);
        delete state;
        state = nullptr;
    }
}

void Particle::setState(State* newState) {
    if (state) {
        state->onExit(this);
        delete state;
    }
    state = newState;
    if (state) {
        state->onEnter(this);
    }
}

void Particle::update() {
    if (state) {
        state->update(this);
    }
    keepInsideWindow();
}

void Particle::draw() {
    ofPushStyle();
    ofSetColor(color);
    ofDrawCircle(position, size);
    ofPopStyle();
}

void Particle::onNotify(const std::string& event) {
    if (event == "attract") {
        setState(new AttractState());
    }
    else if (event == "repel") {
        setState(new RepelState());
    }
    else if (event == "stop") {
        setState(new StopState());
    }
    else if (event == "normal") {
        setState(new NormalState());
    }
}

void Particle::keepInsideWindow() {
    const float W = static_cast<float>(ofGetWidth());
    const float H = static_cast<float>(ofGetHeight());

    if (position.x < 0.0f) {
        position.x = 0.0f;
        velocity.x *= -1.0f;
    }
    else if (position.x > W) {
        position.x = W;
        velocity.x *= -1.0f;
    }
    if (position.y < 0.0f) {
        position.y = 0.0f;
        velocity.y *= -1.0f;
    }
    else if (position.y > H) {
        position.y = H;
        velocity.y *= -1.0f;
    }
}

void NormalState::onEnter(Particle* particle) {
    particle->velocity.set(ofRandom(-0.5f, 0.5f), ofRandom(-0.5f, 0.5f));
}

void NormalState::update(Particle* particle) {
    particle->position += particle->velocity;
}

static void steer(Particle* particle, const ofVec2f& toward, float accel, float vmax, float posScale) {
    ofVec2f dir = toward - particle->position;
    float len = dir.length();
    if (len > 1e-6f) {
        dir /= len;
        particle->velocity += dir * accel;
    }
    particle->velocity.limit(vmax);
    particle->position += particle->velocity * posScale;
}

void AttractState::update(Particle* particle) {
    ofVec2f mouse(ofGetMouseX(), ofGetMouseY());
    steer(particle, mouse, /*accel*/ 0.05f, /*vmax*/ 3.0f, /*posScale*/ 0.2f);
}

void RepelState::update(Particle* particle) {
    ofVec2f mouse(ofGetMouseX(), ofGetMouseY());
    ofVec2f away = particle->position - mouse;
    float len = away.length();
    if (len > 1e-6f) {
        away /= len;
        particle->velocity += away * 0.05f;
    }
    particle->velocity.limit(3.0f);
    particle->position += particle->velocity * 0.2f;
}

void StopState::update(Particle* particle) {
    particle->velocity *= 0.80f;
    if (particle->velocity.lengthSquared() < 1e-4f) {
        particle->velocity.set(0.0f, 0.0f);
    }
    particle->position += particle->velocity;
}

Particle* ParticleFactory::createParticle(const std::string& type) {
    Particle* particle = new Particle();

    if (type == "star") {
        particle->size = ofRandom(2.0f, 4.0f);
        particle->color = ofColor(255, 0, 0);
    }
    else if (type == "shooting_star") {
        particle->size = ofRandom(3.0f, 6.0f);
        particle->color = ofColor(0, 255, 0);
        particle->velocity *= 3.0f;
    }
    else if (type == "planet") {
        particle->size = ofRandom(5.0f, 8.0f);
        particle->color = ofColor(0, 0, 255);
    }
    else if (type == "sun") {
        particle->size = ofRandom(20.0f, 30.0f);
        particle->color = ofColor(225, 225, 0);
        particle->velocity *= 0.5f;
    }
    return particle;
}

ofApp::~ofApp() {
    for (Particle* p : particles) {
        removeObserver(p);
        delete p;
    }
    particles.clear();
}

void ofApp::setup() {
    ofBackground(0);
    particles.reserve(100 + 5 + 10 + 3);

    for (int i = 0; i < 100; ++i) {
        Particle* p = ParticleFactory::createParticle("star");
        particles.push_back(p);
        addObserver(p);
    }
    for (int i = 0; i < 5; ++i) {
        Particle* p = ParticleFactory::createParticle("shooting_star");
        particles.push_back(p);
        addObserver(p);
    }
    for (int i = 0; i < 10; ++i) {
        Particle* p = ParticleFactory::createParticle("planet");
        particles.push_back(p);
        addObserver(p);
    }
    for (int i = 0; i < 3; i++) {
        Particle* p = ParticleFactory::createParticle("sun");
        particles.push_back(p);
        addObserver(p);
    }
}

void ofApp::update() {
    for (Particle* p : particles) {
        p->update();
    }
}

void ofApp::draw() {
    for (Particle* p : particles) {
        p->draw();
    }
}

void ofApp::keyPressed(int key) {
    switch (key) {
    case 's':
        notify("stop");
        break;
    case 'a':
        notify("attract");
        break;
    case 'r':
        notify("repel");
        break;
    case 'n':
        notify("normal");
        break;
    default:
        break;
    }
}
````

ofApp.h
````c#
#pragma once

#include "ofMain.h"
#include <string>
#include <vector>

class Observer {
public:
	virtual ~Observer() = default;
	virtual void onNotify(const std::string& event) = 0;
};

class Subject {
public:
	void addObserver(Observer* observer);
	void removeObserver(Observer* observer);

protected:
	void notify(const std::string& event);

private:
	std::vector<Observer*> observers;
};

class Particle;

class State {
public:
	virtual ~State() = default;
	virtual void update(Particle* particle) = 0;
	virtual void onEnter(Particle* particle) {}
	virtual void onExit(Particle* particle) {}
};

class Particle : public Observer {
public:
	Particle();
	~Particle() override;

	Particle(const Particle&) = delete;
	Particle& operator=(const Particle&) = delete;

	void update();
	void draw();
	void onNotify(const std::string& event) override;

	void setState(State* newState);

	ofVec2f position;
	ofVec2f velocity;
	float size;
	ofColor color;

private:
	void keepInsideWindow();
	State* state;
};

class NormalState : public State {
public:
	void update(Particle* particle) override;
	void onEnter(Particle* particle) override;
};

class AttractState : public State {
public:
	void update(Particle* particle) override;
};

class RepelState : public State {
public:
	void update(Particle* particle) override;
};

class StopState : public State {
public:
	void update(Particle* particle) override;
};

class ParticleFactory {
public:
	static Particle* createParticle(const std::string& type);
};

class ofApp : public ofBaseApp, public Subject {
public:
	~ofApp() override;
	void setup() override;
	void update() override;
	void draw() override;
	void keyPressed(int key) override;

private:
	std::vector<Particle*> particles;
};
````
- 🐗**Explica cómo usaste el patrón Factory para esta nueva partícula**
>
> En realidad el proceso para crear una nueva partícula consistía en añadirla en el factory, darle4 nombre, tamaño, color y velocidad si era necesario y finalmente añadir el "addObserver" que literalemnte se encargaba de añadirle el resto de cosas que hacían falta
>
> De resto solo era necesario añadir la particula nueva con un contador y la cantidad de particulas que queremos que se creen en el setup y ya. El código solitohace el resto

- 🐻**Describe cómo implementaste el patrón Observer para esta nueva partícula**
>
> Una vez añadimos el "addObserver" automaticamente la particula nueva se vuelve un nuevo observador, por ende el código lo tendra en cuenta para enviarle notificaciones una vez hayan cambios en los estados

- 🐴**Explica cómo aplicaste el patrón State a esta nueva partícula.**
>
> Ahora que nuestra particula es un nuevo observador que esta atento a as notificaciones y sabemos que actuará con respecto a cada una de ellas, el patron state se activa cuando presionamos una nueva tecla, se cambia el estado en el que están las particulas y se les notifica.

## 🫏 **AUTOEVALUACIÓN** 🫏

- 🦭**Mi nota propuesta:** 5
- 🤺**Justificación:**
>
> El estudiante se esfuerza por tratar de entender el funcionamiento básico del programa y sus interacciones con el usuario
>
> [evidencia actividad 1](#evidencia1)
>
> El estudiante analiza y comprende las facilidades que proporciona el patrón observer, asi como consigue entender su comportamiento
>
> [evidencia actividad 2](#evidencia2)
>
> El estudiante comprende el funcionamiento del patron factory como corazón principal de la creación de particulas, asi mismo el como el patron factory y el observer se enlazan entre si
>
> [evidencia actividad 3](#evidencia3)
>
> El estudiante afina sus hipótesis del funcionamiento del patron state gracias al comportamiento de factory y observer, donde comprende finalmente de donde nacen inicialemnte las notficaciones que eventualmente envia el concrete subject a la interfaz de observer
>
> [evidencia actividad 4](#evidencia4)
>
> El estudiante consgue entender que solamente es necesario hacer que nazca una particula nueva desde el factory, añadirla como obervador y que haga parte del setup, ya que el resto de las cosas el código consigue hacerlas por su cuenta grcias a sus comportamientos y automatización
>
> [evidencia actividad 5](#evidencia5)
