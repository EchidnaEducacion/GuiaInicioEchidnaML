---
marp: true
theme: echidna
paginate: true
footer: "2.5 Interruptor crepuscular · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.5 Interruptor crepuscular

![Interruptor crepuscular](../assets/images/Interruptor_crepuscular.png)

<!--
Notas del docente: primer proyecto con un sensor analógico. Hasta ahora
las entradas (pulsadores) solo daban verdadero o falso; el sensor de luz
da un número, y el programa decide comparándolo con un umbral.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a programar una **luz automática**, como las farolas de la calle:

- el **LED verde** se **enciende** cuando hay poca luz (de noche),
- y se **apaga** cuando hay suficiente luz (de día).

<!--
Pregunta antes de programar: ¿cómo sabe una farola cuándo encenderse?
¿Qué otros sistemas automáticos conocen? (puertas, grifos, luces de
pasillo…).
-->

---

## Qué vamos a aprender

- A programar un **sistema automático** que reacciona al entorno.
- A usar el **sensor de luz (LDR)** para medir la iluminación.
- A usar un **operador de comparación** (`<`) para que el condicional `si ... si no` decida a partir de la lectura de un sensor.
- A trabajar con **umbrales numéricos** para definir estados (día y noche).

---

## Componentes

<div class="dos-columnas">
<div>

- **Sensor de luz (LDR):** mide la luz que recibe. Cuanto más oscuro, menor es el valor.
- **LED verde:** nuestra luz automática.

</div>
<div>

![Sensor de luz (LDR) en EchidnaBlack2](../assets/images/Lupa_LDR.png)

</div>
</div>

---

## Programación

Para leer el sensor de luz usamos el bloque `leer sensor luz`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_sensor_luz.png" alt="Bloque leer sensor luz">
</div>

- Da valores entre **0** (no hay luz) y **1023** (mucha luz).
- Si marcas la **casilla** junto al bloque, verás el valor en el escenario.

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** para ejecutarlo y tapa el sensor con la mano.

</div>
<div class="centro">

![Bloques programación interruptor crepuscular](../assets/images/Ejemplo_sensor_luz.png)

</div>
</div>

---

## Cómo funciona

`por siempre` revisa el sensor de luz una y otra vez:

```
SI el sensor de luz da un valor menor que 200:
    --> Se enciende el LED verde.

SI NO (valor mayor o igual que 200):
    --> Se apaga el LED verde.
```

El valor **200** es el **umbral**: marca cuándo es de noche y cuándo de día.

<!--
Errores típicos:
- El umbral no sirve para la luz del aula: el LED está siempre encendido
  o siempre apagado. Se arregla en el reto 1.
- El operador está al revés (`>` en lugar de `<`): el LED se enciende de
  día y se apaga de noche.
- Un LED distinto en el bloque de encender y en el de apagar.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Calibra tu aula

Averigua qué valor lee el sensor de luz en tu mesa y **ajusta el umbral** para que la luz se encienda **solo cuando tapes el sensor** con la mano.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** marca la casilla junto a `leer sensor luz` y apunta el valor con el sensor destapado y tapado. Pon un umbral entre los dos.

</div>

<!--
El valor cambia según la hora, las ventanas y las luces del aula: cada
grupo puede necesitar un umbral distinto.
-->

---

## Mejóralo 2: Fondo de día y noche

Añade **dos fondos** al escenario: uno soleado y otro nocturno.

Haz que el fondo cambie en la pantalla **al mismo tiempo** que se enciende o se apaga el LED de la placa.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** añade el bloque `cambiar fondo a` en cada parte del `si ... si no`: el fondo nocturno donde se enciende el LED y el soleado donde se apaga.

</div>

---

## Mejóralo 3: Luz blanca

Sustituye el LED verde por el **LED RGB** para que ilumine más:

- con **oscuridad**, se enciende en color **blanco**;
- con **mucha luz**, se apaga.

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** con el bloque `LED R G B`, el blanco se consigue poniendo los tres colores a `255`, y para apagarlo los ponemos a `0`.

</div>

<div class="centro" style="display: flex; justify-content: center; gap: 32px;">
<img src="../assets/images/Bloque_LED_RGB_blanco.png" alt="Bloque LED R G B a 255 255 255" style="zoom: 1.1;">
<img src="../assets/images/Bloque_LED_RGB_apagado.png" alt="Bloque LED R G B a 0 0 0" style="zoom: 1.1;">
</div>

<!--
Es la primera vez que se usa el LED RGB; se presenta en 2.8 Termómetro
de colores. Mezclando rojo, verde y azul a tope sale el blanco.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué valor da el sensor con **mucha luz**? ¿Y a **oscuras**?
2. ¿Qué pasa si subimos el umbral a `800`?
3. ¿Qué ocurre si cambiamos `<` por `>`?
4. ¿Qué es un **umbral**?

<!--
Respuestas:
1. Con mucha luz, valores cercanos a 1023; a oscuras, cercanos a 0.
2. El LED se enciende con muy poca oscuridad: en un aula normal puede
   estar casi siempre encendido.
3. Funciona al revés: el LED se enciende de día y se apaga de noche.
4. El valor que marca el cambio de un estado a otro; aquí, entre día y
   noche.
-->

---

## He conseguido…

<div class="logros">

- Encender el LED automáticamente cuando hay poca luz.
- Ajustar el umbral a la luz de mi aula (Mejóralo 1).
- Cambiar el fondo del escenario entre día y noche (Mejóralo 2).
- Encender el LED RGB en blanco (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el programa o no entiende
  para qué sirve el umbral.
- Conseguido: el programa funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con el LED RGB.
-->

---

## Qué he aprendido

<div class="logros">

- A programar un **sistema automático** que reacciona al entorno.
- A usar el **sensor de luz (LDR)** para medir la iluminación.
- A usar un **operador de comparación** (`<`) para que el condicional `si ... si no` decida a partir de la lectura de un sensor.
- A trabajar con **umbrales numéricos** para definir estados (día y noche).

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes hacer que la placa reaccione a la luz.

Siguiente proyecto: **2.6 Piano de frutas**

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
