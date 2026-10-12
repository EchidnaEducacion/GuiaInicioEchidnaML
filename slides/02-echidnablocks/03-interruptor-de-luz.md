---
marp: true
theme: echidna
paginate: true
footer: "2.3 Interruptor de luz · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.3 Interruptor de luz

![Interruptor de luz](../assets/images/Pulsadores.png)

<!--
Notas del docente: primer proyecto con entradas. Hasta ahora el programa
solo daba órdenes (encender y apagar LED); ahora también lee lo que hace
el usuario con los pulsadores y decide qué hacer con condicionales.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a programar un **interruptor de luz** con los dos pulsadores de la placa:

- Al pulsar el **pulsador derecho (SR)**, el **LED rojo** se enciende.
- Al pulsar el **pulsador izquierdo (SL)**, el **LED rojo** se apaga.

<!--
Pregunta antes de programar: ¿qué interruptores de este tipo conocen?
(timbres, ascensores, luces de la escalera…). ¿Qué pasa con la luz cuando
soltamos el botón?
-->

---

## Qué vamos a aprender

- A leer **entradas digitales**: saber si un botón está pulsado o no.
- A diferenciar una **entrada** (SR y SL: detectan la orden) de una **salida** (LED rojo: produce la respuesta).
- A tomar decisiones con el bloque condicional **`si ... si no`**.
- A usar **condicionales anidados**: un `si` dentro de otro.
- A controlar un actuador (el LED) con eventos físicos (pulsaciones).

---

## Componentes

<div class="dos-columnas">
<div>

- **Pulsador SR** (derecho): enciende el LED.
- **Pulsador SL** (izquierdo): apaga el LED.
- **LED rojo:** cambia de estado según el botón pulsado.

</div>
<div>

![Pulsadores en EchidnaBlack2](../assets/images/Lupa_Pulsadores.png)

</div>
</div>

---

## Programación

Para leer el estado de los pulsadores usamos el bloque `¿botón SL pulsado?`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_pulsador.png" alt="Bloque ¿botón pulsado?">
</div>

En el bloque elegimos el pulsador **SL** o **SR**. Devuelve:

- **verdadero** (1) si está pulsado,
- **falso** (0) si no lo está.

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** para ejecutarlo y prueba los dos pulsadores.

</div>
<div class="centro">

![Bloques programación pulsadores](../assets/images/Ejemplo_encender_apagar_led_pulsadores.png)

</div>
</div>

---

## Cómo funciona

`por siempre` revisa los pulsadores una y otra vez:

```
SI el pulsador derecho (SR) está pulsado:
    --> Enciende el LED rojo.

SI NO:
    SI el pulsador izquierdo (SL) está pulsado:
        --> Apaga el LED rojo.
```

Si no pulsamos ninguno, no hace nada: el LED se queda como estaba.

<!--
Errores típicos:
- SR y SL cambiados en los bloques `¿botón pulsado?`.
- El segundo `si` fuera del hueco `si no`: funciona casi igual, pero ya
  no es un condicional anidado.
- Falta el `por siempre`: el programa mira los pulsadores una sola vez,
  al pulsar la bandera, y luego no responde.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Luz cruzada

Añade el **LED verde** para que funcione al revés que el rojo:

- Al pulsar **SR**: LED rojo encendido y LED verde apagado.
- Al pulsar **SL**: LED rojo apagado y LED verde encendido.

<!--
Es un biestable: cada pulsador deja la placa en uno de dos estados
estables, y se mantiene al soltar.
-->

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** en cada condición añade un segundo bloque `encender LED` para el verde: en la de SR, que lo apague; en la de SL, que lo encienda.

</div>

---

## Mejóralo 2: LED virtual en pantalla

Crea un **objeto** en EchidnaML que cambie de **disfraz** (encendido y apagado) al mismo tiempo que cambia el LED de la placa.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** como en Hola Mundo, usa **mensajes**: envía uno al pulsar SR y otro al pulsar SL, y en el objeto cambia de disfraz al recibirlos.

</div>

---

## Mejóralo 3: Pulsador con memoria

Programa **un solo pulsador** (por ejemplo, **SL**) para que funcione como el interruptor de la luz de tu habitación:

- la primera vez que lo pulsas, enciende el LED;
- al volverlo a pulsar, lo apaga.

<!--
Es un conmutador. Necesita recordar el estado del LED, así que es el
primer proyecto con una variable.
-->

---

## Mejóralo 3: Ayuda

<div class="dos-columnas">
<div>

<div class="pista">

**Ayuda:** la variable **`estadoLED`** recuerda si el LED está apagado (`0`) o encendido (`1`). Cada pulsación de SL lo cambia al estado contrario.

</div>

</div>
<div class="centro">

![Bloques programación pulsador con memoria](../assets/images/Ejemplo_pulsador_memoria.png)

</div>
</div>

<!--
`esperar hasta que no ¿botón SL pulsado?` espera a que se suelte el
pulsador. Sin él, mientras se mantiene pulsado SL el LED se
enciende y se apaga muchas veces seguidas y queda en un estado al azar.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. En este proyecto, ¿cuál es la **entrada** y cuál la **salida**?
2. ¿Qué devuelve `¿botón SR pulsado?` si no pulsamos el botón?
3. ¿Qué ocurre si pulsamos **SR y SL a la vez**?
4. ¿Qué le pasa al LED cuando **soltamos** el pulsador?

<!--
Respuestas:
1. Entradas: los pulsadores SR y SL. Salida: el LED rojo.
2. Falso (0).
3. Se enciende el LED: el programa comprueba primero SR, y SL solo se
   mira si SR no está pulsado.
4. Nada: se queda como estaba, porque el programa solo cambia el LED
   cuando hay una pulsación.
-->

---

## He conseguido…

<div class="logros">

- Encender y apagar el LED con los pulsadores.
- Hacer que el LED verde funcione al revés que el rojo (Mejóralo 1).
- Simular el LED en la pantalla con mensajes (Mejóralo 2).
- Encender y apagar el LED con un solo pulsador (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el programa o confunde los
  pulsadores o la estructura `si ... si no`.
- Conseguido: el programa funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 y explica para qué sirven la
  variable y el `esperar hasta que`.
-->

---

## Qué he aprendido

<div class="logros">

- A leer **entradas digitales**: saber si un botón está pulsado o no.
- A diferenciar una **entrada** (SR y SL: detectan la orden) de una **salida** (LED rojo: produce la respuesta).
- A tomar decisiones con el bloque condicional **`si ... si no`**.
- A usar **condicionales anidados**: un `si` dentro de otro.
- A controlar un actuador (el LED) con eventos físicos (pulsaciones).

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes leer pulsadores y tomar decisiones con condicionales.

Siguiente proyecto: **2.4 Timbre**

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
