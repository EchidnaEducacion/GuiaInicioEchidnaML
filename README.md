# Proyectos de inicio con EchidnaML — proyecto Zensical

Proyectos sencillos para iniciarse con EchidnaML y la placa EchidnaBlack2.
Se publican como sitio web estático con
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

### Diapositivas para el docente (en preparación)

Una presentación por proyecto en `slides/`, escrita con
[Marp](https://marp.app/). De momento, piloto de
[2.1 Hola Mundo](slides/02-echidnablocks/01-hola-mundo.md).

## Requisitos

- Python 3.10 o superior (en 3.10 se instala además `tomli`, ya incluido en
  `requirements.txt`)
- `pip`
- Solo para exportar las diapositivas desde la terminal: Node.js (versión
  LTS) y Chrome o Chromium (ver [Diapositivas](#diapositivas))

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
empezar cada proyecto. Genera `site/proyectos-inicio-echidnaml.pdf`.

En Debian/Ubuntu, WeasyPrint necesita estas bibliotecas del sistema y, si
`pip` no encuentra una rueda precompilada de `lxml` para tu Python, hacen
falta además las cabeceras de desarrollo de `libxml2`/`libxslt`:

```bash
sudo apt install libpango-1.0-0 libpangoft2-1.0-0 libharfbuzz-subset0 libxml2-dev libxslt1-dev
```

El flujo de GitHub Actions instala estas dependencias y genera el PDF en
cada publicación, por lo que queda disponible en
`<sitio>/proyectos-inicio-echidnaml.pdf` (enlazado desde la página de inicio).

## Diapositivas

Cada proyecto tendrá una presentación para el docente en Markdown
(`slides/<sección>/NN-nombre.md`), con el tema `slides/tema-echidna.css`.
Sigue las fases del proyecto: portada, `1. Qué vamos a hacer`,
`2. Programamos`, `3. Mejóralo` (un reto por diapositiva, con su Pista y
otra diapositiva de Ayuda), `4. Evaluación`, `5. Licencia` y cierre.
Las imágenes se toman de `docs/assets` a través del enlace simbólico
`slides/assets`, así que se referencian igual que en los proyectos. Las notas
del docente van en comentarios `<!-- ... -->` y se ven en el modo
presentador.

### Ver y exportar con VS Code

1. Instala la extensión **Marp for VS Code** (`marp-team.marp-vscode`).
   VS Code la propone al abrir la carpeta del repositorio; también se
   instala con `code --install-extension marp-team.marp-vscode`.
2. Abre la presentación y pulsa **Open Preview to the Side**.
3. Para exportar, usa el comando **Marp: Export Slide Deck…** (PDF, PPTX,
   HTML o imágenes). Para PDF usa el Chrome o Chromium del sistema; si falla,
   genera el PDF desde la terminal (ver abajo).

El tema y el HTML ya están activados en `.vscode/settings.json`.

### Generar desde la terminal

Requiere Node.js (versión LTS; en Linux, por ejemplo, con
[nvm](https://github.com/nvm-sh/nvm)) y Chrome o Chromium. La primera vez,
instala marp-cli (queda en `node_modules/`, que no se sube):

```bash
npm ci
```

Después, para generar el PDF de todas las presentaciones:

```bash
npm run slides:pdf
```

Los PDF se guardan en `site-slides/<sección>/NN-nombre.pdf` (tampoco se
sube).

Si Chrome o Chromium no se encuentra, o la exportación falla o se queda
colgada (pasa con el Chromium de snap de Ubuntu cuando está abierto), usa un
Chrome sin interfaz solo para esto e indícalo en `CHROME_PATH`:

```bash
npx @puppeteer/browsers install chrome-headless-shell@stable --path ~/.cache/chrome-marp
export CHROME_PATH=~/.cache/chrome-marp/chrome-headless-shell/<versión>/chrome-headless-shell-linux64/chrome-headless-shell
```

(la primera orden muestra la ruta exacta; añade el `export` a tu
`~/.bashrc` para no repetirlo).

En Windows, `slides/assets` solo funciona si Git crea enlaces simbólicos; si
no, las imágenes no se verán. Clona con `git clone -c core.symlinks=true ...`
o usa WSL. `npm run slides:pdf` también necesita una terminal tipo Unix
(WSL o Git Bash).

Las diapositivas aún no se publican en la web; se añadirán al flujo de
GitHub Actions cuando la plantilla esté cerrada.

## Licencia

Contenido bajo licencia
[Creative Commons Reconocimiento-CompartirIgual 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
