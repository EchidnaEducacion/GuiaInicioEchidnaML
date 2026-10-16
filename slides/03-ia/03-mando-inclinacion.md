---
marp: true
theme: echidna
paginate: true
footer: "3.3 Mando de inclinación · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 3.3 Mando de inclinación

![Modelo de números](../assets/images/MODELO_Numeros.png)

<!--
Notas del docente: tercer proyecto con IA, ahora con un modelo de
números. Los datos salen de un sensor de la placa (el acelerómetro), que ya
se usó en 2.11 Movemos el echidna: allí la dirección se decidía con
umbrales fijos y aquí la aprende el modelo.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a convertir la placa EchidnaBlack2 en un **mando**: al inclinarla hacia la **derecha** o hacia la **izquierda** y pulsar **SL**, el echidna se desplazará por el escenario en esa dirección.

Para saber hacia dónde inclinamos la placa, crearemos con **LearningML** un **modelo de números** con los valores del **acelerómetro** en cada posición.

---

## Qué vamos a aprender

- A crear un **modelo de machine learning** que clasifica **números**.
- A recoger **datos** de un sensor para entrenar un modelo.
- A introducir ejemplos con **varias columnas** (en nuestro caso, los ejes X e Y del acelerómetro).
- A usar el modelo en EchidnaBlocks para controlar un personaje.

---

## Componentes

<div class="dos-columnas">
<div>

- **Acelerómetro:** mide la inclinación de la placa.
- **Pulsador SL:** al pulsarlo, el echidna se mueve.

</div>
<div>

![Acelerómetro en EchidnaBlack2](../assets/images/Lupa_Acelerometro.png)

</div>
</div>

---

## Programación

Para usar el modelo en nuestro programa usamos el bloque `clasificar números`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_clasificar_numeros.png" alt="Bloque clasificar números">
</div>

Le damos un **conjunto de números separados por comas** y nos devuelve la **clase** más probable; en nuestro caso, **Derecha** o **Izquierda**.

---

<!-- _class: seccion -->

## **2** Entrenamos el modelo

Entrenar, aprender y probar en LearningML

---

## Entrenar: clases y ejemplos

<div class="dos-columnas">
<div>

Elegimos un modelo de **números** con **2 columnas**: eje **X** y eje **Y**.

Creamos las clases **Derecha** e **Izquierda**. Cada ejemplo es una pareja `X,Y`.

Inclina la placa y anota los valores: hacia la izquierda, X **negativo**; hacia la derecha, **positivo**.

</div>
<div class="centro">

![Clases Izquierda y Derecha](../assets/images/Clases_numeros.png)

</div>
</div>

<!--
Los valores se ven en el escenario marcando la casilla junto al bloque
`leer acelerómetro`. El eje X va de -1 a 1. Conviene recoger inclinaciones
suaves y fuertes en cada clase. La coma separa las columnas; los decimales
se escriben con punto (0.3).
-->

---

## Aprender

<div class="dos-columnas" style="grid-template-columns: 3fr 2fr;">
<div>

Pulsamos **Aprender a reconocer números**.

El algoritmo analiza los ejemplos y construye un **modelo** capaz de clasificar números nuevos.

</div>
<div class="centro">

![Aprender a reconocer números](../assets/images/Aprender_numeros.png)

</div>
</div>

---

## Probar

<div class="dos-columnas">
<div>

Escribimos parejas de números **nuevas** y vemos su clase y su **confianza**.

`0.3,0.05` sale **Derecha** con un 82,08 %.

Si se equivoca, volvemos a **Entrenar**: más ejemplos o revisamos los que hay.

</div>
<div class="centro">

![Probar el modelo de números](../assets/images/Probar_numeros.png)

</div>
</div>

---

<!-- _class: seccion -->

## **3** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa: leer el acelerómetro

<div class="dos-columnas">
<div>

El primer script guarda los ejes X e Y en `acelX` y `acelY`.

También guarda la confianza y la clase en `Confianza` y `Sentido`, para verlas en el escenario mientras inclinamos la placa.

</div>
<div class="centro">

