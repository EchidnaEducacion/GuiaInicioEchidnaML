# Interruptor crepuscular

![Imagen cabecera Interruptor crepuscular](./imagenes/Interruptor_crepuscular.png)

## 1. Qué vamos a hacer

Vamos a realizar un sistema que controle el encendido de un LED en función d la cantidad de luz que reciba el sensor de luz. Con alta luminosidad el LED está apagado y con baja intensidad se enciende.

--> Video del funcionamiento

### 1.1 Qué vamos a aprender
- A programar un sistema automático que controle el encendido de un LED según la luz
- A usar bloques condicionales

### 1.2 Qué componentes vamos a usar

Usaremos la LDR, que es un sensor de luz, y un LED.

IMAGEN LUPA LDR

# 2. Programación

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

# 3. Mejóralo

Prueba a realizar algunas de las siguientes modificaciones al proyecto:

1. Crea dos fondos uno de noche y otro de dia que cambien con la luz. 
