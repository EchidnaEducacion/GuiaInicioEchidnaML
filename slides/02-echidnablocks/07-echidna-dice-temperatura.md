---
marp: true
theme: echidna
paginate: true
footer: "2.7 El echidna dice la temperatura · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.7 El echidna dice la temperatura

![El echidna dice la temperatura](../assets/images/Temperatura.png)

<!--
Notas del docente: la placa y el escenario trabajan juntos. El sensor
mide la temperatura y el personaje de EchidnaML la dice en un bocadillo.
Es el primer proyecto que empieza con una tecla del ordenador y no con
la bandera verde, y el primero que construye frases con `unir`.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

<div class="dos-columnas">
<div>

Vamos a convertir a nuestro echidna en un **hombre del tiempo**.

Cada vez que pulses la tecla **t** del ordenador, el echidna dirá en un bocadillo qué **temperatura** hace, medida con el sensor de la placa.

</div>
<div class="centro">

![El echidna dice la temperatura](../assets/images/Echidna_dice-temperatura.png)

</div>
</div>

<!--
Pregunta antes de programar: ¿qué temperatura creéis que hace en el
aula? Apuntad las estimaciones y comparadlas con lo que diga el echidna.
-->

---

## Qué vamos a aprender

- A utilizar el **sensor de temperatura** para medir la temperatura ambiente en **grados Celsius** (°C).
- A iniciar un programa al **pulsar una tecla** del ordenador.
- A **unir textos** y valores de un sensor para construir una frase.
- A hacer que un personaje **diga** mensajes en un bocadillo.

---

## Componentes

<div class="dos-columnas">
<div>

- **Sensor de temperatura:** mide la temperatura del ambiente. Entrega un voltaje que depende de la temperatura.

</div>
<div>

![Sensor de temperatura en EchidnaBlack2](../assets/images/Lupa_Temperatura.png)

</div>
</div>

---

## Programación

Para leer la temperatura usamos el bloque `leer temperatura`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_temperatura.png" alt="Bloque leer temperatura">
</div>

- Convierte el voltaje del sensor directamente a **grados Celsius** (°C).
- Si marcas la **casilla** junto al bloque, verás la temperatura en el escenario.

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

Usa el personaje **Echidna** del escenario y construye este programa:

<div class="centro">

![w:1100 Bloques programación El echidna dice la temperatura](../assets/images/Ejemplo_temperatura.png)

</div>

Pulsa la tecla **t** para ejecutarlo.

<!--
El texto «Hola, ahora hace una temperatura de » lleva un espacio al
final; sin él, el número sale pegado a «de».
-->

---

## Cómo funciona

```
CUANDO se pulsa la tecla t:
    --> Se lee la temperatura del sensor.
    --> El echidna dice la frase durante 2 segundos.
```

`unir` junta el texto, el valor del sensor y «ºC». Como en un `unir` solo caben **dos partes**, usamos un `unir` dentro de otro para juntar las tres.

<!--
Errores típicos:
- El programa está en otro objeto o en el escenario: no habla nadie o
  no habla el echidna.
- Pulsan la tecla t con el foco fuera del escenario (por ejemplo, en
  otra ventana): no ocurre nada.
- El orden de las partes en los `unir` está cambiado y la frase sale
  desordenada.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Sin tantos decimales

El sensor da la temperatura con decimales (por ejemplo, **16.61**).

Usa el bloque `redondear` para que el echidna diga solo un **número entero**.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** `redondear` está en **Operadores**. Mete `leer temperatura` dentro de `redondear` y pon ese bloque en el `unir`, donde estaba `leer temperatura`.

</div>

---

## Mejóralo 2: Grados Fahrenheit

Haz que el echidna diga también la temperatura en **grados Fahrenheit** (°F).

Para calcularla, **multiplica** los grados Celsius por **1.8** y **súmale 32**.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** añade un segundo `decir` con otro `unir`. Para el cálculo usa los operadores `*` y `+`: mete `leer temperatura * 1.8` dentro de `+ 32`.

</div>

<!--
Ejemplo: 20 °C son 20 · 1.8 + 32 = 68 °F. El orden importa: primero se
multiplica y después se suma.
-->

---

## Mejóralo 3: Fondo de frío y calor

Añade **dos fondos** al escenario: uno de **frío** (un paisaje nevado) y otro de **calor** (una playa).

Haz que se muestre uno u otro según si la temperatura está **por debajo o por encima** de un valor.

Para probarlo, calienta el sensor tocándolo suavemente con el dedo.

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** dentro de un `por siempre`, usa un `si ... si no` con `leer temperatura > 25`: en una parte `cambiar fondo a` la playa y en la otra, el paisaje nevado.

</div>

<!--
El valor 25 es orientativo: conviene elegir uno un par de grados por
encima de la temperatura del aula, para que al calentar el sensor con el
dedo cambie el fondo. El sensor tarda unos segundos en calentarse y en
volver a enfriarse.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿En qué unidad da la temperatura el bloque `leer temperatura`?
2. ¿Por qué usamos un `unir` dentro de otro?
3. ¿Qué pasa si quitamos el espacio del final de «…temperatura de »?
4. ¿Qué cambiarías para que el programa empiece con la **bandera verde**?

<!--
Respuestas:
1. En grados Celsius (°C).
2. Porque en un `unir` solo caben dos partes y la frase tiene tres.
3. El número sale pegado a la palabra «de».
4. Cambiar `al presionar tecla t` por `al hacer clic en` la bandera
   verde.
-->

---

## He conseguido…

<div class="logros">

- Que el echidna diga la temperatura al pulsar la tecla t.
- Que diga la temperatura sin decimales (Mejóralo 1).
- Que diga también la temperatura en grados Fahrenheit (Mejóralo 2).
- Cambiar el fondo según haga frío o calor (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir la frase con `unir`.
- Conseguido: el programa funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con los fondos.
-->

---

## Qué he aprendido

<div class="logros">

- A utilizar el **sensor de temperatura** para medir la temperatura ambiente en **grados Celsius** (°C).
- A iniciar un programa al **pulsar una tecla** del ordenador.
- A **unir textos** y valores de un sensor para construir una frase.
- A hacer que un personaje **diga** mensajes en un bocadillo.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes hacer que un personaje diga lo que mide la placa.

Siguiente proyecto: **2.8 Termómetro de colores**

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
