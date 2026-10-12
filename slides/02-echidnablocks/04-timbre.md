---
marp: true
theme: echidna
paginate: true
footer: "2.4 Timbre · Proyectos de inicio con EchidnaML"
---

<!-- _class: portada -->
<!-- _paginate: false -->
<!-- _footer: "Echidna Educación" -->

Proyectos de inicio con EchidnaML

# 2.4 Timbre

![Timbre](../assets/images/Zumbador.png)

<!--
Notas del docente: primer proyecto con sonido. Antes de empezar, baja el
volumen con el potenciómetro Volume de cada placa: con muchas placas
sonando a la vez el aula se vuelve ruidosa.
-->

---

<!-- _class: seccion -->

## **1** Qué vamos a hacer

El reto, lo que aprenderemos y lo que vamos a usar

---

## El reto

Vamos a programar un **timbre eléctrico**:

- el **zumbador** suena **mientras mantenemos pulsado** el **pulsador izquierdo (SL)**,
- y deja de sonar en cuanto lo **soltamos**.

<!--
Compáralo con el interruptor de luz (2.3): allí el LED se quedaba
encendido al soltar el botón; aquí el sonido dura solo mientras el botón
está pulsado.
-->

---

## Qué vamos a aprender

- A controlar un actuador de sonido (el **zumbador**) con un botón de entrada.
- A evaluar estados en tiempo real: pulsado o soltado.
- A usar el condicional **`si ... si no`** para que el zumbador suene solo mientras el pulsador está pulsado.

---

## Componentes

<div class="dos-columnas">
<div>

- **Pulsador SL** (izquierdo): entrada que activa el sonido.
- **Zumbador:** salida que genera pitidos.

El volumen se ajusta con el potenciómetro **Volume**.

</div>
<div>

![Zumbador en EchidnaBlack2](../assets/images/Lupa_Zumbador.png)

</div>
</div>

<!--
Si hay algo conectado al jack de audio, el zumbador se desconecta y no
suena.
-->

---

## Programación

Para hacer sonar el zumbador usamos el bloque `encender zumbador`:

<div class="centro">
<img class="img-bloque" src="../assets/images/Bloque_zumbador.png" alt="Bloque encender zumbador">
</div>

En el bloque elegimos si queremos **encender** o **apagar** el zumbador.

---

<!-- _class: seccion -->

## **2** Programamos

Construimos el programa y vemos cómo funciona

---

## El programa

<div class="dos-columnas">
<div>

Construye este programa arrastrando los bloques al área de trabajo.

Pulsa la **bandera verde** para ejecutarlo y mantén pulsado **SL**.

</div>
<div class="centro">

![Bloques programación zumbador](../assets/images/Ejemplo_pulsador-zumbador.png)

</div>
</div>

---

## Cómo funciona

`por siempre` revisa el pulsador una y otra vez:

```
SI el pulsador SL está pulsado:
    --> El zumbador suena.

SI NO (SL está soltado):
    --> El zumbador deja de sonar.
```

Así, el zumbador solo suena mientras mantenemos pulsado SL.

<!--
Errores típicos:
- Falta el `apagar zumbador` en el `si no`: el zumbador empieza a sonar y
  ya no se calla.
- Se ha elegido SR en lugar de SL.
- El volumen está al mínimo o hay algo conectado al jack: parece que el
  programa no funciona.
-->

---

<!-- _class: seccion -->

## **3** Mejóralo

Tres retos, de menos a más difícil

---

## Mejóralo 1: Alarma intermitente

Haz que, al mantener pulsado **SL**, el sonido no sea continuo, sino **pitidos intermitentes** tipo alarma:

- sonido `0.1` segundos,
- silencio `0.1` segundos.

---

## Mejóralo 1: Pista

<div class="pista">

**Pista:** dentro del `si`, enciende el zumbador, espera `0.1` segundos, apágalo y vuelve a esperar `0.1` segundos.

</div>

---

## Mejóralo 2: Emisor de código Morse

Programa el pulsador **SR** para emitir un **tono más agudo** que el pulsador **SL**.

Combina pulsaciones cortas y largas para enviar **mensajes secretos** en código Morse a tus compañeros.

<!--
El zumbador de la placa tiene un solo tono (2300 Hz), así que el tono
agudo de SR tiene que salir por el ordenador, con los bloques de música
que se usan en 2.6 Piano de frutas.
-->

---

## Mejóralo 2: Pista

<div class="pista">

**Pista:** el zumbador siempre suena con el mismo tono. Para el tono agudo de SR, usa el sonido del ordenador con el bloque `tocar nota`, como en el Piano de frutas.

</div>

---

## Mejóralo 3: Efecto visual de altavoz

Crea o elige un **objeto** con forma de altavoz o campana.

Haz que **cambie de tamaño** o **gire** de un lado a otro, como si vibrara, mientras el zumbador está sonando.

---

## Mejóralo 3: Ayuda

<div class="pista">

**Ayuda:** en el objeto, usa un `por siempre` con un `si ¿botón SL pulsado?`: dentro, gira unos grados a un lado y luego al otro; en el `si no`, déjalo recto.

</div>

<div class="pendiente">

IMAGEN AYUDA TIMBRE MEJORA 3

</div>

<!--
También puede hacerse con mensajes, como en los retos de LED virtual de
2.1 y 2.3.
-->

---

<!-- _class: seccion -->

## **4** Evaluación

Comprueba lo que has conseguido

---

## Comprueba lo que sabes

1. ¿Qué ocurre si quitamos el bloque `apagar zumbador` del `si no`?
2. ¿Cómo bajamos el **volumen** del zumbador?
3. ¿Qué cambiarías para que el timbre funcione con el pulsador **SR**?
4. ¿En qué se diferencia este timbre del **interruptor de luz** (2.3)?

<!--
Respuestas:
1. El zumbador empieza a sonar al pulsar SL y ya no deja de sonar.
2. Girando el potenciómetro Volume de la placa.
3. Elegir SR en el bloque `¿botón pulsado?`.
4. En el interruptor, el LED se queda como está al soltar el botón; en el
   timbre, el sonido dura solo mientras el botón está pulsado.
-->

---

## He conseguido…

<div class="logros">

- Hacer sonar el zumbador solo mientras pulso SL.
- Convertir el timbre en una alarma intermitente (Mejóralo 1).
- Emitir dos tonos distintos para enviar Morse (Mejóralo 2).
- Hacer que un objeto vibre en pantalla mientras suena (Mejóralo 3).

</div>

<!--
Rúbrica orientativa:
- En proceso: necesita ayuda para construir el programa o el zumbador no
  deja de sonar al soltar SL.
- Conseguido: el programa funciona y resuelve los retos 1 y 2.
- Avanzado: además, resuelve el reto 3 y el objeto se mueve solo mientras
  suena el zumbador.
-->

---

## Qué he aprendido

<div class="logros">

- A controlar un actuador de sonido (el **zumbador**) con un botón de entrada.
- A evaluar estados en tiempo real: pulsado o soltado.
- A usar el condicional **`si ... si no`** para que el zumbador suene solo mientras el pulsador está pulsado.

</div>

<!--
Son los objetivos de «Qué vamos a aprender». El alumnado marca los que
cree haber conseguido; sirve de autoevaluación.
-->

---

<!-- _class: seccion -->

## ¡Enhorabuena!

Ya sabes hacer sonar la placa al pulsar un botón.

Siguiente proyecto: **2.5 Interruptor crepuscular**

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
