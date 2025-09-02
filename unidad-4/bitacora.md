# Evidencias para la unidad 4

## Código

Código para ofApp.h:

``` cpp
#pragma once
#include "ofMain.h"

// Nodo de la cola
struct Node {
    float x, y;
    float radius;
    ofColor color;
    float opacity;
    Node* next;

    Node(float _x, float _y, float _radius, ofColor _color, float _opacity)
        : x(_x), y(_y), radius(_radius), color(_color), opacity(_opacity), next(nullptr) {
    }
};

// Implementación manual de una cola (FIFO)
class BrushQueue {
public:
    Node* front;
    Node* rear;
    int size;
    int maxSize;

    BrushQueue(int _maxSize);
    ~BrushQueue();

    void enqueue(float x, float y, float radius, ofColor color, float opacity);
    void dequeue();
    void clear();
    bool isEmpty();
};


// Constructor
BrushQueue::BrushQueue(int _maxSize) : front(nullptr), rear(nullptr), size(0), maxSize(_maxSize) {}

// Destructor
BrushQueue::~BrushQueue() {
    clear();
}

// Implementa aquí `enqueue()`
void BrushQueue::enqueue(float x, float y, float radius, ofColor color, float opacity) {
    Node* newNode = new Node(x, y, radius, color, opacity);

    if (rear == nullptr) { // cola vacía
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
    size++;

    if (size > maxSize) {
        dequeue();
    }
}

// Implementa aquí `dequeue()`
void BrushQueue::dequeue() {
    if (front == nullptr) return;

    Node* temp = front;
    front = front->next;
    if (front == nullptr) {
        rear = nullptr;
    }
    delete temp;
    size--;
}

// Implementa aquí `clear()`
void BrushQueue::clear() {
    while (front != nullptr) {
        Node* nextNode = front->next;
        delete front;
        front = nextNode;
    }
    rear = nullptr;
    size = 0;
}

// Implementa aquí `isEmpty()`
bool BrushQueue::isEmpty() {
    return front == nullptr;
}


class ofApp : public ofBaseApp {
public:
    BrushQueue strokes; // Cola de trazos
    float backgroundHue = 0;

    ofApp() : strokes(50) {} // Tamaño máximo de la cola

    void setup();
    void update();
    void draw();
    void keyPressed(int key);
};

```

Código para ofApp.cpp:

``` cpp
#include "ofApp.h"

//--------------------------------------------------------------
void ofApp::setup() {
    ofBackground(0);
}

//--------------------------------------------------------------
void ofApp::update() {
    backgroundHue += 0.2;
    if (backgroundHue > 255) backgroundHue = 0;

    // TODO: agregar un nuevo trazo si el mouse está presionado.
    if (ofGetMousePressed()) {
        float x = ofGetMouseX();
        float y = ofGetMouseY();
        float radius = ofRandom(6, 16);
        ofColor color = ofColor::fromHsb(ofRandom(255), 220, 255);
        float opacity = 255;

        strokes.enqueue(x, y, radius, color, opacity);
    }
}

//--------------------------------------------------------------
void ofApp::draw() {
    // Fondo con gradiente dinámico
    ofColor color1, color2;
    color1.setHsb(backgroundHue, 150, 240);
    color2.setHsb(fmod(backgroundHue + 128, 255), 150, 240);
    ofBackgroundGradient(color1, color2, OF_GRADIENT_LINEAR);

    // TODO: dibujar los trazos almacenados en la cola.
    Node* cur = strokes.front;
    int i = 0;
    int denom = std::max(1, strokes.size - 1);

    while (cur != nullptr) {
        float alpha = (strokes.size <= 1)
            ? 255.0f
            : ofMap(i, 0, denom, 40.0f, 255.0f, true);

        ofSetColor(cur->color, (unsigned char)alpha);
        ofDrawCircle(cur->x, cur->y, cur->radius);

        cur = cur->next;
        i++;
    }

    ofSetColor(255);
    ofDrawBitmapString("maxSize = " + ofToString(strokes.maxSize), 12, 18);
}

//--------------------------------------------------------------
void ofApp::keyPressed(int key) {
    if (key == 'c') {
        // TODO: limpiar la cola de trazos.
        strokes.clear();
    }
    if (key == 'a') {
        // TODO: alternar entre 50 y 100 trazos.
        strokes.maxSize = (strokes.maxSize == 50) ? 100 : 50;
        while (strokes.size > strokes.maxSize) {
            strokes.dequeue();
        }
    }
    else if (key == 's') {
        // TODO: guardar el frame actual.
        ofSaveFrame();
    }
}

```

Código para main.cpp:
``` cpp
#include "ofMain.h"
#include "ofApp.h"

//========================================================================
int main( ){

	//Use ofGLFWWindowSettings for more options like multi-monitor fullscreen
	ofGLWindowSettings settings;
	settings.setSize(1024, 768);
	settings.windowMode = OF_WINDOW; //can also be OF_FULLSCREEN

	auto window = ofCreateWindow(settings);

	ofRunApp(window, std::make_shared<ofApp>());
	ofRunMainLoop();

}

```

## Demostración:

[Aquí está el video demostrativo de mi aplicación](url del video no listado en youtube)


