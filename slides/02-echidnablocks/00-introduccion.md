---
marp: true
theme: echidna
paginate: true
footer: "2. Introducción a EchidnaBlocks · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2. Introducción a EchidnaBlocks

![EchidnaBlack2](../assets/images/EchidnaBlack_2_perspectiva.jpg)

<!--
Notas del docente: presentación para la primera sesión, antes de 2.1 Hola
Mundo. Conviene tener la placa conectada y EchidnaML abierto para enseñar
el entorno en directo.
-->

---

<!-- _class: seccion -->

## **1** Qué es EchidnaML

La placa y el programa que vamos a usar

---

## El sistema

<div class="dos-columnas">
<div>

**EchidnaBlack2** (hardware) y **EchidnaML** (software) forman un **sistema integrado** para aprender **programación**, **robótica** e **inteligencia artificial**.

Una **placa** con muchos componentes y un **entorno de programación** hecho a su medida.

</div>
<div class="centro">

![EchidnaML](../assets/images/pegataechidnaml.png)

</div>
</div>

---

## Las herramientas de EchidnaML

- **EchidnaBlocks:** el entorno de programación por **bloques**, basado en **Scratch**, con el que programamos la placa.
- **LearningML:** la herramienta para crear modelos de **machine learning** que después usamos en nuestros programas. La veremos en los proyectos con IA.

No necesitas saber programar, aunque te resultará más fácil si ya conoces **Scratch**.

---

<!-- _class: seccion -->

## **2** La placa EchidnaBlack2

Sus componentes y su función

---

## La placa

<div class="dos-columnas">
<div>

La placa tiene sus componentes **ya montados**: no hace falta cablear para empezar.

- **Sensores:** miden lo que pasa a su alrededor (entradas).
- **Actuadores:** hacen algo, como dar luz o sonar (salidas).

</div>
<div class="centro">

![EchidnaBlack2](../assets/images/EchidnaBlack_2_perspectiva.jpg)

</div>
</div>

---

## Componentes

<div class="centro">

![h:520px Componentes de EchidnaBlack2](../assets/images/Componentes.png)

</div>

<!--
Los colores del esquema agrupan los componentes por su función: sensores
(verde), actuadores (naranja), alimentación (rojo), conectividad (azul) y
el selector Sensores/MkMk (amarillo). Junto a cada nombre aparece el pin
al que está conectado (por ejemplo, LDR en A3).
-->

---

## Función

<div class="centro">

![h:500px Esquema de la placa según la función de sus componentes](../assets/images/Esquema_microcontrolador.png)

</div>

<!--
Los componentes se clasifican en cuatro grupos según su función:
- Entradas (sensores): capturan información del entorno (temperatura, luz,
  sonido, gravedad…) y la traducen en datos.
- Microcontrolador (el cerebro): recibe los datos de las entradas, ejecuta
  las instrucciones del programa y envía las órdenes a las salidas.
- Salidas (actuadores): producen una acción física, sobre todo luz (LED) y
  sonido (zumbador).
- Conectividad: comunican la placa con el ordenador y permiten conectar
  sensores y actuadores externos.
-->

---

<!-- _class: seccion -->

## **3** EchidnaBlocks

El entorno con el que programamos la placa

---

## El entorno

<div class="centro">

![h:500px Entorno de programación EchidnaBlocks](../assets/images/EchidnaBlocks-_partes.png)

</div>

<!--
Señala las partes que más se usan: la paleta de bloques (con los bloques
Echidna y los de LearningML), la zona de programación, el escenario con el
echidna y, arriba, el tipo de placa conectada y el puerto.
-->

---

## Cómo se comunica con la placa

Por el **puerto serie** (cable USB), la placa **envía** sus **sensores** y el programa le **devuelve** sus **actuadores**.

<div class="centro">

![h:380px Comunicación entre EchidnaBlocks y la placa](../assets/images/StandarFirmata-EchidnaBlocks.png)

</div>

<!--
Por eso la placa tiene que estar conectada mientras el programa funciona:
el programa se ejecuta en el ordenador, no en la placa. La placa trae de
fábrica el programa StandardFirmata, que es el que se encarga de esa
comunicación.
-->

---

## Puesta en marcha

**Conecta la placa antes de abrir EchidnaML**: así la detecta automáticamente y muestra el mensaje **«¡Placa conectada!»**.

<div class="centro">

![Puesta en marcha](../assets/images/Puesta_en_marcha.png)

</div>

<!--
EchidnaML detecta también la versión de la placa (EchidnaBlack o
EchidnaBlack2). Si no la detecta: cerrar EchidnaML, revisar el cable USB y
volver a abrirlo con la placa ya conectada.
-->

---

## Los ejemplos

<div class="dos-columnas">
<div>

Los programas de todos los proyectos están en el menú **Archivo → Ejemplos**.

Ábrelos para **probarlos**, **estudiarlos** y **modificarlos**.

</div>
<div class="centro">

![Menú Archivo de EchidnaBlocks](../assets/images/menuejemplos.png)

</div>
</div>

---

<!-- _class: seccion -->

## **4** Los proyectos

Qué vamos a hacer y cómo

---

## Proyectos con EchidnaBlocks

<div class="dos-columnas arriba">
<div>

1. Hola Mundo
2. Semáforo
3. Interruptor de luz
4. Timbre
5. Interruptor crepuscular
6. Piano de frutas

</div>
<div>

7. El echidna dice la temperatura
8. Termómetro de colores
9. Vúmetro
10. Telesketch
11. Movemos el echidna

</div>
</div>

Cada proyecto presenta un **componente nuevo** y va creciendo en complejidad. Después vienen los **proyectos con IA**.

---

## Cómo es cada proyecto

1. **Qué vamos a hacer:** el reto, qué vamos a aprender y qué vamos a usar.
2. **Programamos:** el programa de bloques y cómo funciona.
3. **Mejóralo:** tres retos, de menos a más difícil, con una pista o una ayuda.
4. **Evaluación:** preguntas para comprobar lo que sabes y lo que has conseguido.

---

<!-- _class: seccion -->

## **5** Evaluación

Comprueba lo que has aprendido

---

## Comprueba lo que sabes

1. ¿Son **sensores** o **actuadores**: el zumbador, el micrófono, el LED RGB y el acelerómetro?
2. ¿Qué hay que hacer **antes** de abrir EchidnaML?
3. ¿Cómo se comunican EchidnaBlocks y la placa?
4. ¿Dónde están los programas de los proyectos?

<!--
Respuestas:
1. Actuadores: el zumbador y el LED RGB. Sensores: el micrófono y el
   acelerómetro.
2. Conectar la placa al ordenador con el cable USB.
3. Por el puerto serie, a través del cable USB: la placa envía los
   sensores y el programa le devuelve los actuadores.
4. En el menú Archivo → Ejemplos de EchidnaBlocks.
-->

---

## Qué he aprendido

<div class="logros">

- Qué son **EchidnaML**, **EchidnaBlocks** y **LearningML**.
- A distinguir los **sensores** y los **actuadores** de la placa.
- Cómo se **comunican** la placa y EchidnaBlocks.
- A poner en marcha la placa y abrir los **ejemplos**.

</div>

<!--
El alumnado marca lo que cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡A programar!

Ya conoces la placa y EchidnaBlocks.

Primer proyecto: **2.1 Hola Mundo**

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
