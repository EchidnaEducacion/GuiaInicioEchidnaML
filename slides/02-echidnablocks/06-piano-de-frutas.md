---
marp: true
theme: echidna
paginate: true
footer: "2.6 Piano de frutas · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.6 Piano de frutas

![Piano de frutas](../assets/images/MkMk.png)

<!--
Notas del docente: primer proyecto con el modo Makey Makey (MkMk). Los
objetos cotidianos se convierten en entradas: el circuito se cierra a
través del cuerpo del alumnado. También es el primero en el que suena
música desde el ordenador y no desde la placa.

Material: cables de cocodrilo, una pulsera o cable para el conector
común y objetos conductores (fruta, plastilina, papel de aluminio).
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a convertir la entrada **MkMk A0** de la placa en una **tecla de piano táctil**.

Cada vez que toques la entrada (o una fruta conectada a ella), el ordenador tocará una **nota musical**.

<!--
Pregunta antes de programar: ¿qué objetos creéis que dejan pasar la
corriente? Apuntad las hipótesis y comprobadlas al final con el piano.
-->

---

## Qué vamos a aprender

- A detectar la conductividad eléctrica de objetos cotidianos usando el **modo Makey Makey (MkMk)**.
- A conectar cables de cocodrilo en los conectores externos de la placa.
- A entender cómo funciona un **circuito cerrado** a través de nuestro propio cuerpo.
- A reproducir notas musicales y sonidos desde el software.

---

## Componentes

<div class="dos-columnas">
<div>

- **Entrada MkMk A0:** la tecla, conectada a la fruta.
- **Conector común MkMk I/O:** la pulsera, que cierra el circuito con tu cuerpo.
- **Cables de cocodrilo.**

**¡Atención!** Pon el selector en **MkMk**.

</div>
<div>

![Conexión en modo MkMk](../assets/images/mkmk_conexion.png)

</div>
</div>

<!--
Al tocar la fruta, una corriente muy pequeña pasa por el cuerpo desde la
pulsera (MkMk I/O) hasta la entrada A0: el circuito se cierra y la placa
lo detecta. Es inofensiva.

Si no funciona: comprobar el selector y el LED testigo, que la pulsera
toque la piel y que las pinzas de cocodrilo estén bien sujetas.

El selector va hacia la derecha; al ponerlo en MkMk se enciende el LED
testigo de la parte inferior. El conector común da 5V.
-->

---

## Programación

Para leer una entrada MkMk usamos el bloque `leer MK MK`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_MkMk.png" alt="Bloque leer MK MK">
</div>

- Puedes elegir la entrada: **A0**, **A1**, **A2**, **A3**, **A6**, **A7**, **D2** o **D3**.
- Da **verdadero** cuando el circuito se cierra y **falso** cuando está abierto.

<!--
La placa considera el circuito cerrado cuando la lectura de la entrada
supera 350 en una escala de 0 a 1023.
-->

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde**, ponte la pulsera y toca la fruta.

</div>
<div class="centro">

![Bloques programación MkMk](../assets/images/Ejemplo_MkMk_piano.png)

</div>
</div>

<!--
`fijar instrumento a` elige el sonido (aquí, el piano). Animar a probar
otros instrumentos del desplegable.
-->

---

## Cómo funciona

`por siempre` revisa la entrada MkMk A0 una y otra vez:

```
SI la entrada MkMk A0 detecta contacto:
    --> Suena la nota 60 (Do central) durante 0.25 tiempos.
```

Si no hay contacto, no ocurre nada y el programa vuelve a comprobar la entrada.

<!--
Con el tempo por defecto (60 pulsos por minuto), 0.25 tiempos es un
cuarto de segundo.

Errores típicos:
- El selector no está en MkMk: no detecta nada.
- No llevan la pulsera o no toca la piel: el circuito no se cierra.
- Si se mantiene el dedo sobre la fruta, la nota se repite sin parar:
  es lo esperado, porque `por siempre` vuelve a comprobar la entrada.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Animación en pantalla

Añade un **objeto** en EchidnaML (un instrumento o una nota musical) que **cambie de disfraz**, baile o salte en la pantalla cada vez que suene la nota.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** añade el bloque `siguiente disfraz` dentro del `si`, justo antes de `tocar nota`. Elige un objeto que tenga varios disfraces.

</div>

---

## Mejóralo 2: Luz y sonido

Haz que el **LED RGB** se ilumine de un **color distinto** cada vez que toques una tecla de tu piano MkMk.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** añade el bloque `LED R G B` dentro del `si` y pon en cada color un `número aleatorio entre 0 y 255`.

</div>

<!--
Es la primera vez que se usa el LED RGB con valores; se presenta en
2.8 Termómetro de colores. Cada color va de 0 (apagado) a 255 (máxima
intensidad).
-->

---

## Mejóralo 3: Escala musical

Usa los otros conectores (**A1**, **A2** y **A3**) con más cables y frutas para programar **notas diferentes** y crea un **mini teclado** completo:

- **Do** = 60, **Re** = 62, **Mi** = 64, **Fa** = 65.

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** duplica el programa tres veces y, en cada copia, adapta la entrada de `leer MK MK` (**A1**, **A2** y **A3**) y la nota de `tocar nota` (**62**, **64** y **65**).

</div>

<!--
La pulsera sigue siendo una sola: el conector común MkMk I/O sirve para
todas las teclas.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Por qué hay que llevar la **pulsera** conectada a MkMk I/O?
2. ¿Qué objetos funcionan como tecla? ¿Cuáles no?
3. ¿Qué pasa si mantienes el dedo sobre la fruta?
4. ¿Qué ocurre si cambiamos la nota `60` por `72`?

<!--
Respuestas:
1. Para cerrar el circuito: la corriente va de la pulsera, por el
   cuerpo, hasta la fruta y la entrada A0.
2. Funcionan los conductores (fruta, plastilina, papel de aluminio,
   agua); no funcionan los aislantes (plástico, madera seca, papel).
3. La nota se repite mientras dure el contacto.
4. Suena el Do una octava más aguda (12 notas por encima).
-->

---

## He conseguido…

<div class="logros">

- Hacer sonar una nota al tocar una fruta.
- Animar un objeto en la pantalla al tocar la nota (Mejóralo 1).
- Encender el LED RGB de colores distintos (Mejóralo 2).
- Crear un mini teclado de cuatro notas (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para montar el circuito o para construir
  el programa.
- Conseguido: el piano funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con cuatro teclas.
-->

---

## Qué he aprendido

<div class="logros">

- A detectar la conductividad eléctrica de objetos cotidianos usando el **modo Makey Makey (MkMk)**.
- A conectar cables de cocodrilo en los conectores externos de la placa.
- A entender cómo funciona un **circuito cerrado** a través de nuestro propio cuerpo.
- A reproducir notas musicales y sonidos desde el software.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes convertir objetos cotidianos en teclas.

Siguiente proyecto: **2.7 El echidna dice la temperatura**

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
