# Fichas bibliográficas — Sistemas Distribuidos

Este proyecto contiene las **fichas bibliográficas** correspondientes a la asignatura de **Sistemas Distribuidos**, elaboradas para la Carrera de Ingeniería en Software de la Universidad Técnica Estatal de Quevedo.

El documento incluye cinco fichas de fuentes académicas sobre sistemas distribuidos y arquitecturas de microservicios. Cada ficha contiene:

- Título de la fuente.
- Referencia en formato IEEE con DOI.
- Resumen de aproximadamente 100 palabras.
- Dato concreto de la fuente.
- Nota personal como aporte al informe.

## Estructura del proyecto

```text
.
├── main.tex
└── README.md
```

El archivo principal del proyecto es:

```text
main.tex
```

## Requisitos previos

Para compilar el documento se requiere una distribución de LaTeX que incluya:

- `pdflatex`
- `biber` o `bibtex`, solo si se utilizan referencias externas mediante BibLaTeX o BibTeX
- Paquetes de LaTeX estándar:
  - `inputenc`
  - `fontenc`
  - `babel`
  - `geometry`
  - `enumitem`
  - `hyperref`

En Overleaf no es necesario instalar manualmente los paquetes, ya que la plataforma incluye una distribución de LaTeX con las dependencias requeridas.

## Compilación en Overleaf

1. Ingresar a [Overleaf](https://www.overleaf.com/).
2. Crear un nuevo proyecto o subir los archivos del proyecto.
3. Asegurarse de que el archivo principal sea `main.tex`.
4. En el menú de configuración, seleccionar el compilador **pdfLaTeX**.
5. Presionar el botón **Recompile** para generar el PDF.

### Configuración recomendada en Overleaf

| Opción | Valor recomendado |
|---|---|
| Compiler | pdfLaTeX |
| Main document | `main.tex` |
| TeX Live version | Cualquier versión reciente |
| Output format | PDF |

## Compilación local

Si se desea compilar el documento en un equipo local, se puede utilizar una distribución de LaTeX como:

- TeX Live
- MiKTeX
- MacTeX

### Comandos de compilación

Desde la carpeta del proyecto, ejecutar:

```bash
pdflatex main.tex
pdflatex main.tex
```

El primer comando genera el archivo PDF inicial y el segundo actualiza referencias cruzadas, índices y enlaces internos.

Si el documento utiliza bibliografía externa mediante BibLaTeX, ejecutar:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Si el documento utiliza BibTeX, ejecutar:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Archivos generados

Tras la compilación se generan los siguientes archivos:

| Archivo | Descripción |
|---|---|
| `main.pdf` | Documento final en formato PDF |
| `main.aux` | Información auxiliar de referencias y estructura |
| `main.log` | Registro de compilación y mensajes de error |
| `main.out` | Información de hipervínculos y marcadores |
| `main.bbl` | Bibliografía generada, si se utiliza BibTeX |
| `main.bcf` | Información de BibLaTeX, si se utiliza BibLaTeX |

## Notas importantes

- El compilador recomendado es **pdfLaTeX**.
- El archivo principal es **`main.tex`**.
- No es necesario ejecutar BibTeX o Biber si el documento no incluye un archivo `.bib` ni comandos de citación como `\cite{}`.
- Si se añade un archivo `.bib`, se debe compilar primero con `pdflatex`, luego ejecutar `biber` o `bibtex` según el caso, y finalmente compilar dos veces con `pdflatex`.
- En caso de error de compilación, revisar el archivo `main.log`, que contiene información detallada sobre el problema detectado.

## Autor

**Giraldo Cagua Diego José**  
Carrera de Ingeniería en Software  
Universidad Técnica Estatal de Quevedo  
Facultad de Ciencias de la Computación y Diseño Digital  
Asignatura: Sistemas Distribuidos  
Documento: FORM-FB-01 — Fichas bibliográficas
