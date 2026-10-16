---
marp: true
theme: echidna
paginate: true
footer: "3.2 Clasificador de residuos · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 3.2 Clasificador de residuos

![Modelo de imágenes](../assets/images/Modelo_IA_imagenes.png)

<!--
Notas del docente: segundo proyecto con IA, ahora con un modelo de
imágenes. Se presentan la cámara (webcam) en EchidnaBlocks y el servomotor
de posición. Hace falta una webcam y dos servos con alimentación externa.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a construir un **clasificador de residuos** que nos ayuda a reciclar. Enseñamos un residuo a la **cámara** y el sistema decide si va al contenedor **amarillo** (envases) o al **azul** (papel y cartón).

Después enciende el **LED RGB** del color del contenedor y **abre** su tapa con un **servomotor**.

Para que reconozca los residuos, crearemos con **LearningML** un **modelo de imágenes**.

---

## Qué vamos a aprender

- A crear un **modelo de machine learning** que clasifica **imágenes**.
- A preparar buenas **imágenes de entrenamiento** para cada **clase**.
- A usar la **cámara** (webcam) en EchidnaBlocks para clasificar lo que ve.
- A mover un **servomotor de posición** a un ángulo concreto.

---

## Componentes

<div class="dos-columnas">
<div>

- **Cámara** del ordenador.
- **LED RGB** de la placa.
- Dos **servomotores de posición**: **D7** (azul) y **D8** (amarillo).

**¡Atención!** Con dos servos, usa alimentación externa y pon el selector en **Vin**.

</div>
<div>

![Conexión del servomotor](../assets/images/Conexion_Servo_posicion.png)

</div>
</div>

<!--
Cables del servo: rojo a Vcc, negro a GND y amarillo a la señal. Sin
alimentación externa, los dos servos pueden pedir más corriente de la que
da el USB y la placa se reinicia o los servos tiemblan.
-->

---

## Programación

Para usar el modelo en nuestro programa usamos el bloque `clasificar imagen`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_clasificar_imagen.png" alt="Bloque clasificar imagen">
</div>

Le damos una **imagen** (la de la cámara, con el bloque `imagen de vídeo`) y nos devuelve la **clase** más probable: **azul** o **amarillo**.

---

<!-- _class: seccion -->

## **2** Entrenamos el modelo

Entrenar, aprender y probar en LearningML

---

## Entrenar: clases y ejemplos

Abrimos LearningML, elegimos un modelo de **imágenes** y creamos dos **clases** con fotos de residuos (desde un archivo o con la cámara):

<div class="dos-columnas">
<div class="centro">

![Clase azul](../assets/images/imagen_clase_azul.png)

**azul:** papel y cartón

</div>
<div class="centro">

![Clase amarillo](../assets/images/imagen_clase_amarillo.png)

**amarillo:** envases

</div>
</div>

<!--
Para que el modelo aprenda bien hacen falta muchos residuos distintos en
cada clase (en el ejemplo, 22 imágenes por clase), vistos desde varias
posiciones. Conviene que el fondo y la luz sean parecidos en las dos
clases: si no, el modelo puede aprender el fondo en lugar del residuo.
-->

---

## Aprender

<div class="dos-columnas" style="grid-template-columns: 3fr 2fr;">
<div>

Pulsamos **Aprender a reconocer imágenes**.

El algoritmo analiza las imágenes y construye un **modelo** capaz de reconocer imágenes parecidas, pero distintas.

Con imágenes tarda **varios segundos**, y más cuantas más imágenes haya.

</div>
<div class="centro">

![Aprender a reconocer imágenes](../assets/images/Aprender_imagenes.png)

</div>
</div>

---

## Probar

<div class="dos-columnas" style="grid-template-columns: 3fr 2fr;">
<div>

Enseñamos a la cámara residuos **nuevos** y vemos su clase y su **confianza**.

Una botella sale **amarillo** con un 91,68 %.

Si se equivoca, volvemos a **Entrenar**: más imágenes o revisamos las que hay.

</div>
<div class="centro">

![Probar el modelo de imágenes](../assets/images/prueba_modelo_imagenes.png)

</div>
</div>

---

<!-- _class: seccion -->

## **3** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="centro">

![h:500px Bloques programación Clasificador de residuos](../assets/images/Ejemplo_modelo_imagenes.png)

</div>

---

## Cómo funciona

Con la **bandera verde**: activamos la cámara, cerramos las tapas (servos a 90°) y apagamos el LED RGB.

