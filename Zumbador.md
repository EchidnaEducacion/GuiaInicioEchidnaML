# Zumbador

![Imagen cabecera zumbador](./imagenes/Zumbador.png)

## 1. Qué vamos a hacer

Vamos a programar un timbre eléctrico: el **zumbador** emitirá un tono sonoro únicamente mientras mantengamos presionado el **pulsador izquierdo (SL)**, y se apagará inmediatamente al soltarlo.

--> GIF o video del funcionamiento?

### 1.1 Qué vamos a aprender

* A controlar un actuador de sonido (**zumbador**) mediante un botón de entrada.
* A diferenciar claramente entre una **Entrada (Input)** y una **Salida (Output)** en robótica:
  * **Entrada (SL):** Detecta la orden del usuario.
  * **Salida (Zumbador):** Produce la respuesta (sonido).
* A evaluar estados en tiempo real (`presionado` vs `liberado`).
### 1.2 Qué componentes vamos a usar

* **Pulsador SL (Switch Left / Izquierdo):** Componente de entrada para activar el sonido.
* **Zumbador (Buzzer):** Componente de salida que genera notas o pitidos.

IMAGEN LUPA ZUMBADOR

## 2. Programación

La programación se basa en revisar continuamente si el pulsador SL está presionado, si lo está se activa el pulsador y si no se apaga.

![Bloques programación zumbador](https://github.com/EchidnaEducacion/manual/blob/main/docs/assets/images/Ejemplo_pulsador-zumbador.png?raw=true)

**Lógica de programación**:

El programa revisa continuamente:

```
SI el pulsador es presionado (o activado):
    --> El zumbador suena.

SI el pulsador es liberado (o soltado):
    --> El zumbador deja de sonar.
```
De esta forma, el zumbador solo se activa mientras el pulsador se mantiene presionado.

## 3. Mejóralo

Prueba a realizar estas tres mejoras en tu proyecto de forma autónoma:

1. 🔊 **Efecto visual de altavoz (Vibración en pantalla):** Crea o selecciona un personaje en EchidnaML con forma de altavoz o campana. Haz que el personaje cambie de tamaño ligeramente o gire de un lado a otro (simulando vibración) mientras el zumbador esté sonando.
2. 🚨 **Alarma Intermitente:** Modifica el programa para que, al mantener pulsado **SL**, el sonido no sea continuo, sino que emita pitidos intermitentes tipo alarma (sonido 0.1s ➔ silencio 0.1s).
3. 📻 **Emisor de Código Morse:** Programa el pulsador **SR** para emitir un tono más agudo que el pulsador **SL**. ¡Intenta combinar pulsaciones cortas y largas para enviar mensajes secretos en código Morse a tus compañeros!