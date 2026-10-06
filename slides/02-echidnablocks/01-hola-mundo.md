---
marp: true
theme: echidna
paginate: true
footer: "2.1 Hola Mundo · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "" -->

# 2.1 Hola Mundo

![Hola Mundo](../assets/images/Hola_Mundo.png)

Proyectos de inicio con EchidnaML

<!--
Notas del docente: primer proyecto. Antes de empezar, comprueba que la
placa EchidnaBlack2 está conectada y que EchidnaML la detecta (ver la
presentación de EchidnaBlocks en la guía).
-->

---

<!-- _class: seccion -->

## 1. Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

<div class="dos-columnas">
<div>

Vamos a hacer que el **LED rojo** de la placa se **encienda y se apague** sin parar.

Es el «Hola Mundo» de la electrónica: el primer programa que se hace con una placa nueva.

</div>
<div>

![LED rojo parpadeando en EchidnaBlack2](../assets/images/Hola_Mundo_funcionamiento.gif)

</div>
</div>

<!--
Muestra el resultado antes de programar: así el alumnado sabe a dónde
tiene que llegar.
-->

---

## Qué vamos a aprender

- A crear nuestro **primer programa** en EchidnaML.
- A usar un **bucle infinito** para hacer una **programación cíclica**: tareas que se repiten para siempre.
- A controlar el estado de un componente de la placa: **encendido** o **apagado**.

---

## Componentes

<div class="dos-columnas">
<div>

- **LED rojo:** se enciende y se apaga para crear el parpadeo.

La placa tiene tres LED: **verde**, **naranja** y **rojo**.

</div>
<div>

![LED en EchidnaBlack2](../assets/images/Lupa_Ledes.png)

</div>
</div>

---

## Programación

Para encender y apagar los LED usamos el bloque `encender LED`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_LED.png" alt="Bloque encender LED">
</div>

En el bloque elegimos:

- si queremos **encender** o **apagar** el LED,
- **qué LED**: verde, naranja o rojo.

---

<!-- _class: seccion -->

## 2. Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** para ejecutarlo.

</div>
<div class="centro">

![Bloques programación Hola Mundo](../assets/images/HolaMundo.png)

</div>
</div>

<!--
En la web de la guía hay un GIF con el paso a paso para construirlo.
-->

---

## Cómo funciona

`al hacer clic en` (bandera verde): lo que va debajo se ejecuta al pulsar la bandera.

`por siempre` repite estos pasos, de arriba a abajo, sin parar:

1. `encender LED rojo`: enciende el LED.
2. `esperar 1 segundos`: lo mantiene encendido un segundo.
3. `apagar LED rojo`: apaga el LED.
4. `esperar 1 segundos`: lo mantiene apagado un segundo y vuelve al paso 1.

<!--
Errores típicos:
- Falta el segundo `esperar`: el LED se apaga y se vuelve a encender al
  instante, así que parece que está siempre encendido.
- Falta el `por siempre`: el LED parpadea una sola vez.
- El LED elegido en el bloque no es el rojo.
- La placa no está conectada o EchidnaML no la detecta.
-->

---

<!-- _class: seccion -->

## 3. Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Ritmo rápido

Cambia el tiempo de espera a `0.2` segundos.

- ¿Qué le ocurre al parpadeo?
- ¿Qué ocurre si sigues bajando el tiempo de espera?

<div class="pista">

**Pista:** cambia el valor de los dos bloques `esperar`.

</div>

<!--
Con tiempos muy pequeños el ojo deja de ver el parpadeo y parece que el
LED está siempre encendido (persistencia de la visión).
-->

---

## Mejóralo 1: Ayuda

<div class="pendiente">

IMAGEN AYUDA HOLA MUNDO MEJORA 1

</div>

---

## Mejóralo 2: Sombra de señal

Haz que el LED esté **encendido mucho tiempo** (`2` segundos) y **apagado muy poco** (`0.1` segundos).

<div class="pista">

**Pista:** cada bloque `esperar` controla una parte del ciclo: el primero, el tiempo encendido; el segundo, el tiempo apagado.

</div>

---

## Mejóralo 2: Ayuda

<div class="pendiente">

IMAGEN AYUDA HOLA MUNDO MEJORA 2

</div>

---

## Mejóralo 3: LED virtual en pantalla

Crea un **objeto** en EchidnaML que cambie de **disfraz** para simular en la pantalla el mismo parpadeo que ocurre en la placa.

<div class="pista">

**Pista:** para sincronizar el objeto LED, lo podemos hacer mediante **mensajes**.

</div>

---

## Mejóralo 3: Ayuda

<div class="pendiente">

IMAGEN AYUDA HOLA MUNDO MEJORA 3

</div>

<div class="pendiente">

IMAGEN DISFRACES LED

</div>

---

<!-- _class: seccion -->

## 4. Evaluación

¿Qué hemos aprendido?

---

## Comprueba lo que sabes

1. ¿Qué ocurre si quitamos el bloque `por siempre`?
2. ¿Y si quitamos el último bloque `esperar`?
3. ¿Qué cambiarías para que parpadee el LED **verde**?
4. ¿Qué es una **programación cíclica**?

<!--
Respuestas:
1. El LED se enciende y se apaga una sola vez.
2. El LED se apaga y se vuelve a encender al instante: parece que está
   siempre encendido.
3. Elegir «verde» en los dos bloques `encender LED` / `apagar LED`.
4. Un programa con tareas que se repiten para siempre, dentro de un bucle
   infinito como `por siempre`.
-->

---

## He conseguido...

<div class="logros">

- Hacer parpadear el LED rojo.
- Cambiar la velocidad del parpadeo (Mejóralo 1).
- Cambiar el tiempo encendido y apagado por separado (Mejóralo 2).
- Simular el LED en la pantalla con mensajes (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el programa o no consigue que
  el LED parpadee.
- Conseguido: el programa funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 sincronizando el objeto con
  mensajes.
-->

---

## Qué he aprendido

<div class="logros">

- A crear mi **primer programa** en EchidnaML.
- A usar un **bucle infinito** para hacer una **programación cíclica**: tareas que se repiten para siempre.
- A controlar el estado de un componente de la placa: **encendido** o **apagado**.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya has hecho tu primer programa con EchidnaML.

Siguiente proyecto: **2.2 Semáforo**
