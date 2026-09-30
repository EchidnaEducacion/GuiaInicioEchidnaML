# Interruptor crepuscular

![Imagen cabecera Interruptor crepuscular](assets/images/Interruptor_crepuscular.png "Imagen cabecera Interruptor crepuscular"){ .img-cabecera }

## 1. Qué vamos a hacer

Vamos a programar un sistema automático similar al de las farolas de la calle: el **LED verde** se encenderá automáticamente cuando la luz ambiental baje (de noche) y se apagará cuando haya suficiente luz (de día).

--> Video del funcionamiento

### 1.1 Qué vamos a aprender

* A programar un **sistema automático** que reaccione al entorno.
* A utilizar el **sensor de luz (LDR)** para medir la iluminación ambiental.
* A usar un **operador de comparación** (`<`) para que el condicional `si ... si no` decida a partir de la lectura de un sensor.
* A trabajar con **umbrales numéricos** para definir estados (día/noche).

### 1.2 Qué componentes vamos a usar

* **Sensor de luz (LDR):** Mide la cantidad de luz que recibe. Cuanto más oscuro esté el entorno, menor será el valor registrado.
* **LED verde:** Funcionará como nuestra luz automática.

![Sensor de luz (LDR) en EchidnaBlack2](assets/images/Lupa_LDR.png "Sensor de luz (LDR) en EchidnaBlack2"){ .img-lupa }

## 2. Programación

Revisamos continuamente el valor del sensor de luz: si es menor que un cierto umbral, encendemos el LED; en caso contrario, lo apagamos.

![Bloques programación interruptor crepuscular](assets/images/Ejemplo_sensor_luz.png "Bloques programación interruptor crepuscular")

**Lógica de programación**:

El programa revisa continuamente:

```
SI el sensor de luz registra valores menores de 200:
    --> Se enciende el LED verde.

SI NO (si registra valores mayores o iguales a 200):
    --> Se apaga el LED verde.
```

El valor 200 actúa como el umbral que define cuándo debe encenderse o apagarse la luz.

## 3. Mejóralo

Prueba a realizar algunas de estas mejoras en tu proyecto de forma autónoma:

1. **Calibra tu aula:** Averigua qué valor lee el sensor de luz en tu mesa y ajusta el umbral exacto para que la luz se encienda solo cuando tapes el sensor con la mano. Para ver en pantalla el valor del sensor de luz, marca la casilla que hay junto al bloque `leer sensor luz`.
2. **Fondo de día y noche:** Añade dos fondos al escenario de EchidnaML (uno soleado y otro nocturno). Haz que el fondo cambie en la pantalla al mismo tiempo que se enciende o apaga el LED en la placa.
3. **Luz de emergencia RGB:** En lugar de usar el LED verde, haz que si hay mucha luz el LED RGB se ponga **Verde**, y si hay oscuridad se encienda en **Rojo**.
