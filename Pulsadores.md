# Pulsadores

![Imagen cabecera pulsadores](./imagenes/Pulsadores.png)

## 1. Qué vamos a hacer

Este ejemplo utiliza dos pulsadores para controlar el encendido y apagado del LED rojo. El pulsador derecho (SR) controla el encendido del LED rojo y el pulsador izquierdo (SL) el apagado.

--> GIF o video del funcionamiento?

### 1.1 Qué vamos a aprender

- A controlar un LED mediante pulsadores.
- A utilizar un si anidado.

### 1.2 Qué componentes vamos a usar

Usaremos los 2 pulsadores SL y SR y el LED rojo.

IMAGEN LUPA PULSADORES

# 2. Programación

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

# 3. Mejóralo

Prueba a realizar algunas de las siguientes modificaciones al proyecto:

1. Crea una animación en Scratch en la que el LED se encienda y apague sincronizado con el LED rede la placa.
2. Añade el LED verde y haz que cuando el LED rojo encendido- verde apagado, y cuando el LED rojo apagado-verde encendido.
3. Prueba a programar un pulsador con Memoria, que al presionar encienda el LED y se mantenga encendido hasta que se vuelva a presionar.

![Bloques programación pulsador con memoria](https://github.com/EchidnaEducacion/manual/blob/main/docs/assets/images/Ejemplo_pulsador_memoria.png?raw=true)

