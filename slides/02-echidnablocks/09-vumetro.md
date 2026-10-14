---
marp: true
theme: echidna
paginate: true
footer: "2.9 Vúmetro · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.9 Vúmetro

![Vúmetro](../assets/images/Vumetro.png)

<!--
Notas del docente: se presenta el micrófono, un sensor cuya lectura
cambia muy deprisa. Repite la estructura del Termómetro de colores (un
`si ... si no` dentro de otro para tres niveles), ahora con los tres LED.
Es útil en el aula como semáforo de ruido.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a construir un **vúmetro** o **semáforo de ruido**, que muestra con los LED cuánto ruido hay a nuestro alrededor:

- **Silencio:** solo el **LED verde**.
- **Ruido moderado:** el **verde** y el **naranja**.
- **Mucho ruido:** los **tres LED**.

<!--
Pregunta antes de programar: ¿dónde habéis visto un vúmetro? (equipos
de música, aplicaciones de grabación, karaokes…).
-->

---

## Qué vamos a aprender

- A utilizar el **micrófono** para medir la **intensidad del sonido**.
- A usar un condicional `si ... si no` **dentro de otro** para distinguir tres niveles.
- A trabajar con **umbrales numéricos** para definir estados (silencio, ruido moderado y mucho ruido).
- A entender por qué algunas señales, como el sonido, **cambian constantemente**.

---

## Componentes

<div class="dos-columnas">
<div>

- **Micrófono:** convierte el sonido en una señal eléctrica. Da valores entre 0 y 1023: bajos con silencio y más altos cuanto más intenso es el sonido.
- **LED verde, naranja y rojo:** indican el nivel de ruido.

</div>
<div>

![Micrófono en EchidnaBlack2](../assets/images/Lupa_Microfono.png)

</div>
</div>

---

## Programación

Para leer el micrófono usamos el bloque `leer micrófono`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_microfono.png" alt="Bloque leer micrófono">
</div>

- Da valores entre **0** y **1023**.
- Si marcas la **casilla** junto al bloque, verás en el escenario el valor que mide en cada momento.

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** y prueba en silencio, hablando y dando una palmada.

</div>
<div class="centro">

![Bloques programación Vúmetro](../assets/images/Ejemplo_vumetro.png)

</div>
</div>

<!--
Cada parte del condicional enciende o apaga los tres LED: si falta
alguno, se queda encendido del nivel anterior.
-->

---

## Cómo funciona

```
SI el micrófono da menos de 20 (silencio):
    --> Verde encendido; naranja y rojo apagados.
SI NO:
    SI da menos de 50 (ruido moderado):
        --> Verde y naranja encendidos; rojo apagado.
    SI NO (50 o más, mucho ruido):
        --> Los tres LED encendidos.
```

Los LED pueden **parpadear** aunque el ruido sea constante: el sonido cambia muy deprisa y cada lectura da un valor distinto.

<!--
El micrófono capta las vibraciones de la onda sonora: cada lectura cae
en un punto distinto de la onda. El parpadeo se soluciona en el
Mejóralo 1 con la media de varias lecturas.

Errores típicos:
- Poner los dos `si` uno detrás de otro en lugar de uno dentro del otro.
- Olvidar apagar algún LED en una de las partes.
- Umbrales que no sirven para el aula: se ajustan en el Mejóralo 2.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos para mejorar el vúmetro

---

## Mejóralo 1: Una lectura más estable

Para que los LED no parpadeen, en lugar de usar cada lectura del micrófono calcula la **media** de varias (por ejemplo, de **10**).

Usa esa media en los condicionales.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** necesitas una variable que vaya sumando las lecturas (`suma`) y otra que las cuente (`numeroDatos`). La media es `suma / numeroDatos`.

</div>

---

## Mejóralo 1: Ayuda

<div class="dos-columnas">
<div class="pista">

**Ayuda:** puedes encontrar la programación en **Archivo → Ejemplos → Vumetro_media_sonido**.

</div>
<div class="centro">

![height:480px Programa del vúmetro con media](../assets/images/Ejemplo_Vumetro-media.png)

</div>
</div>

<!--
Cada 10 lecturas, `mediaSonido` guarda `suma / numeroDatos` y `suma` y
`numeroDatos` vuelven a 0. El programa del vúmetro compara `mediaSonido`
en lugar de `leer micrófono`.

Es el reto más difícil de los tres, aunque va primero porque soluciona
el parpadeo. Conviene revisar el ejemplo con el grupo antes de que lo
abran.
-->

---

## Mejóralo 2: Calibra tu aula

Observa qué valores mide el micrófono con **silencio**, **hablando en voz baja** y **dando una palmada**.

Ajusta los umbrales (**20** y **50**) para que el vúmetro funcione bien en tu clase.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** marca la casilla junto a `leer micrófono` y apunta los valores en cada caso. Pon cada umbral entre dos de ellos.

</div>

<!--
Como el valor cambia muy deprisa, es más fácil calibrar después de
resolver el reto 1, mostrando la media en el escenario.
-->

---

## Mejóralo 3: Vúmetro virtual en pantalla

Crea un **objeto** en EchidnaML con **cuatro disfraces**: sin barras, una, dos y tres barras.

Haz que cambie de disfraz **al mismo tiempo** que se encienden los LED de la placa.

---

## Mejóralo 3: Pista

<div class="pista">

**Pista:** añade `cambiar disfraz a` en cada parte del condicional: una barra con silencio, dos con ruido moderado y tres con mucho ruido. El disfraz sin barras se pone al empezar, tras la bandera verde.

</div>

<!--
Los disfraces se dibujan en el editor de disfraces con rectángulos de
colores (verde, naranja y rojo).
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué LED se encienden si el micrófono da **35**? ¿Y **50**?
2. ¿Por qué los LED **parpadean** aunque el ruido sea constante?
3. ¿Cómo se calcula la **media** de 10 lecturas?
4. ¿Qué pasa si subimos los umbrales a `200` y `500`?

<!--
Respuestas:
1. Con 35, verde y naranja. Con 50, los tres: 50 no es menor de 50.
2. Porque el sonido es una onda que cambia muy deprisa y cada lectura
   cae en un punto distinto.
3. Sumando las 10 lecturas y dividiendo el resultado entre 10.
4. Hace falta mucho más ruido para que se encienda el naranja o el
   rojo; con ruido normal solo estará el verde.
-->

---

## He conseguido…

<div class="logros">

- Que los LED muestren el nivel de ruido.
- Que los LED no parpadeen usando la media (Mejóralo 1).
- Ajustar los umbrales al ruido de mi aula (Mejóralo 2).
- Mostrar el vúmetro también en la pantalla (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el condicional dentro de
  otro.
- Conseguido: el programa funciona y resuelve los retos 2 y 3.
- Avanzado: además, resuelve el reto 1 con la media.
-->

---

## Qué he aprendido

<div class="logros">

- A utilizar el **micrófono** para medir la **intensidad del sonido**.
- A usar un condicional `si ... si no` **dentro de otro** para distinguir tres niveles.
- A trabajar con **umbrales numéricos** para definir estados (silencio, ruido moderado y mucho ruido).
- A entender por qué algunas señales, como el sonido, **cambian constantemente**.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes medir el ruido con la placa.

Siguiente proyecto: **2.10 Telesketch**

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
