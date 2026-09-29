# Interruptor crepuscular

![Imagen cabecera Interruptor crepuscular](./imagenes/Interruptor_crepuscular.png)

## 1. Qué vamos a hacer

Vamos a programar un sistema automático similar al de las farolas de la calle: el **LED verde** se encenderá automáticamente cuando la luz ambiental baje (de noche) y se apagará cuando haya suficiente luz (de día).

--> Video del funcionamiento

### 1.1 Qué vamos a aprender

* A programar un **sistema automático** que reaccione al entorno.
* A utilizar el **sensor de luz (LDR)** para medir la iluminación ambiental.
* A tomar decisiones en el programa mediante el bloque condicional **`si ... si no`**.
* A trabajar con **umbrales numéricos** para definir estados (día/noche).

### 1.2 Qué componentes vamos a usar

* **Sensor de luz (LDR):** Mide la cantidad de luz que recibe. Cuanto más oscuro esté el entorno, menor será el valor registrado.
* **LED Verde:** Funcionará como nuestra luz automática.

IMAGEN LUPA LDR

## 2. Programación

Revisamos continuamente el valor del sensor de luz, en caso de que sea menor que un cierto umbral encendemos el LED, en caso contrario lo apagamos.

![Bloques programación interruptor crepuscular](https://github.com/EchidnaEducacion/manual/raw/main/docs/assets/images/Ejemplo_sensor_luz.png)

**Lógica de programación**:

El programa revisa continuamente:

```
SI el sensor de luz registra valores menores de 200:
    --> Se enciende el LED verde.

SI NO (si registra valores mayores):
    --> Se apaga el LED.
```

El valor 200 actúa como el umbral que define cuándo debe encenderse o apagarse la luz.

## 3. Mejóralo

Prueba a realizar algunas de estas mejoras en tu proyecto de forma autónoma:

1. 🎯 **Calibra tu aula:** Averigua qué valor lee el sensor de luz en tu mesa y ajusta el umbral exacto para que la luz se encienda solo cuando tapes el sensor con la mano. Para leer el valor del sensor de luz marca el tick al lado del bloque.
2. 🌄 **Fondo de Día y Noche:** Añade dos fondos al escenario de EchidnaML (uno soleado y otro nocturno). Haz que el fondo cambie en la pantalla al mismo tiempo que se enciende o apaga el LED en la placa.
3. 🚨 **Luz de emergencia RGB:** En lugar de usar el LED verde, haz que si hay mucha luz el LED RGB se ponga **Verde**, y si hay oscuridad se encienda en **Rojo**.
