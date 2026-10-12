---
marp: true
theme: echidna
paginate: true
footer: "2.2 Semáforo · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.2 Semáforo

![Semáforo](../assets/images/EchidnaSemaforo.png)

<!--
Notas del docente: segundo proyecto. Usa el mismo bloque que Hola Mundo
(`encender LED`), ahora con los tres LED coordinados. Si el alumnado viene
de 2.1, puede partir de ese programa.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

<div class="dos-columnas">
<div>

Vamos a convertir la placa en un **semáforo**:

- el LED **verde** se enciende **5 segundos**,
- luego el **naranja**, **2 segundos**,
- y por último el **rojo**, **5 segundos**.

El ciclo se repite sin parar.

</div>
<div>

![Semáforo funcionando en EchidnaBlack2](../assets/images/Semaforo_funcionamiento.gif)

</div>
</div>

<!--
Muestra el resultado antes de programar y pregunta en qué orden cambian
las luces de un semáforo de verdad y cuánto dura cada una.
-->

---

## Qué vamos a aprender

- A diseñar **secuencias temporizadas**: eventos que ocurren en un orden y un tiempo exactos.
- A controlar varios componentes (los LED) de forma coordinada.
- A estructurar un ciclo de estados infinito (**programación cíclica**).

---

## Componentes

<div class="dos-columnas">
<div>

- **LED verde:** fase de paso.
- **LED naranja:** fase de precaución.
- **LED rojo:** fase de detención.

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

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** para ejecutarlo.

</div>
<div class="centro">

![Bloques programación semáforo](../assets/images/Semaforo.png)

</div>
</div>

<!--
En la web de la guía está el programa completo. Truco: construye la fase
verde, duplícala dos veces y cambia el color y el tiempo en cada copia.
-->

---

## Cómo funciona

`por siempre` repite tres fases, una detrás de otra. Cada fase tiene tres bloques: **encender** el LED, **esperar** y **apagar** el LED.

1. **Verde:** `encender LED verde`, `esperar 5 segundos` y `apagar LED verde`.
2. **Naranja:** `encender LED naranja`, `esperar 2 segundos` y `apagar LED naranja`.
3. **Rojo:** `encender LED rojo`, `esperar 5 segundos` y `apagar LED rojo`.

Después, el ciclo vuelve a empezar por el verde.

<!--
Errores típicos:
- Falta un `apagar LED`: ese LED se queda encendido junto con el siguiente.
- Al duplicar una fase, no se cambia el color en los dos bloques (encender
  y apagar), o se cambia en uno solo.
- Los tiempos no están en su fase (por ejemplo, el naranja dura 5 s).
- Falta el `por siempre`: el semáforo hace un solo ciclo.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Naranja intermitente

Haz que el LED naranja no se quede fijo, sino que **parpadee 3 veces rápidas** (encendido `0.3` segundos y apagado `0.3` segundos) antes de pasar al rojo.

<!--
Dentro de `repetir 3`: encender LED naranja, esperar 0.3, apagar LED
naranja, esperar 0.3. Sustituye a la fase naranja original.
-->

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** usa el bloque `repetir 3` con un parpadeo dentro.

</div>

---

## Mejóralo 2: Semáforo virtual en pantalla

Diseña un **objeto** «Semáforo» en EchidnaML con tres **disfraces** (verde, naranja y rojo).

Prográmalo para que cambie de disfraz en la pantalla **al mismo tiempo** que cambian los LED de la placa.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** como en Hola Mundo, sincroniza el objeto con **mensajes**: envía uno al empezar cada fase y, en el objeto, cambia de disfraz al recibirlo.

</div>

---

## Mejóralo 3: Semáforo sonoro adaptado

Añade el **zumbador** de la placa para avisar a las personas con discapacidad visual:

- **Fase verde:** sonido intermitente lento.
- **Fase roja:** sonido continuo o apagado.

<!--
Por ejemplo, `repetir 5` con encender zumbador, esperar 0.5, apagar
zumbador y esperar 0.5: dura 5 segundos, como la fase original.
Es la primera vez que se usa el zumbador; se presenta en 2.4 Timbre.
El volumen se ajusta con el potenciómetro Volume de la placa: bájalo antes
de empezar si hay muchas placas sonando en el aula.
-->

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** cambia el `esperar 5 segundos` del verde por un `repetir` que encienda y apague el zumbador con el bloque `encender zumbador`.

</div>

<div class="pendiente">

<img class="img-bloque" src="../assets/images/Bloque_zumbador.png" alt="Bloque encender zumbador">

</div>

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Cuánto dura un ciclo completo del semáforo?
2. ¿Qué ocurre si quitamos el bloque `apagar LED verde`?
3. ¿Qué cambiarías para que el rojo dure el **doble**?
4. ¿Qué es una **secuencia temporizada**?

<!--
Respuestas:
1. 12 segundos: 5 (verde) + 2 (naranja) + 5 (rojo).
2. El LED verde no se apaga nunca: se queda encendido junto al naranja y
   al rojo.
3. Cambiar el último `esperar` de 5 a 10 segundos.
4. Una serie de acciones que ocurren en un orden fijo y durante un tiempo
   exacto, como las fases del semáforo.
-->

---

## He conseguido…

<div class="logros">

- Hacer funcionar el semáforo con sus tres fases.
- Hacer parpadear el naranja antes del rojo (Mejóralo 1).
- Simular el semáforo en la pantalla con mensajes (Mejóralo 2).
- Añadir avisos sonoros con el zumbador (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el programa o las fases no
  van en orden o con sus tiempos.
- Conseguido: el semáforo funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 manteniendo la duración de cada
  fase.
-->

---

## Qué he aprendido

<div class="logros">

- A diseñar **secuencias temporizadas**: eventos que ocurren en un orden y un tiempo exactos.
- A controlar varios componentes (los LED) de forma coordinada.
- A estructurar un ciclo de estados infinito (**programación cíclica**).

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes coordinar varios LED en una secuencia.

Siguiente proyecto: **2.3 Interruptor de luz**

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
