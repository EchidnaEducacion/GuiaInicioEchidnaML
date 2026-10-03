# Guía de inicio EchidnaML — proyecto Zensical

Guía para iniciarse con EchidnaML y la placa EchidnaBlack2 basada en
proyectos sencillos. Se publica como sitio web estático con
[Zensical](https://zensical.org/) y como PDF maquetado con
[WeasyPrint](https://weasyprint.org/), con la misma estrategia que el
[manual de EchidnaBlack y EchidnaML](https://github.com/EchidnaEducacion/manual).

## Estructura

### 1. Introducción

[Introducción](docs/01-introduccion.md): EchidnaBlack2, EchidnaML y el entorno EchidnaBlocks.

### 2. Proyectos con EchidnaBlocks

[Presentación de la sección](docs/02-echidnablocks/index.md).

1. [Hola Mundo](docs/02-echidnablocks/01-hola-mundo.md)
2. [Semáforo](docs/02-echidnablocks/02-semaforo.md)
3. [Interruptor de luz](docs/02-echidnablocks/03-interruptor-de-luz.md)
4. [Timbre](docs/02-echidnablocks/04-timbre.md)
5. [Interruptor crepuscular](docs/02-echidnablocks/05-interruptor-crepuscular.md)
6. [Piano de frutas](docs/02-echidnablocks/06-piano-de-frutas.md)
7. [El echidna dice la temperatura](docs/02-echidnablocks/07-echidna-dice-temperatura.md)
8. [Termómetro de colores](docs/02-echidnablocks/08-termometro-de-colores.md)
9. [Vúmetro](docs/02-echidnablocks/09-vumetro.md)
10. [Telesketch](docs/02-echidnablocks/10-telesketch.md)
11. [Movemos el echidna](docs/02-echidnablocks/11-movemos-el-echidna.md)

### 3. Proyectos con IA

[Presentación de la sección](docs/03-ia/index.md): proyectos con LearningML.

1. [Asistente virtual](docs/03-ia/01-asistente-virtual.md)
2. [Clasificador de residuos](docs/03-ia/02-clasificador-residuos.md)
3. [Mando de inclinación](docs/03-ia/03-mando-inclinacion.md)

### 4. Licencia

[Licencia](docs/04-licencia.md).

Todos los proyectos siguen la misma estructura: `1. Qué vamos a hacer` (con
`1.1 Qué vamos a aprender` y `1.2 Qué vamos a usar`),
`2. Programamos` y `3. Mejóralo`.

## Requisitos

- Python 3.11 o superior
- `pip`

## Vista previa local

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
zensical serve
```

En Windows, active el entorno con `.venv\Scripts\activate`.
La terminal mostrará la dirección local de la vista previa.

## Generar el sitio estático

```bash
zensical build --clean
```

El sitio resultante se guarda en `site/`. Puede publicarse con cualquier
servidor web estático.

## Generar el PDF

```bash
python scripts/build_pdf.py
```

Requiere haber ejecutado antes `zensical build --clean`. El script une el
contenido de todas las páginas (en el orden del `nav` de `zensical.toml`) en
un único documento y lo maqueta con WeasyPrint usando `scripts/print.css`:
portada, índice con numeración de página real y un salto de página al
empezar cada proyecto. Genera `site/guia-inicio-echidnaml.pdf`.

En Debian/Ubuntu, WeasyPrint necesita estas bibliotecas del sistema y, si
`pip` no encuentra una rueda precompilada de `lxml` para tu Python, hacen
falta además las cabeceras de desarrollo de `libxml2`/`libxslt`:

```bash
sudo apt install libpango-1.0-0 libpangoft2-1.0-0 libharfbuzz-subset0 libxml2-dev libxslt1-dev
```

El flujo de GitHub Actions instala estas dependencias y genera el PDF en
cada publicación, por lo que queda disponible en
`<sitio>/guia-inicio-echidnaml.pdf` (enlazado desde la página de inicio).

## Licencia

Contenido bajo licencia
[Creative Commons Reconocimiento-CompartirIgual 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
