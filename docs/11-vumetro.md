# Vúmetro

![Imagen cabecera Vúmetro](assets/images/Vumetro.png "Imagen cabecera Vúmetro"){ .img-cabecera }

--> Video del funcionamiento

## 1. Qué vamos a hacer

Vamos a construir un **vúmetro** o **semáforo de ruido**, que muestra con los LED de la placa cuánto ruido hay a nuestro alrededor. Con silencio se encenderá solo el **LED verde**; si el ruido aumenta, se encenderá también el **naranja**; y si hay mucho ruido, se encenderán los **tres LED**.

### 1.1 Qué vamos a aprender

* A utilizar el **micrófono** para medir la **intensidad del sonido**.
* A usar un condicional `si ... si no` **dentro de otro** para distinguir tres niveles.
* A trabajar con **umbrales numéricos** para definir estados (silencio, ruido moderado y mucho ruido).
* A entender por qué algunas señales, como el sonido, **cambian constantemente**.

### 1.2 Qué componentes vamos a usar

* **Micrófono:** Convierte las vibraciones del sonido en una señal eléctrica. Da valores bajos con silencio y valores más altos cuanto más intenso es el sonido, entre 0 y 1023.
* **LED verde, naranja y rojo:** Nos indicarán el nivel de ruido.

![Micrófono en EchidnaBlack2](assets/images/Lupa_Microfono.png "Micrófono en EchidnaBlack2"){ .img-lupa }

Si marcas la casilla que hay junto al bloque `leer micrófono`, verás en el escenario el valor que mide en cada momento.

## 2. Programación

Revisamos continuamente el valor del micrófono y, según el nivel de ruido, encendemos o apagamos cada uno de los tres LED.

![Bloques programación Vúmetro](assets/images/Ejemplo_vumetro.png "Bloques programación Vúmetro")

**Lógica de programación**:

El programa revisa continuamente:

```
SI el micrófono registra valores menores de 20 (silencio):
    --> Se enciende el LED verde y se apagan el naranja y el rojo.

SI NO:
    SI registra valores menores de 50 (entre 20 y 50, ruido moderado):
        --> Se encienden los LED verde y naranja y se apaga el rojo.

    SI NO (50 o más, mucho ruido):
        --> Se encienden los tres LED.
```

Es probable que veas que los LED **parpadean** aunque el ruido sea constante. Esto ocurre porque la señal del sonido cambia muy deprisa: el micrófono capta las vibraciones de la onda sonora y cada lectura da un valor distinto. En la segunda propuesta de Mejóralo aprenderás a solucionarlo.

## 3. Mejóralo

Prueba a realizar algunas de estas mejoras en tu proyecto de forma autónoma:

1. **Calibra tu aula:** Observa qué valores mide el micrófono con silencio, hablando en voz baja y dando una palmada, y ajusta los umbrales (20 y 50) para que el vúmetro funcione bien en tu clase.
2. **Una lectura más estable:** Para que los LED no parpadeen, en lugar de usar cada lectura del micrófono calcula la **media** de varias. Crea las variables `suma`, `numeroDatos` y `mediaSonido`: en cada vuelta suma a `suma` la lectura del micrófono y suma 1 a `numeroDatos`; cuando tengas 10 datos, guarda en `mediaSonido` la división `suma / numeroDatos` y vuelve a poner `suma` y `numeroDatos` a 0. Después usa `mediaSonido` en los condicionales.
3. **Silencio, por favor:** Haz que, cuando se enciendan los tres LED, el echidna del escenario diga "¡Silencio, por favor!".
