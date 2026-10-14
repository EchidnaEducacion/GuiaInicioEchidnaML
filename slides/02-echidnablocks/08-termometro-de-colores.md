---
marp: true
theme: echidna
paginate: true
footer: "2.8 Termómetro de colores · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.8 Termómetro de colores

![Termómetro de colores](../assets/images/Mezclamos_colores.png)

<!--
Notas del docente: se presenta el LED RGB y la mezcla de colores con
valores de 0 a 255. También es el primer proyecto con un condicional
dentro de otro, para distinguir tres casos en lugar de dos.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a construir un **termómetro de colores**: el **LED RGB** de la placa cambiará de color según la temperatura.

- **Azul** si hace frío.
- **Verde** si la temperatura es agradable.
- **Rojo** si hace calor.

<!--
Pregunta antes de programar: ¿dónde habéis visto colores que indican
frío o calor? (grifos, mapas del tiempo, termostatos…).
-->

---

## Qué vamos a aprender

- A utilizar el **LED RGB** y a **mezclar** sus tres colores (rojo, verde y azul) para conseguir otros.
- A ajustar la **intensidad** de cada color con valores de 0 a 255.
- A usar el **sensor de temperatura** como entrada para controlar un actuador.
- A usar un condicional `si ... si no` **dentro de otro** para distinguir tres zonas de temperatura.

---

## Componentes

<div class="dos-columnas">
<div>

- **LED RGB:** tiene dentro tres LED, uno **rojo** (R), uno **verde** (G) y uno **azul** (B). Mezclándolos conseguimos más de 16 millones de colores.
- **Sensor de temperatura:** mide la temperatura en grados Celsius (°C).

</div>
<div>

![LED RGB en EchidnaBlack2](../assets/images/Lupa_LEDRGB.png)

</div>
</div>

<!--
R, G y B vienen del inglés: Red, Green y Blue.
-->

---

## Programación

Para controlar el LED RGB usamos el bloque `LED R G B`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_LED_RGB_naranja.png" alt="Bloque LED R G B con el naranja Echidna">
</div>

- Cada color va de **0** (apagado) a **255** (máxima intensidad).
- El **naranja Echidna**: mucho rojo (254), algo de verde (109) y casi nada de azul (4).

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** y calienta el sensor con el dedo.

</div>
<div class="centro">

![Bloques programación Termómetro de colores](../assets/images/Ejemplo_temperatura_RGB.png)

</div>
</div>

<!--
Para el azul solo damos valor al canal B, para el verde solo al G y
para el rojo solo al R.

Con el dedo el sensor sube unos pocos grados y tarda en enfriarse: para
ver el cambio de color en el aula puede hacer falta ajustar los valores
20 y 30 a la temperatura real.
-->

---

## Cómo funciona

```
SI la temperatura es menor de 20 °C (frío):
    --> El LED RGB se ilumina en azul.
SI NO:
    SI la temperatura es menor de 30 °C (agradable):
        --> El LED RGB se ilumina en verde.
    SI NO (30 °C o más, calor):
        --> El LED RGB se ilumina en rojo.
```

El segundo `si ... si no` solo se comprueba cuando la temperatura **no** es menor de 20 °C: con dos condicionales distinguimos **tres zonas**.

<!--
Errores típicos:
- Poner los dos `si` uno detrás de otro en lugar de uno dentro del otro:
  con menos de 20 °C se cumplen los dos y el LED parpadea entre azul y
  verde.
- Confundir el orden de R, G y B en el bloque.
- Usar `>` en lugar de `<` en alguna de las condiciones.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: El echidna avisa

Haz que el echidna del escenario diga **«¡Qué frío!»**, **«¡Qué bien se está!»** o **«¡Qué calor!»** según el color que se encienda.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** añade un bloque `decir` en cada parte del condicional, junto a su bloque `LED R G B`.

</div>

<!--
El programa tiene que estar en el objeto Echidna para que sea él quien
hable.
-->

---

## Mejóralo 2: Tu paleta de colores

Mezcla colores en el bloque `LED R G B` y descubre qué valores necesitas para conseguir **amarillo**, **morado**, **blanco** o tu color favorito.

Después, úsalos para añadir una zona **muy fría** (menos de 10 °C) y otra **muy caliente** (más de 35 °C).

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** el amarillo sale de mezclar rojo y verde; el morado, de rojo y azul; y el blanco, de los tres a `255`. Para cada zona nueva, añade otro `si ... si no` dentro.

</div>

<!--
Valores orientativos: amarillo 255, 255, 0; morado 128, 0, 128;
blanco 255, 255, 255.

Las zonas se comprueban de la más fría a la más caliente: < 10, < 20,
< 30 y < 35 (o > 35 al final).
-->

---

## Mejóralo 2: Ayuda

<div class="dos-columnas">
<div class="pista">

**Ayuda:** en la web podemos usar un selector de colores y copiar su código RGB. En la imagen hemos elegido el naranja Echidna, que tiene los valores R = `254`, G = `109` y B = `4`.

</div>
<div class="centro">

![Selector de colores con el naranja Echidna](../assets/images/Selector_colores_RGB.png)

</div>
</div>

---

## Mejóralo 3: Arcoíris

Crea una **variable** y usa un bucle `repetir` para que el LED RGB pase **poco a poco del azul al rojo**.

En cada vuelta, **suma 1 al rojo** y **resta 1 al azul**.

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** crea la variable `rojo` y fíjala a `0`. Dentro de `repetir 255`, pon `LED R G B` con R = `rojo`, G = `0` y B = `255 - rojo`, y después `cambiar rojo por 1`.

</div>

<div class="pendiente">

IMAGEN AYUDA TERMÓMETRO DE COLORES MEJORA 3

</div>

<!--
Conviene hacerlo en un programa aparte (o quitar el del termómetro):
si los dos funcionan a la vez, se pelean por el LED RGB.

Con un `esperar 0.01 segundos` dentro del bucle, el cambio se ve más
despacio.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué valores pondrías en `LED R G B` para encender el LED en **rojo**?
2. ¿De qué color se enciende con **22 °C**? ¿Y con **30 °C**?
3. ¿Por qué hay un `si ... si no` dentro de otro?
4. ¿Qué pasa si pones los tres colores a `255`? ¿Y a `0`?

<!--
Respuestas:
1. R = 255, G = 0, B = 0.
2. Con 22 °C, verde. Con 30 °C, rojo: 30 no es menor de 30.
3. Porque hay tres zonas y un `si ... si no` solo distingue dos.
4. Con los tres a 255, blanco; con los tres a 0, apagado.
-->

---

## He conseguido…

<div class="logros">

- Encender el LED RGB de un color según la temperatura.
- Que el echidna diga si hace frío o calor (Mejóralo 1).
- Crear colores nuevos y añadir más zonas (Mejóralo 2).
- Pasar poco a poco del azul al rojo (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el condicional dentro de
  otro.
- Conseguido: el programa funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con la variable y el bucle.
-->

---

## Qué he aprendido

<div class="logros">

- A utilizar el **LED RGB** y a **mezclar** sus tres colores (rojo, verde y azul) para conseguir otros.
- A ajustar la **intensidad** de cada color con valores de 0 a 255.
- A usar el **sensor de temperatura** como entrada para controlar un actuador.
- A usar un condicional `si ... si no` **dentro de otro** para distinguir tres zonas de temperatura.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes mezclar colores con el LED RGB.

Siguiente proyecto: **2.9 Vúmetro**

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