![Lectura del acelerómetro](../assets/images/LMLModeloNumeros-ValoresAcel.png)

</div>
</div>

---

## El programa: mover el echidna

<div class="centro">

![h:480px Bloques programación Mando de inclinación](../assets/images/NumerosEchidnaBlocks.png)

</div>

---

## Cómo funciona

Al pulsar **SL**, `unir` junta `acelX` y `acelY` con una coma y el modelo los clasifica:

```
SI la confianza es mayor de 70:
    SI la clase es "Derecha":
        --> El echidna avanza 20 pasos a la derecha.
    SI la clase es "Izquierda":
        --> El echidna avanza 20 pasos a la izquierda.
--> Espera 0.5 segundos.
```

<!--
Derecha es `sumar a x 20`; izquierda, `sumar a x -20`.

Errores típicos:
- Falta la coma en `unir`: el modelo recibe un solo número.
- Los nombres de las clases del programa no coinciden con los del modelo.
- Ejemplos solo con inclinaciones fuertes: con la placa poco inclinada, la
  confianza no llega a 70 y el echidna no se mueve.
-->

---

<!-- _class: seccion -->

## **4** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Pasos de gigante

Cambia los **20 pasos** y el **tiempo de espera** para que el echidna se mueva más rápido o más despacio.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** cambia el valor de los dos `sumar a x` (20 y -20) y el del `esperar 0.5 segundos`.

</div>

---

## Mejóralo 2: Placa quieta

Añade la clase **Quieta** con ejemplos de la placa en horizontal, para que el echidna no se mueva cuando no la inclinas.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** con la placa en horizontal, X e Y están cerca de **0**. Añade esos ejemplos a la clase **Quieta** y vuelve a pulsar **Aprender**; en el programa no hace falta añadir nada.

</div>

---

## Mejóralo 3: Cuatro direcciones

Añade las clases **Adelante** y **Atrás** (inclinando la placa en el eje Y) para que el echidna también se mueva hacia arriba y hacia abajo.

---

## Mejóralo 3: Pista

<div class="pista">

**Pista:** entrena las dos clases nuevas en LearningML y añade dos `si` más con `sumar a y 20` (Adelante) y `sumar a y -20` (Atrás).

</div>

---

<!-- _class: seccion -->

## **5** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Por qué el modelo tiene **2 columnas**?
2. ¿Qué valores da el eje X al inclinar la placa a la **izquierda**? ¿Y a la **derecha**?
3. ¿Para qué sirve el bloque `unir` en este programa?
4. ¿Qué diferencia hay con **2.11 Movemos el echidna**, que también usa el acelerómetro?

<!--
Respuestas:
1. Porque cada ejemplo tiene dos números: el eje X y el eje Y.
2. Negativos (hasta -1) a la izquierda y positivos (hasta 1) a la derecha.
3. Para juntar acelX y acelY con una coma, que es el formato que espera
   el modelo.
4. En 2.11 la dirección se decide con umbrales que pone quien programa
   (0,5 y -0,5); aquí la aprende el modelo a partir de ejemplos.
-->

---

## He conseguido…

<div class="logros">

- Entrenar un modelo con datos del acelerómetro.
- Mover el echidna inclinando la placa y pulsando SL.
- Cambiar la velocidad del echidna (Mejóralo 1).
- Que el echidna no se mueva con la placa quieta (Mejóralo 2).
- Mover el echidna en cuatro direcciones (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para recoger los datos o entrenar el modelo,
  o el echidna no se mueve.
- Conseguido: el mando funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con las cuatro direcciones.
-->

---

## Qué he aprendido

<div class="logros">

- A crear un **modelo de machine learning** que clasifica **números**.
- A recoger **datos** de un sensor para entrenar un modelo.
- A introducir ejemplos con **varias columnas** (en nuestro caso, los ejes X e Y del acelerómetro).
- A usar el modelo en EchidnaBlocks para controlar un personaje.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Has terminado los Proyectos de inicio con EchidnaML.

Ya puedes crear tus propios proyectos con la placa y con IA.

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
