# Semáforo

![Imagen cabecera semaforo](./imagenes/EchidnaSemaforo.png)

## 1. Qué vamos a hacer

Vamos a realizar un semaforo en el que el LED Verde se enciende 5 segundos, luego se enciende el LED amarillo durante 2s y finalmente el LED Rojo durante 5s. El ciclo se repite por siempre.

--> GIF o video del funcionamiento?

### 1.1 Qué vamos a aprender
- A programar un semáforo
- A usar los LEDs digitalmente
- A realizar una programación cíclica

### 1.2 Qué componentes vamos a usar

Usaremos los 3 LEDes que vienen en la parte central de la Echidna.

![LEDes en EchidnaBlack](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Lupa_Ledes.png)

# 2. Programación

La programación se basa en una secuencia cíclica donde cada LED permanece encendido durante un tiempo específico y luego pasa al siguiente estado de forma automática.

![Bloques programación semáforo](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Semaforo.png)

**Estados**:
1. El LED verde se enciende durante 5 segundos. Al finalizar este tiempo, se apaga.
2. El LED naranja se enciende durante 2 segundos, y luego se apaga.
3. El LED rojo se enciende durante 5 segundos. Transcurrido este tiempo, se apaga.

Luego, el ciclo vuelve a comenzar con la luz verde y se repite de forma indefinida.

# 3. Mejóralo

Prueba a realizar algunas de las siguientes modificaciones al proyecto:

1. Crea una animación en Scratch del semáforo de modo que tengamos un semáforo real y uno virtual.
2. Haz que el led naranja se vuelva intermitente.
3. Añade el zumbador para que avise que el semáforo cambia a rojo.
