# 2.9 Vúmetro

![Imagen cabecera Vúmetro](../assets/images/Vumetro.png "Imagen cabecera Vúmetro"){ .img-cabecera }

## 1. Qué vamos a hacer

Vamos a construir un **vúmetro** o **semáforo de ruido**, que muestra con los LED de la placa cuánto ruido hay a nuestro alrededor. Con silencio se encenderá solo el **LED verde**; si el ruido aumenta, se encenderá también el **naranja**; y si hay mucho ruido, se encenderán los **tres LED**.

### 1.1 Qué vamos a aprender

* A utilizar el **micrófono** para medir la **intensidad del sonido**.
* A usar un condicional `si ... si no` **dentro de otro** para distinguir tres niveles.
* A trabajar con **umbrales numéricos** para definir estados (silencio, ruido moderado y mucho ruido).
* A entender por qué algunas señales, como el sonido, **cambian constantemente**.

### 1.2 Qué vamos a usar

#### Componentes

* **Micrófono:** Convierte las vibraciones del sonido en una señal eléctrica. Da valores bajos con silencio y valores más altos cuanto más intenso es el sonido, entre 0 y 1023.
* **LED verde, naranja y rojo:** Nos indicarán el nivel de ruido.

![Micrófono en EchidnaBlack2](../assets/images/Lupa_Microfono.png "Micrófono en EchidnaBlack2"){ .img-lupa }

#### Programación

Para leer el micrófono usamos el bloque `leer micrófono`:

![Bloque leer micrófono](../assets/images/Bloque_microfono.png "Bloque leer micrófono"){ .img-bloque }

Si marcas la casilla que hay junto al bloque, verás en el escenario el valor que mide en cada momento.

## 2. Programamos

Revisamos continuamente el valor del micrófono y, según el nivel de ruido, encendemos o apagamos cada uno de los tres LED.

![Bloques programación Vúmetro](../assets/images/Ejemplo_vumetro.png "Bloques programación Vúmetro")

**Cómo funciona**:

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

1. **Una lectura más estable:** Para que los LED no parpadeen, en lugar de usar cada lectura del micrófono calcula la **media** de varias (por ejemplo, de 10) y usa esa media en los condicionales. **Pista:** necesitas una variable que vaya sumando las lecturas (`suma`) y otra que las cuente (`numeroDatos`); la media es `suma / numeroDatos`. **Ayuda:** puedes encontrar la programación en **Archivo → Ejemplos → Vumetro_media_sonido**.
2. **Calibra tu aula:** Observa qué valores mide el micrófono con silencio, hablando en voz baja y dando una palmada, y ajusta los umbrales (20 y 50) para que el vúmetro funcione bien en tu clase.
3. **Vúmetro virtual en pantalla:** Diseña un vúmetro en la pantalla: crea un objeto en EchidnaML con cuatro disfraces (sin barras, una, dos y tres barras) y haz que cambie de disfraz al mismo tiempo que se encienden los LED de la placa.
