# Guía de inicio EchidnaML — proyecto Zensical

Guía para iniciarse con EchidnaML y la placa EchidnaBlack2 basada en
proyectos sencillos. Se publica como sitio web estático con
[Zensical](https://zensical.org/) y como PDF maquetado con
[WeasyPrint](https://weasyprint.org/), con la misma estrategia que el
[manual de EchidnaBlack y EchidnaML](https://github.com/EchidnaEducacion/manual).

## Proyectos

1. [Hola Mundo](docs/01-hola-mundo.md)
2. [Semáforo](docs/02-semaforo.md)
3. [Zumbador](docs/03-zumbador.md)
4. [Pulsadores](docs/04-pulsadores.md)
5. [Interruptor crepuscular](docs/05-interruptor-crepuscular.md)
6. [Makey Makey](docs/06-makey-makey.md)

Todos siguen la misma estructura: `1. Qué vamos a hacer` (con
`1.1 Qué vamos a aprender` y `1.2 Qué componentes vamos a usar`),
`2. Programación` y `3. Mejóralo`.

## Requisitos

- Python 3
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
