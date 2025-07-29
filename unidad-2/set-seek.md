# Unidad 2

## 🔎 Fase: Set + Seek

─── ･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆: *.☽ .* :☆｡ﾟ.･ ｡ﾟ☆───

### **ACTIVIDAD 01 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@SCREEN
M=1
```
```
screen = 1;
```
<img width="388" height="38" alt="image" src="https://github.com/user-attachments/assets/40d4efa1-15a2-46c0-b22a-d35c1e588f41" />

### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  *predice, ejecuta, observa y reflexiona*
PREDICE: Gracias a la etiqueta SCREEN, el compuatdor debe iniciar la posición de la pantalla, es decir, 16384. Luego asignamos un 1 en uno de los 16 dígitos de la posición 16384

EJECUTA: En efecto, ttras pasar el código a NAND2tetris, la etiqueta SCREEN se transporma en 16384, luego lo lee y A pasa a dicho valor. Luego M=1 asigna un valor al 16384 de RAM que acabamos de leer y asigna el 1 en el último valor de los 16 ceros que hay

OBSERVA: El código funciona con normalidad. el pixel es super chiquito, pero funciona

REFLEXIONA:

### **ACTIVIDAD 02 ༓☾∘∙•⋅⋅⊰⋅•⋅**
```
@SCREEN
M=-1
```
```
screen = -1;
screen = 0xFFF;
```
<img width="358" height="30" alt="image" src="https://github.com/user-attachments/assets/fe1fd9e0-16af-4807-8311-1ef13ec75358" />

### **BITÁCORA 𖤓 ☆ ☼ ⋆⋅**
-  *predice, ejecuta, observa y reflexiona*
PREDICE: Gracias a la etiqueta SCREEN, el compuatdor debe iniciar la posición de la pantalla, es decir, 16384. Luego asignamos un -1, el cual representa un numero enorme en positivos, y llena las 16 casillas de ese lugar 

EJECUTA: En efecto, ttras pasar el código a NAND2tetris, la etiqueta SCREEN se transporma en 16384, luego lo lee y A pasa a dicho valor. Luego M=-1 asigna un valor al 16384 de RAM que acabamos de leer y llena todas las 16 casillas

OBSERVA: Se ve claramente la linea con los 16 pixeles llenos

REFLEXIONA: No es necesario llenar todas las 16 casillas una por una. podemos poner un numero grande directamente 
