# AGENTS.md

Instrucciones para agentes de IA (Claude Code y similares) que trabajen en este repositorio.

## Qué es este proyecto

**Proyectos de inicio con EchidnaML**: proyectos sencillos con **EchidnaML** y
la placa **EchidnaBlack2**, publicados con [Zensical](https://zensical.org/) como
sitio estático y como PDF. Siguen la misma estrategia (configuración,
scripts y estilos) que el manual de Echidna
(<https://github.com/EchidnaEducacion/manual>); si cambias algo de la
maquetación, comprueba si conviene hacer lo mismo allí.

No es un proyecto de software: es contenido editorial dirigido a docentes y
alumnado que empiezan con la placa.

## Convenciones editoriales

- **Idioma**: español, registro cercano (tuteo al alumnado), términos clave
  en **negrita**.
- **Estructura fija de cada proyecto**: `# N.M Título`, imagen de cabecera,
  `## 1. Qué vamos a hacer`, `### 1.1 Qué vamos a aprender`,
  `### 1.2 Qué vamos a usar` (con `#### Componentes` y
  `#### Programación`), `## 2. Programamos` (con
  **Cómo funciona** cuando aplica) y `## 3. Mejóralo` (tres
  propuestas numeradas, de menos a más difícil). Mantén este patrón al
  añadir un proyecto.
- **Qué vamos a usar (1.2)**: dos subapartados. `#### Componentes`: lista
  de componentes (o frase con lo que se usa en los proyectos con IA),
  imagen de la lupa y avisos de montaje (por ejemplo, el selector MkMk o
  la alimentación de los servos). `#### Programación`: el bloque del
  componente (ver «Bloque del componente»).
- **Pista y Ayuda en «Mejóralo»**: **Pista:** da información sobre cómo
  hacerlo (un bloque, un valor, una idea) y **Ayuda:** da la solución
  (captura del programa o ejemplo de EchidnaML). Van en negrita al final de
  la propuesta, o en párrafo aparte tras la lista si incluyen imagen.
- **Estructura fija de cada proyecto con IA** (sección 3, LearningML): la
  misma, con un apartado nuevo tras el 1, que sigue las fases del manual:
  `## 1. Qué vamos a hacer` (con 1.1 y 1.2), `## 2. Entrenamos el modelo`
  (`### 2.1 Entrenar: clases y ejemplos`, `### 2.2 Aprender`,
  `### 2.3 Probar`, que incluye volver a entrenar si no clasifica bien),
  `## 3. Programamos` (con **Cómo funciona**, incluida la
  comprobación de confianza) y `## 4. Mejóralo`. En el 1.2, el bloque que se
  presenta es el de LearningML que introduce el proyecto. Cómo abrir
  LearningML y su entorno se explica una sola vez en `docs/03-ia/index.md`.
- **Bloque del componente**: en `#### Programación`, al final del 1.2, se
  presenta **un único bloque**, el del componente que introduce el proyecto
  (en Timbre, el zumbador y no los pulsadores): una frase con el nombre
  del bloque entre comillas invertidas, su imagen
  `![Bloque ...](../assets/images/Bloque_*.png "Bloque ..."){ .img-bloque }`
  y sus opciones o valores. Imagen y explicación salen del apartado
  «BLOQUE DE PROGRAMACIÓN» del manual. Todas las `Bloque_*.png` están
  recortadas y a la misma escala (la x del texto mide 12 px) para que
  `.img-bloque` las muestre con el texto del mismo tamaño; respeta esa
  escala al añadir una nueva.
- **Estructura por secciones**: `1. Introducción` (`docs/01-introduccion.md`),
  `2. Proyectos con EchidnaBlocks` (`docs/02-echidnablocks/`),
  `3. Proyectos con IA` (`docs/03-ia/`, proyectos con LearningML) y
  `4. Licencia` (`docs/04-licencia.md`). Cada sección con proyectos tiene un
  `index.md` (presentación y lista de proyectos) y los proyectos se numeran
  por sección (2.1, 2.2…, 3.1…). El número va en el `nav` y también en el
  `# Título` de la página (`# 2.1 Hola Mundo`, `# 3. Proyectos con IA`), para
  que el índice del PDF salga numerado; si reordenas, renumera ambos.
- **Navegación**: `nav` en `zensical.toml` es la fuente de verdad del orden.
  Si añades, eliminas o reordenas un proyecto, actualiza a la vez `nav`, la
  lista del `index.md` de su sección, la de `docs/index.md` y la del
  `README.md`. Los ficheros de proyecto se nombran `NN-nombre.md` dentro de
  la carpeta de su sección.
- **Enlaces**: los externos a la guía (incluidos el manual de Echidna y la
  guía de Arduino, que son otros sitios) se abren en otra pestaña:
  `[texto](https://...){ target="_blank" rel="noopener" }`. Los internos
  (rutas relativas a otros `.md` de la guía, y el PDF de la propia guía) no
  llevan atributos y se abren en la misma pestaña.
- **Sin emojis**: WeasyPrint no los coloca bien en el PDF (aparecen como un
  punto suelto en el margen superior). No los reintroduzcas.
- **Markdown estricto (Python-Markdown)**: las listas necesitan una línea en
  blanco antes y las listas anidadas 4 espacios de sangría; con 2 o 3
  espacios, o sin línea en blanco, GitHub las muestra bien pero la web y el
  PDF no.
- **Imágenes**: viven en `docs/assets/images/` (sin subcarpetas), siempre en
  local (no enlaces a GitHub), referenciadas con ruta relativa y el `title`
  repitiendo el `alt`:
  `![Descripción](../assets/images/Nombre.png "Descripción")` desde las
  carpetas de sección (`assets/images/...` sin `../` solo en las páginas de
  `docs/`). Ancho explícito
  opcional con `{ width="N" }`. En el PDF, `print.css` limita la altura de
  las imágenes a 95 mm. Están disponibles las clases `.img-row` e
  `.img-text-row` (ver `extra.css`/`print.css`) para poner imágenes en fila.
  Las imágenes de detalle con lupa (`Lupa_*.png`) llevan `{ .img-lupa }`
  para que todas tengan el mismo tamaño reducido (26rem en la web, 100 mm en
  el PDF), y la imagen de cabecera de cada proyecto lleva `{ .img-cabecera }`
  (18rem en la web, 80 mm en el PDF). En el PDF `{ width="N" }` no tiene
  efecto porque `print.css` fija `width: auto`. Los GIF del proceso de
  programación llevan `{ .solo-web }`: se ven en la web y se ocultan en el
  PDF (allí solo saldría el primer fotograma y ya está la captura del
  programa). Captura y GIF van en pestañas (`pymdownx.tabbed`):
  `=== "Programa"` con la captura y `=== "Paso a paso"` con el GIF, con el
  contenido sangrado 4 espacios; en el PDF las pestañas no se ven y solo
  sale la captura.
- **Pseudocódigo** (`SI ... / SI NO ...` y `-->`): siempre en bloque de
  código con ``` ``` ```, 4 espacios por nivel.
- Los marcadores provisionales en mayúsculas (`IMAGEN LUPA ...`,
  `--> GIF ...`, `VIDEO ...`) son contenido pendiente del autor: no los
  elimines ni los inventes.

## Estructura del repositorio

- `zensical.toml`: configuración del sitio y navegación (`nav`).
- `docs/`: contenido Markdown (`index.md` es la página de inicio web y no
  entra en el PDF).
- `docs/assets/images/`, `docs/assets/fonts/` (Exo y Open Sans para el PDF),
  `docs/assets/stylesheets/extra.css` (identidad visual de la web).
- `scripts/guia_nav.py`: recorrido común del `nav`.
- `slides/` (diapositivas Marp, tema `slides/tema-echidna.css`) y
  `package.json` (marp-cli para exportarlas).
- `scripts/build_pdf.py` + `scripts/print.css`: generan
  `site/proyectos-inicio-echidnaml.pdf` uniendo todas las páginas ya construidas
  en un único documento (portada maquetada en HTML, índice con página real
  de secciones y proyectos, un salto de página por sección y por proyecto).
  Requiere `zensical build --clean` previo.
- `.github/workflows/docs.yml`: publicación en GitHub Pages (web + PDF) al
  hacer push a `main`. `.gitlab-ci.yml`: GitLab Pages (sin PDF).

## Al empezar a trabajar

Antes de tocar nada, comprueba si alguien del equipo ha subido cambios:

1. `git status`: si hay cambios locales sin confirmar, avisa antes de
   seguir (no hagas `stash` ni descartes nada por tu cuenta).
2. `git fetch --prune` y `git log --oneline HEAD..@{u}` para ver qué hay
   nuevo en `main`.
3. Si hay commits nuevos, `git pull --rebase`; si da conflictos, detente y
   consúltalo.
4. Resume en pocas líneas qué ha llegado a `main` (commits y ficheros).
   Las demás ramas no hace falta revisarlas.

Antes de hacer `push`, repite `git pull --rebase` por si ha llegado algo
durante la sesión.

## Cómo comprobar los cambios

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
zensical build --clean
python scripts/build_pdf.py
```

Revisa la web (`zensical serve`) y el PDF: imágenes visibles, listas bien
formadas y posición correcta en la navegación.

Las diapositivas para el docente (`slides/`, Marp) se ven en VS Code con la
extensión Marp for VS Code (recomendada en `.vscode/`). Para exportarlas a PDF
hace falta Node.js (LTS) y un Chrome o Chromium; `CHROME_PATH` indica cuál usar
(el Chromium de snap falla si está abierto, mejor un `chrome-headless-shell`
instalado con `npx @puppeteer/browsers install chrome-headless-shell@stable`):

```bash
npm ci
npm run slides:pdf   # genera site-slides/<sección>/<proyecto>.pdf
```

## Licencia

Contenido bajo
[Creative Commons Reconocimiento-CompartirIgual 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
Cualquier contenido nuevo debe ser compatible con esta licencia.
