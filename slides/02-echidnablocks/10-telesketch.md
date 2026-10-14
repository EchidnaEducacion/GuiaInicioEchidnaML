---
marp: true
theme: echidna
paginate: true
footer: "2.10 Telesketch · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.10 Telesketch

![Telesketch](../assets/images/Telesketch.png)

<!--
Notas del docente: se presentan el joystick (dos ejes analógicos) y la
extensión Lápiz. Es el primer proyecto con varios `si` seguidos e
independientes, uno por dirección, y con coordenadas del escenario.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a convertir la pantalla de EchidnaML en un **Telesketch**, la pizarra mágica que dibuja líneas con dos ruedas.

Usaremos el **joystick** de la placa: al mover la palanca hacia un lado, el **lápiz** dibujará una línea en el escenario en esa misma dirección.

<!--
Pregunta antes de programar: ¿alguien ha usado un Telesketch? ¿Cómo se
dibuja una diagonal con dos ruedas? ¿Y con nuestro joystick?
-->

---

## Qué vamos a aprender

- A utilizar el **joystick** y sus dos ejes: horizontal (**X**) y vertical (**Y**).
- A leer **valores analógicos** entre 0 y 1023.
- A usar la extensión **Lápiz** de EchidnaML para dibujar en el escenario.
- A combinar varios condicionales `si` con **umbrales** (`>` y `<`) para detectar hacia dónde movemos la palanca.
- A mover un objeto por el escenario usando **direcciones** y **coordenadas**.

---

## Componentes

<div class="dos-columnas">
<div>

- **Joystick:** palanca que se mueve en varias direcciones. Tiene dos potenciómetros, uno para cada eje, que indican hacia dónde y cuánto la has desplazado.
- Al **presionar** la palanca funciona como el pulsador **SR**.

</div>
<div>

![Joystick en EchidnaBlack2](../assets/images/Lupa_Joystick.png)

</div>
</div>

---

## Programación

Para leer el joystick usamos el bloque `leer joystick`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_joystick.png" alt="Bloque leer joystick">
</div>

- Puedes elegir el eje **x** (horizontal) o el eje **y** (vertical).
- Da valores entre **0** y **1023**.

---

## Valores del joystick

<div class="dos-columnas">
<div>

- En **reposo**: alrededor de **512** en los dos ejes.
- **Eje X:** **0** a la izquierda y **1023** a la derecha.
- **Eje Y:** **0** hacia abajo y **1023** hacia arriba.

</div>
<div class="centro">

![height:440px Valores del joystick](../assets/images/valores_joystick.png)

</div>
</div>

<!--
Marcar la casilla junto a `leer joystick` para ver los valores en el
escenario mientras se mueve la palanca. En reposo no siempre da 512
exacto: por eso el programa usa umbrales con margen.
-->

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## Configuración inicial

<div class="dos-columnas">
<div>

Añade la extensión **Lápiz**: pulsa el botón de extensiones (abajo a la izquierda) y elige **Lápiz**.

Al pulsar la **bandera verde**, el lápiz borra el escenario, va al centro (0, 0), fija color y grosor y **baja** para dibujar.

</div>
<div class="centro">

![Configuración inicial del lápiz](../assets/images/Ejemplo_joystick_configuracion_inicial.png)

</div>
</div>

---

## Control con el joystick

<div class="dos-columnas">
<div>

Revisamos continuamente los dos ejes del joystick.

Si la palanca está desplazada hacia un lado, el objeto **apunta** en esa dirección y **avanza 20 pasos**, dibujando una línea.

</div>
<div class="centro">

![Bloques programación Telesketch](../assets/images/Ejemplo_Pintamos.png)

</div>
</div>

<!--
Los dos programas empiezan con la bandera verde y van en el mismo
objeto.
-->

---

## Cómo funciona

```
SI el eje x es mayor de 900 (derecha):
    --> Apunta en dirección 90 y avanza 20 pasos.
SI el eje x es menor de 100 (izquierda):
    --> Apunta en dirección -90 y avanza 20 pasos.
SI el eje y es mayor de 900 (arriba):
    --> Apunta en dirección 0 y avanza 20 pasos.
SI el eje y es menor de 100 (abajo):
    --> Apunta en dirección 180 y avanza 20 pasos.
```

