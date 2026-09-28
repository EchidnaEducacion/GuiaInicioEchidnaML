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

La programación se basa en una secuencia cíclica donde cada LED permanece encendido durante un tiempo específico y luego pasa al siguiente estado de forma automática.

![Bloques programación semáforo](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Ejemplo_encender_apagar_led_pulsadores.png)

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

1. Crea una animación en Scratch del semáforo de modo que tengamos un semáforo real y uno virtual.
2. Haz que hayas dos estados. LED rojo encencdifdo- verde apagado, LED rojo apagado-verde encendido.
