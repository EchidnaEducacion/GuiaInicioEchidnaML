---
marp: true
theme: echidna
paginate: true
footer: "2.11 Movemos el echidna · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.11 Movemos el echidna

![Movemos el echidna](../assets/images/Movemos_echidna.png)

<!--
Notas del docente: último proyecto con EchidnaBlocks. Se presenta el
acelerómetro y la placa pasa a ser un mando de videojuego. Es el primer
proyecto con dos hilos de ejecución que funcionan a la vez.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a convertir la placa en un **mando de videojuego**:

- al **inclinar la placa** hacia un lado, el echidna se moverá por la pantalla en esa dirección;
- si **levantas la placa de golpe**, el echidna dará un **salto**.

<!--
Pregunta antes de programar: ¿qué mandos o móviles conocéis que
reaccionan al inclinarlos? (mandos de consola, juegos de carreras en el
móvil, la pantalla que gira…).
-->

---

## Qué vamos a aprender

- A utilizar el **acelerómetro** para detectar la **inclinación** y los **movimientos bruscos** de la placa.
- A leer los valores de los tres ejes: **X**, **Y** y **Z**.
- A mover un personaje por el escenario usando sus **coordenadas** (`sumar a x` y `sumar a y`).
- A animar un personaje cambiando de **disfraz**.
- A ejecutar dos programas a la vez usando **dos hilos** de ejecución.

---

## Componentes

<div class="dos-columnas">
<div>

- **Acelerómetro:** mide los movimientos de la placa en tres ejes.
- **X** e **Y**: hacia dónde **inclinas** la placa.
- **Z**: los movimientos **bruscos** hacia arriba o abajo.

</div>
<div>

![Acelerómetro en EchidnaBlack2](../assets/images/Lupa_Acelerometro.png)

</div>
</div>

<!--
Los ejes X e Y detectan la inclinación gracias a la fuerza de la
gravedad.
-->

---

## Programación

Para leer el acelerómetro usamos el bloque `leer acelerómetro`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_acelerometro.png" alt="Bloque leer acelerómetro">
</div>

- En **reposo**: alrededor de **0** en X e Y, y de **1** en Z.
- **Ejes X e Y:** al inclinar la placa, van de **-1** a **1**.
- **Eje Z:** con un movimiento brusco se aleja mucho de **1**.

<!--
En el bloque se elige el eje: x, y o z. Marcar la casilla junto al
bloque para ver los valores en el escenario mientras se inclina la
placa.
-->

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

En el **Echidna**, **dos hilos** que empiezan a la vez con la **bandera verde**:

<div class="centro">

![height:380px Bloques programación Movemos el echidna](../assets/images/Ejemplo_acelerometro.png)

</div>

<!--
Hilo de movimiento: si la placa está inclinada, el echidna se desplaza y
cambia de disfraz. Hilo de salto: si se levanta de golpe, sube y vuelve
a bajar.

El cambio de disfraz hace que parezca que camina. Al saltar sube 50
pasos: 10 veces 5.
-->

---

## Cómo funciona: movimiento

```
SI el eje x es menor de -0,5 (inclinada a la izquierda):
    --> El echidna se desplaza hacia la izquierda.
SI el eje x es mayor de 0,5 (inclinada a la derecha):
    --> El echidna se desplaza hacia la derecha.
SI el eje y es menor de -0,5 (inclinada hacia atrás):
    --> El echidna se desplaza hacia abajo.
SI el eje y es mayor de 0,5 (inclinada hacia delante):
    --> El echidna se desplaza hacia arriba.
```

Con la placa **casi plana**, el echidna se queda quieto.

<!--
Los valores 0,5 y -0,5 son los umbrales.

Errores típicos:
- Confundir el eje o el signo: el echidna va al revés.
- Poner `sumar a x` donde va `sumar a y`.
-->

---

## Cómo funciona: salto

```
SI el eje z es mayor de 1,5 (placa levantada de golpe):
    --> El echidna salta: sube y vuelve a bajar.
```

Los dos hilos funcionan **al mismo tiempo**: el echidna puede saltar mientras se mueve.

<!--
Si todo estuviera en un solo `por siempre`, durante el salto el echidna
no podría moverse hacia los lados.

Aviso: al levantar la placa de golpe, sujetarla bien y con cuidado del
cable USB.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Sin salirse de la pantalla

Haz que el echidna **vuelva al centro** del escenario al hacer clic en la bandera verde y que **no pueda salirse** por los bordes.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** al empezar, usa `ir a x: 0 y: 0`. Para que no se salga, usa el bloque `rebotar si toca un borde`.

</div>

---

## Mejóralo 2: Salto con efectos

Haz que, cada vez que el echidna salte, suene el **zumbador** y se encienda el **LED RGB**.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** en el hilo de salto, dentro del `si`, enciende el zumbador y el `LED R G B` antes de subir, y apágalos cuando vuelva a bajar.

</div>

---

## Mejóralo 3: Recoge la comida

Añade un **nuevo objeto** (por ejemplo, una hormiga) en una **posición al azar**.

Cuando el echidna lo toque, **suma un punto** a una **variable** y mueve la comida a otra posición al azar.

---

## Mejóralo 3: Pista

<div class="pista">

**Pista:** en el nuevo objeto «comida», crea la variable `puntos` y ponla a `0` al empezar. Dentro de un `por siempre`, usa `si ¿tocando Echidna? entonces` con `sumar a puntos 1` e `ir a posición aleatoria`.

</div>

<!--
El programa va en el objeto de la comida, no en el echidna. Marcando la
casilla de la variable, los puntos se ven en el escenario.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué valor da el eje **z** con la placa en reposo?
2. ¿Qué pasa si inclinas la placa **muy poco**?
3. ¿Qué es un **hilo** y por qué usamos dos?
4. ¿Cuántos pasos sube el echidna al saltar?

<!--
Respuestas:
1. Alrededor de 1.
2. Nada: no se llega al umbral de 0,5 y el echidna se queda quieto.
3. Un grupo de bloques que funciona a la vez que otros. Usamos dos para
   que el echidna pueda moverse y saltar al mismo tiempo.
4. 50 pasos: repite 10 veces sumar 5.
-->

---

## He conseguido…

<div class="logros">

- Mover el echidna inclinando la placa y hacerlo saltar.
- Que no se salga de la pantalla (Mejóralo 1).
- Que suene el zumbador y se encienda el LED RGB al saltar (Mejóralo 2).
- Recoger comida y contar los puntos (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir los condicionales o
  entender los dos hilos.
- Conseguido: el juego funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con la variable de puntos.
-->

---

## Qué he aprendido

<div class="logros">

- A utilizar el **acelerómetro** para detectar la **inclinación** y los **movimientos bruscos** de la placa.
- A leer los valores de los tres ejes: **X**, **Y** y **Z**.
- A mover un personaje por el escenario usando sus **coordenadas** (`sumar a x` y `sumar a y`).
- A animar un personaje cambiando de **disfraz**.
- A ejecutar dos programas a la vez usando **dos hilos** de ejecución.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes usar la placa como mando de videojuego.

Siguiente proyecto: **3.1 Asistente virtual**

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
