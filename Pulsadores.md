# Pulsadores

![Imagen cabecera pulsadores](./imagenes/Pulsadores.png)

## 1. Qué vamos a hacer

Vamos a programar un sistema de encendido y apagado manual con dos botones:
* Al presionar el **pulsador derecho (SR)**, el **LED rojo** se encenderá.
* Al presionar el **pulsador izquierdo (SL)**, el **LED rojo** se apagará.

### 1.1 Qué vamos a aprender

* A leer **entradas digitales** (saber si un botón está presionado o no).
* A utilizar **condicionales anidados** (`si ... si no` y dentro otro `si`).
* A controlar el estado de un actuador (LED) mediante eventos físicos, pulsación.

### 1.2 Qué componentes vamos a usar

* **Pulsador SR (Switch Right / Derecho):** Para encender el LED.
* **Pulsador SL (Switch Left / Izquierdo):** Para apagar el LED.
* **LED Rojo:** Componente que cambia de estado según el botón pulsado.

IMAGEN LUPA PULSADORES

## 2. Programación

El programa comprueba que el pulsaro derecho está presionado, en ese caso enciende el LED rojo, si no está presionado y presionamos el pulsador izquiero el LED se apaga.

![Bloques programación pulsadores](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Ejemplo_encender_apagar_led_pulsadores.png)

**Lógica de programación**:

El programa revisa continuamente:

```
SI el pulsador derecho (SR) está presionado:
    --> Enciende el LED Rojo inmediatamente.

SI NO (es decir, si SR no está presionado el programa comprueba la segunda condición):
    SI el pulsador izquierdo (SL) está presionado:
        --> Apaga el LED Rojo
```

## 3. Mejóralo

Prueba a realizar algunas de las siguientes modificaciones al proyecto:

1. 🖥️ **LED Virtual en pantalla:** Crea un personaje u objeto en EchidnaML que cambie de disfraz (encendido/apagado) al mismo tiempo que cambia el LED físico de la placa.
2. 🚦 **Luz cruzada (Bi-estable):** Añade el **LED verde** al programa para que funcionen de forma alterna:
   * Al pulsar **SR**: LED Rojo ENCENDIDO y LED Verde APAGADO.
   * Al pulsar **SL**: LED Rojo APAGADO y LED Verde ENCENDIDO.
3. 🧠 **Pulsador con memoria (Conmutador):** Programa un solo pulsador (por ejemplo, **SL**) para que funcione como el interruptor de la luz de tu habitación: la primera vez que lo pulsas enciende el LED, y al volverlo a pulsar lo apaga.

![Bloques programación pulsador con memoria](https://github.com/EchidnaEducacion/manual/blob/main/docs/assets/images/Ejemplo_pulsador_memoria.png?raw=true)

