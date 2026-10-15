---
marp: true
theme: echidna
paginate: true
footer: "3. Introducción a LearningML · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 3. Introducción a LearningML

![Fases LearningML](../assets/images/Fases_LML.png)

<!--
Notas del docente: presentación para la primera sesión de IA, antes de
3.1 Asistente virtual. Conviene tener EchidnaML abierto para enseñar en
directo cómo se pasa de EchidnaBlocks a LearningML y su entorno.
-->

---

<!-- _class: seccion -->

## **1** Qué es LearningML

La inteligencia artificial en nuestros proyectos

---

## LearningML

**EchidnaML** integra **LearningML**, una **plataforma educativa** para aprender los fundamentos del **machine learning** (aprendizaje automático) de forma sencilla y visual.

Con ella añadimos **inteligencia artificial** a nuestros proyectos con la placa EchidnaBlack2.

Crearemos **modelos** que clasifican **textos**, **imágenes** y **números**, y los usaremos en nuestros programas con los bloques de LearningML de EchidnaBlocks.

<!--
Idea clave para el alumnado: en lugar de escribir nosotros las reglas,
damos ejemplos y el ordenador aprende a partir de ellos. Por eso la calidad
y la variedad de los datos importan: si los ejemplos están sesgados, el
modelo también lo estará.
-->

---

## Conceptos clave

- **Modelo:** lo que construye el ordenador a partir de los ejemplos para clasificar datos nuevos.
- **Clase:** cada una de las categorías en las que el modelo puede clasificar un dato (por ejemplo, Enciende y Apaga).
- **Ejemplo:** cada dato que añadimos a una clase para enseñar al modelo cómo es esa clase.
- **Confianza:** el porcentaje de seguridad que tiene el modelo en su respuesta.

<!--
Un ejemplo cercano: un modelo que distingue perros de gatos tiene dos
clases (Perro y Gato); los ejemplos son las fotos que le damos de cada
uno, y ante una foto nueva responde «Gato» con, por ejemplo, un 85 % de
confianza.
-->

---

<!-- _class: seccion -->

## **2** Fases para crear un modelo

Entrenar, aprender, probar y programar

---

## Fases de LearningML

<div class="centro">

![h:200px Fases LearningML](../assets/images/Fases_LML_sin_titulo.png)

</div>

1. **Entrenar:** creamos las clases y añadimos los ejemplos.
2. **Aprender:** creamos el modelo.
3. **Probar:** comprobamos si clasifica bien; si no, volvemos a **Entrenar**.
4. **Programar:** usamos el modelo en **EchidnaBlocks**.

<!--
Insiste en que es un ciclo: si al probar el modelo se equivoca, no pasa
nada; añadimos más ejemplos (o más variados) y volvemos a aprender.
-->

---

<!-- _class: seccion -->

## **3** El entorno de LearningML

Dónde creamos los modelos

---

## Acceder a LearningML

Para abrir LearningML pulsamos el botón **Ir a LearningML** de EchidnaBlocks, y para volver, el botón **Ir a EchidnaBlocks**.

<div class="centro">

![h:400px Acceder a LearningML](../assets/images/EchidnaBlocks-_partes.png)

</div>

---

## El entorno de programación

<div class="centro">

![h:480px Entorno de LearningML](../assets/images/Entorno_LearningML.png)

</div>

<!--
Las partes que más usaremos en los proyectos:
- Nombre del archivo (6): el nombre con el que guardamos el modelo.
- Tipos de modelo (7): elegimos si queremos reconocer textos, imágenes o
  números.
- Ir a EchidnaBlocks (3): volvemos a EchidnaBlocks para usar el modelo en
  nuestro programa.
-->

---

## Tipos de modelo

<div class="dos-columnas">
<div>

- **Textos:** entiende frases que escribimos.
- **Imágenes:** reconoce lo que ve la cámara.
- **Números:** reconoce patrones en los datos de los sensores.

</div>
<div class="centro">

![h:140px Modelo de texto](../assets/images/MODELO_TEXTOS.png)
![h:140px Modelo de imágenes](../assets/images/Modelo_IA_imagenes.png)
![h:140px Modelo de números](../assets/images/MODELO_Numeros.png)

</div>
</div>

<!--
Haremos un proyecto con cada tipo: 3.1 Asistente virtual (textos),
3.2 Clasificador de residuos (imágenes) y 3.3 Mando de inclinación
(números, con el acelerómetro).
-->

---

<!-- _class: seccion -->

## **4** Los proyectos

Qué vamos a hacer y cómo

---

## Proyectos con IA

1. **Asistente virtual:** un modelo de **texto** que entiende nuestras órdenes para encender y apagar la luz.
2. **Clasificador de residuos:** un modelo de **imágenes** que reconoce con la cámara a qué contenedor va cada residuo.
3. **Mando de inclinación:** un modelo de **números** que reconoce, con el acelerómetro, hacia dónde inclinamos la placa.

---

## Cómo es cada proyecto

1. **Qué vamos a hacer:** el reto, qué vamos a aprender y qué vamos a usar.
2. **Entrenamos el modelo:** creamos las clases y los ejemplos, el modelo aprende y lo probamos.
3. **Programamos:** el programa de bloques que usa el modelo y cómo funciona.
4. **Mejóralo:** tres retos, de menos a más difícil, con una pista o una ayuda.
5. **Evaluación:** preguntas para comprobar lo que sabes y lo que has conseguido.

---

<!-- _class: seccion -->

## **5** Evaluación

Comprueba lo que has aprendido

---

## Comprueba lo que sabes

1. ¿Qué diferencia hay entre una **clase** y un **ejemplo**?
2. ¿Cuáles son las **fases** para crear un modelo?
3. ¿Qué hacemos si al **probar** el modelo se equivoca?
4. ¿Qué tres **tipos de modelo** podemos crear con LearningML?

<!--
Respuestas:
1. Una clase es una categoría en la que el modelo clasifica los datos; un
   ejemplo es cada dato que añadimos a una clase para enseñarle cómo es.
2. Entrenar, Aprender, Probar y Programar.
3. Volvemos a Entrenar: añadimos más ejemplos (o más variados) y el modelo
   vuelve a aprender.
4. De textos, de imágenes y de números.
-->

---

## Qué he aprendido

<div class="logros">

- Qué es **LearningML** y para qué sirve el **machine learning**.
- Qué son un **modelo**, una **clase**, un **ejemplo** y la **confianza**.
- Las **fases** para crear un modelo.
- A abrir LearningML y volver a **EchidnaBlocks**.

</div>

<!--
El alumnado marca lo que cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡A entrenar!

Ya conoces LearningML y sus fases.

Primer proyecto: **3.1 Asistente virtual**

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
