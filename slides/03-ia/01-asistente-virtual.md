---
marp: true
theme: echidna
paginate: true
footer: "3.1 Asistente virtual · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 3.1 Asistente virtual

![Modelo de texto](../assets/images/MODELO_TEXTOS.png)

<!--
Notas del docente: primer proyecto con IA. Se presentan LearningML y sus
fases (Entrenar, Aprender, Probar y Programar). Cómo abrir LearningML y su
entorno se explica en la introducción de la sección 3 de la guía.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a crear un **asistente virtual** que entiende lo que le escribimos. Le pediremos con nuestras propias palabras que **encienda** o **apague** la luz, y el asistente encenderá o apagará el **LED RGB** de la placa.

Para que entienda frases que nunca ha visto, crearemos con **LearningML** un **modelo de texto**: le enseñaremos ejemplos de frases para encender y para apagar la luz, y él aprenderá a reconocerlas.

---

## Qué vamos a aprender

- A crear un **modelo de machine learning** que clasifica **textos**.
- A organizar los datos en **clases** y a añadir **ejemplos** a cada una.
- A **entrenar**, **probar** y **mejorar** un modelo.
- A usar la **confianza** del modelo para decidir si nos fiamos de su respuesta.
- A usar el modelo en EchidnaBlocks para controlar la placa.

---

## Componentes

<div class="dos-columnas">
<div>

- **LED RGB:** se enciende en blanco o se apaga según lo que le pidamos.
- **Teclado** del ordenador: para escribir las órdenes.

</div>
<div>

![LED RGB en EchidnaBlack2](../assets/images/Lupa_LEDRGB.png)

</div>
</div>

---

## Programación

Para usar el modelo en nuestro programa usamos el bloque `clasificar texto`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_clasificar_texto.png" alt="Bloque clasificar texto">
</div>

Le damos un **texto** y nos devuelve la **clase** que el modelo considera más probable; en nuestro caso, **Enciende** o **Apaga**.

---

<!-- _class: seccion -->

## **2** Entrenamos el modelo

Entrenar, aprender y probar en LearningML

---

## Entrenar: clases y ejemplos

<div class="dos-columnas" style="grid-template-columns: 3fr 2fr;">
<div>

Abrimos LearningML, elegimos un modelo de **texto** y creamos dos **clases** con ejemplos de frases:

- **Enciende:** "Luz on", "No veo", "Es de noche", "Quiero leer"…
- **Apaga:** "Luz off", "Apaga", "Hay mucha luz", "Voy a dormir"…

</div>
<div class="centro">

![Clase Enciende](../assets/images/Enciende.png)

</div>
</div>

<!--
Para abrir LearningML se pulsa «Ir a LearningML» en EchidnaBlocks; para
volver, «Ir a EchidnaBlocks». Cuantos más ejemplos, y más variados, mejor
clasificará el modelo: la calidad del modelo depende de los datos.
-->

---

## Aprender

<div class="dos-columnas" style="grid-template-columns: 3fr 2fr;">
<div>

Pulsamos **Aprender a reconocer textos**.

El algoritmo analiza los ejemplos y construye un **modelo** capaz de clasificar textos que no ha visto antes: es el **aprendizaje a partir de datos**.

</div>
<div class="centro">

![Aprender a reconocer textos](../assets/images/2-_Aprender_textos.png)

</div>
</div>

---

## Probar

<div class="dos-columnas">
<div>

Escribimos frases **nuevas** y vemos su clase y su **confianza** (en %).

"Me voy a la cama" sale **Apaga** con un 65 %.

Si se equivoca o la confianza es baja, volvemos a **Entrenar**.

</div>
<div class="centro">

![Probar el modelo de textos](../assets/images/3-probar_textos.png)

</div>
</div>

<!--
Probar con frases nuevas comprueba que el modelo ha aprendido y no solo ha
memorizado los ejemplos.
-->

---

<!-- _class: seccion -->

## **3** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Cuando el modelo funcione bien, abrimos **EchidnaBlocks** y construimos el programa con los bloques de LearningML y los de la placa.

