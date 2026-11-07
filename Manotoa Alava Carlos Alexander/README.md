# Fichas Bibliográficas - Fundamentos de Sistemas Distribuidos (TA-IND-01)

Este repositorio contiene el código fuente en LaTeX y el PDF compilado de las 5 fichas bibliográficas

## Contenido del repositorio
- `fichas.tex`: Archivo principal en LaTeX con el contenido de las fichas.
- `referencias.bib`: Base de datos bibliográfica en formato BibTeX.
- `fichas.pdf`: Documento PDF compilado y listo para revisión.
- `README.md`: Este archivo con las instrucciones.

## Instrucciones de compilación

Para generar el documento PDF a partir del código fuente, siga estos pasos:

### 1. Compilador y Herramientas
- **Compilador:** `pdflatex` (TeX Live 2026 / pdfTeX 3.141592653-2.6-1.40.29).
- **Gestor de bibliografía:** `biber` (versión 2.22).
- **Archivo principal:** `fichas.tex`.

### 2. Orden de comandos
Abra una terminal en la raíz del repositorio y ejecute los siguientes comandos en el orden indicado (es necesario ejecutar `pdflatex` tres veces para que las referencias y los enlaces se muestren correctamente):

1. pdflatex fichas.tex
2. biber fichas
3. pdflatex fichas.tex
4. pdflatex fichas.tex