Al pulsar **espacio**, el programa clasifica la imagen de la cámara:

```
SI la clase es "azul":
    --> Servo D7 a 180° y LED RGB en azul.
SI la clase es "amarillo":
    --> Servo D8 a 180° y LED RGB en amarillo.
```

A los **2 segundos** cierra el contenedor (90°) y apaga el LED.

<!--
Azul es R 0, G 0, B 255; amarillo, R 255, G 255, B 0.

Errores típicos:
- Los nombres de las clases del programa no coinciden con los del modelo.
- Falta `activar vídeo ON`: la cámara no se enciende.
- Los servos están en otros pines o sin alimentación externa.
- El fondo o la luz de clase son muy distintos de los del entrenamiento.
-->

---

<!-- _class: seccion -->

## **4** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Dímelo en pantalla

Haz que el echidna diga a qué contenedor va el residuo: "¡Al amarillo!" o "¡Al azul!".

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** añade un bloque `decir` dentro de cada `si`, junto a los bloques del servo y del LED.

</div>

---

## Mejóralo 2: Solo si está seguro

Usa el bloque `confianza para la imagen` para que solo abra un contenedor si la confianza es **mayor de 70**.

Si no, el echidna dirá "No estoy seguro, prueba otra vez".

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** mete los dos `si` dentro de un `si … si no` que compare la `confianza para la imagen` (con `imagen de vídeo`) con 70, como en el Asistente virtual.

</div>

---

## Mejóralo 3: Contenedor verde

Añade la clase **verde** (vidrio) con imágenes de botellas y tarros, un tercer servomotor en el pin **D4** y el LED RGB en verde.

---

## Mejóralo 3: Pista

<div class="pista">

**Pista:** entrena la clase **verde** en LearningML, coloca el servo D4 a 90° al empezar y añade un tercer `si` con el servo D4 y el LED RGB en verde (R 0, G 255, B 0).

</div>

---

<!-- _class: seccion -->

## **5** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Por qué conviene añadir **muchas imágenes distintas** a cada clase?
2. ¿Qué hace el bloque `imagen de vídeo`?
3. ¿Por qué probamos el modelo con residuos que **no** usamos al entrenar?
4. ¿Qué ángulo cierra las tapas? ¿Y cuál las abre?

<!--
Respuestas:
1. Para que el modelo aprenda cómo es la clase y no solo esas fotos
   concretas: así reconoce residuos nuevos.
2. Da la imagen que está viendo la cámara en ese momento, para pasarla al
   bloque `clasificar imagen`.
3. Para comprobar que ha aprendido y no solo ha memorizado las imágenes.
4. 90° las cierra y 180° las abre.
-->

---

## He conseguido…

<div class="logros">

- Entrenar un modelo que distingue envases y cartón.
- Abrir el contenedor correcto con el servo y encender el LED de su color.
- Que el echidna diga a qué contenedor va (Mejóralo 1).
- Abrir solo si el modelo está seguro (Mejóralo 2).
- Añadir el contenedor verde (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para entrenar el modelo o los servos no
  responden.
- Conseguido: el clasificador funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con la clase verde y el tercer servo.
-->

---

## Qué he aprendido

<div class="logros">

- A crear un **modelo de machine learning** que clasifica **imágenes**.
- A preparar buenas **imágenes de entrenamiento** para cada **clase**.
- A usar la **cámara** (webcam) en EchidnaBlocks para clasificar lo que ve.
- A mover un **servomotor de posición** a un ángulo concreto.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya has enseñado a una máquina a reconocer imágenes.

Siguiente proyecto: **3.3 Mando de inclinación**

---

## Licencia

<div class="licencia">

![Licencia Creative Commons BY-SA 4.0](../assets/images/Licencia_CC_BY-SA.svg)

**Proyectos de inicio con EchidnaML** · **Autoría:** Echidna Educación

Licencia <a href="https://creativecommons.org/licenses/by-sa/4.0/deed.es" target="_blank" rel="noopener">Creative Commons Reconocimiento-CompartirIgual 4.0 (CC BY-SA 4.0)</a>

</div>

<div class="dos-columnas arriba">
<div>

Puedes:

- **Compartir:** copiar y redistribuir el material.
- **Adaptar:** remezclar, transformar y crear a partir de él, incluso con fines comerciales.

</div>
<div>

Siempre que:

- **Reconocimiento:** cites la autoría, enlaces la licencia e indiques si has hecho cambios.
- **Compartir igual:** difundas tu obra con la misma licencia.

</div>
</div>