En **reposo** (unos 512) no se cumple ninguna condición: el lápiz no se mueve.

<!--
Los valores 900 y 100 son los umbrales. El bloque `esperar 0.3
segundos` evita que el lápiz se mueva demasiado rápido.

Errores típicos:
- No añadir la extensión Lápiz: no aparecen sus bloques.
- Olvidar `bajar lápiz`: el objeto se mueve pero no dibuja.
- Confundir el eje (x en lugar de y) o la dirección (90 a la derecha,
  -90 a la izquierda, 0 arriba y 180 abajo).
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Borra la pizarra

Como en un Telesketch de verdad, haz que al **presionar el joystick** (pulsador **SR**) se **borre el dibujo** y el lápiz **vuelva al centro** del escenario.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** dentro del `por siempre`, añade un `si ¿botón SR pulsado? entonces` con `borrar todo` e `ir a x: 0 y: 0`.

</div>

---

## Mejóralo 2: Cambia de color

Usa el pulsador **SL** para **cambiar el color del lápiz** cada vez que lo pulses.

Enciende el **LED RGB** del mismo color para saber con cuál estás pintando.

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** con `si ¿botón SL pulsado? entonces`, cambia el color con `fijar color de lápiz a` y pon el mismo color en `LED R G B`. Para encontrar sus valores, usa el selector de colores de 2.8.

</div>

<!--
Para alternar entre varios colores hace falta una variable que cuente
las pulsaciones. Con `esperar hasta que no ¿botón SL pulsado?` cada
pulsación cuenta solo una vez.
-->

---

## Mejóralo 3: Controla la velocidad

Haz que el lápiz avance **más o menos pasos** según **cuánto** muevas la palanca del joystick.

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** usa los bloques `cambiar x en` y `cambiar y en` con el valor de cada eje **menos 512** (para que en reposo valga 0) y divídelo, por ejemplo, **entre 50**.

</div>

<div class="pendiente">

IMAGEN AYUDA TELESKETCH MEJORA 3

</div>

<!--
Con la palanca a tope, (1023 - 512) / 50 da unos 10 pasos; en reposo,
0. Así ya no hacen falta los cuatro `si` ni las direcciones, y se
pueden dibujar diagonales.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué valores da el joystick en **reposo**?
2. ¿Qué valor da el eje **x** con la palanca a la **izquierda**?
3. ¿Por qué usamos los umbrales **900** y **100**, y no 512?
4. ¿Qué pasa si quitamos el bloque `bajar lápiz`?

<!--
Respuestas:
1. Alrededor de 512 en los dos ejes.
2. Un valor cercano a 0.
3. Porque en reposo el valor no es exactamente 512 y varía un poco: con
   margen, el lápiz solo se mueve cuando desplazamos la palanca.
4. El objeto se mueve, pero no dibuja.
-->

---

## He conseguido…

<div class="logros">

- Dibujar en el escenario moviendo el joystick.
- Borrar el dibujo presionando el joystick (Mejóralo 1).
- Cambiar el color del lápiz y del LED RGB con SL (Mejóralo 2).
- Controlar la velocidad con la palanca (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir los condicionales o
  configurar el lápiz.
- Conseguido: el Telesketch funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 y dibuja diagonales.
-->

---

## Qué he aprendido

<div class="logros">

- A utilizar el **joystick** y sus dos ejes: horizontal (**X**) y vertical (**Y**).
- A leer **valores analógicos** entre 0 y 1023.
- A usar la extensión **Lápiz** de EchidnaML para dibujar en el escenario.
- A combinar varios condicionales `si` con **umbrales** (`>` y `<`) para detectar hacia dónde movemos la palanca.
- A mover un objeto por el escenario usando **direcciones** y **coordenadas**.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes dibujar en la pantalla con el joystick.

Siguiente proyecto: **2.11 Movemos el echidna**

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