Pulsa la **bandera verde** para ejecutarlo.

</div>
<div class="centro">

![Bloques programación Asistente virtual](../assets/images/modelo_texto_EchidnaBlocks.png)

</div>
</div>

---

## Cómo funciona

El echidna pregunta "¿Qué necesitas?" y espera nuestra respuesta. Solo nos hace caso si la **confianza** es mayor de 60:

```
SI la confianza es mayor de 60:
    SI la clase es "Enciende":
        --> El LED RGB se enciende en blanco.
    SI la clase es "Apaga":
        --> El LED RGB se apaga.
SI NO:
    --> El echidna dice "No te he entendido".
```

Dentro de un `por siempre`, vuelve a preguntar, listo para una nueva orden.

<!--
Blanco es R 255, G 255, B 255; apagado, R 0, G 0, B 0.

Errores típicos:
- Los nombres de las clases del programa no coinciden con los del modelo
  (mayúsculas incluidas).
- No se ha pulsado «Aprender» después de añadir ejemplos.
- La placa no está conectada o EchidnaML no la detecta.
-->

---

<!-- _class: seccion -->

## **4** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Más exigente

Cambia el **60** de confianza por **80**.

¿Qué ocurre con las frases que antes entendía con dudas?

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** el valor está en el primer `si`, donde se compara `confianza para el texto` con 60. Con 80, las frases dudosas reciben «No te he entendido».

</div>

---

## Mejóralo 2: Entrénalo mejor

Busca frases que el asistente **no entienda** o **clasifique mal**, añádelas como ejemplos a su clase y vuelve a entrenar el modelo.

¿Sube la confianza?

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** vuelve a LearningML, añade los ejemplos a la clase correcta y pulsa de nuevo **Aprender a reconocer textos**.

</div>

---

## Mejóralo 3: Elige el color

Añade las clases **Rojo**, **Verde** y **Azul** para que, además de encender y apagar, el asistente cambie el color del LED RGB según lo que le pidas.

---

## Mejóralo 3: Pista

<div class="pista">

**Pista:** cada clase nueva necesita sus ejemplos en LearningML y su propio `si` en el programa con el color del LED RGB.

</div>

---

<!-- _class: seccion -->

## **5** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué es una **clase**? ¿Y un **ejemplo**?
2. ¿Por qué probamos el modelo con frases que **no** están en los ejemplos?
3. ¿Qué hacemos si el modelo se equivoca o la confianza es baja?
4. ¿Para qué sirve comprobar la **confianza** en el programa?

<!--
Respuestas:
1. Una clase es cada categoría en la que el modelo puede clasificar un dato
   (Enciende, Apaga); un ejemplo es cada dato que añadimos a una clase.
2. Para comprobar que ha aprendido y no solo ha memorizado los ejemplos.
3. Volver a Entrenar: revisar los ejemplos, añadir otros nuevos y aprender
   de nuevo.
4. Para no actuar cuando el modelo no está seguro de su respuesta.
-->

---

## He conseguido…

<div class="logros">

- Entrenar un modelo que distingue Enciende y Apaga.
- Encender y apagar el LED RGB escribiendo órdenes.
- Hacer el asistente más exigente con la confianza (Mejóralo 1).
- Mejorar el modelo con nuevos ejemplos (Mejóralo 2).
- Cambiar el color del LED RGB con clases nuevas (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para entrenar el modelo o el programa no
  responde a las órdenes.
- Conseguido: el asistente funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 con las clases de colores.
-->

---

## Qué he aprendido

<div class="logros">

- A crear un **modelo de machine learning** que clasifica **textos**.
- A organizar los datos en **clases** y a añadir **ejemplos** a cada una.
- A **entrenar**, **probar** y **mejorar** un modelo.
- A usar la **confianza** del modelo para decidir si me fío de su respuesta.
- A usar el modelo en EchidnaBlocks para controlar la placa.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya has creado tu primer modelo de inteligencia artificial.

Siguiente proyecto: **3.2 Clasificador de residuos**

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
