# Makey Makey

![Imagen cabecera MkMk](./imagenes/MkMk.png)

## 1. Qué vamos a hacer

Vamos a convertir la entrada **MkMk A0** de nuestra placa en una tecla de piano táctil. Cada vez que toques la entrada (o un objeto conductor conectado a ella), el ordenador emitirá una nota musical.

### 1.1 Qué vamos a aprender

* A detectar la conductividad eléctrica de objetos cotidianos usando el **modo Makey Makey (MkMk)**.
* A conectar cables de cocodrilo en los conectores externos de la placa.
* A entender cómo funciona un **circuito cerrado** (hacer masa / GND).
* A reproducir notas musicales y sonidos desde el software.

### 1.2 Qué componentes vamos a usar

* **Entrada MkMk A0:** Conector táctil para detectar pulsaciones o conductividad.
* **Pin GND (Masa / Común):** Indispensable para cerrar el circuito con tu cuerpo.
* **Cables tipo cocodrilo:** Para conectar objetos externos (frutas, plastilina, papel de aluminio, etc.).

**¡ATENCIÓN!** Para que funcione el modo MkMk debemos poner el selector del modo de funcionamiento hacia la derecha, y se nos encenderá el LED testigo en la parte inferior.

![IMAGEN CONEXION MKMK](https://github.com/EchidnaEducacion/manual/blob/main/docs/assets/images/mkmk_conexion.png?raw=true)

## 2. Programación

Revisamos continuamente el valor del sensor tipo MkMk, **cuando la entrada MkMk A0 detecta contacto**, se ejecuta el bloque de sonido reproduciendo la **Nota 60** (que corresponde a la nota *Do central* del piano) durante **0,25 segundos**.

![Bloques programación MkMk](https://github.com/EchidnaEducacion/manual/blob/main/docs/assets/images/Ejemplo_MkMk_piano.png?raw=true)


## 3. Mejóralo

Prueba a realizar algunas de las siguientes modificaciones al proyecto:

1. 🎨 **Animación en pantalla:** Añade un personaje en EchidnaML (un instrumento o una nota musical) que cambie de disfraz, baile o salte en la pantalla cada vez que suene la nota.
2. 💡 **Luz y Sonido:** Haz que el **LED RGB** se ilumine de un color distinto cada vez que toques una tecla de tu piano MkMk.
3. 🎹 **Escala Musical:** Utiliza los otros conectores disponibles (**A1, A2, A3**) con otros cables para programar diferentes notas (por ejemplo: Do=60, Re=62, Mi=64, Fa=65) y crea un mini teclado completo.