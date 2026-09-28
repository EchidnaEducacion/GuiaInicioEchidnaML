# Semáforo

![Imagen cabecera semaforo](./imagenes/EchidnaSemaforo.png)

## 1. Qué vamos a hacer

Vamos a realizar un semaforo en el que el LED Verde se enciende 5 segundos, luego se enciende el LED naranja durante 2s y finalmente el LED Rojo durante 5s. El ciclo se repite por siempre.


--> GIF o video del funcionamiento?

### 1.1 Qué vamos a aprender
* A diseñar **secuencias temporizadas** (eventos que ocurren en un orden y tiempo exactos).
* A controlar múltiples componentes digitales (LEDs) de forma coordinada.
* A estructurar un ciclo de estados infinito (**programación cíclica**).

### 1.2 Qué componentes vamos a usar

* **LED Verde:** Fase de paso.
* **LED Naranja:** Fase de precaución.
* **LED Rojo:** Fase de detención.

![LEDes en EchidnaBlack](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Lupa_Ledes.png)

## 2. Programación

La programación se basa en una secuencia cíclica donde cada LED permanece encendido durante un tiempo específico y luego pasa al siguiente estado de forma automática.

![Bloques programación semáforo](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Semaforo.png)

**Estados**:
1. El LED verde se enciende durante 5 segundos. Al finalizar este tiempo, se apaga.
2. El LED naranja se enciende durante 2 segundos, y luego se apaga.
3. El LED rojo se enciende durante 5 segundos. Transcurrido este tiempo, se apaga.

Luego, el ciclo vuelve a comenzar con la luz verde y se repite de forma indefinida.

## 3. Mejóralo

Prueba a perfeccionar tu semáforo con algunas de estas tres mejoras que te proponemos:

1. 🚦 **Semáforo Virtual en Pantalla:** Diseña un objeto "Semáforo" en EchidnaML con tres disfraces (Verde, Naranja, Rojo). Programa el personaje para que cambie de disfraz en la pantalla al mismo tiempo que cambian los LEDs en la placa real.
2. ⚠️ **Naranja Intermitente:** Modifica la fase intermedia para que el LED Naranja no se quede fijo, sino que **parpadee 3 veces rápidas** (encendido 0.3s / apagado 0.3s) antes de pasar al Rojo.
3. 🔊 **Semáforo Sonoro Adaptado:** Añade el **Zumbador** de la placa para avisar a personas con discapacidad visual:
   * **Fase Verde:** Sonido intermitente lento.
   * **Fase Rojo:** Sonido continuo o apagado.
