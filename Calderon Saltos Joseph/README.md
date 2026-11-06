
<div align="center">

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/latex/latex-original.svg" width="175" alt="Logo de LaTeX">

# FORM-FB-01 — Fichas bibliográficas

**APLICACIONES DISTRIBUIDAS**

Universidad Técnica Estatal de Quevedo

**Calderón Saltos Joseph Alexander**

Ingeniería en Software · Sistemas Distribuidos

</div>

---

## Descripción

Este trabajo reúne cinco fichas bibliográficas relacionadas con los sistemas distribuidos, el algoritmo de consenso Raft y la tolerancia a fallos.

Las fuentes se utilizarán como base para el próximo informe académico individual (TA-IND-01). Cada ficha contiene una referencia IEEE, un DOI verificado, un resumen, un dato concreto con su ubicación y una nota personal.

## Archivos del proyecto

| Archivo | Descripción |
|---|---|
| `main.tex` | Documento LaTeX con las cinco fichas bibliográficas. |
| `referencias.bib` | Referencias académicas utilizadas por BibLaTeX. |
| `fichas.pdf` | PDF compilado del documento. |
| `README.md` | Información del proyecto e instrucciones de compilación. |

## Requisitos

Para compilar el documento se necesita una distribución LaTeX, como **TeX Live** o **MiKTeX**, que incluya:

- **pdfLaTeX:** compilador del documento.
- **Biber:** procesador de bibliografía.
- **BibLaTeX:** gestión de referencias con estilo IEEE (`biblatex-ieee`).

El proyecto utiliza los paquetes `babel` (español), `inputenc`, `fontenc`, `newtxtext`, `newtxmath`, `geometry`, `microtype`, `setspace`, `fancyhdr`, `hyperref`, `csquotes` y `biblatex`.

Biber y BibLaTeX deben tener versiones compatibles.

## Compilación

Desde una terminal, ubícate en la carpeta que contiene `main.tex` y `referencias.bib`.

Ejecuta los siguientes comandos en orden:

```bash
pdflatex -interaction=nonstopmode -halt-on-error main.tex
biber main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

**Resultado:** se genera `main.pdf`, con las cinco fichas bibliográficas distribuidas en cinco páginas.

El archivo `fichas.pdf` incluido en el repositorio corresponde a una copia del documento compilado.

## Notas de compilación

La primera ejecución de pdfLaTeX puede mostrar advertencias sobre referencias pendientes. Estas se resuelven al ejecutar Biber y las dos compilaciones posteriores.

Según la versión de `biblatex-ieee`, puede aparecer un aviso relacionado con la traducción de `artno`, utilizado para identificar el número de artículo.

Para reproducir el documento no se necesitan archivos auxiliares previos. Basta con los archivos fuente y las dependencias indicadas.

---

<div align="center">

**FORM-FB-01 · aplicaciones distribuidas**

Universidad Técnica Estatal de Quevedo

</div>
