# FORM-FB-01 — Fichas Bibliográficas — Fundamentos de SD y Arquitecturas Distribuidas

**Asignatura:** Aplicaciones Distribuidas
**Autora:** Belinda Betzabeth Toaquiza Zambrano

Este repositorio contiene cinco fichas bibliográficas sobre arquitecturas de microservicios y sistemas distribuidos (fuentes de 2021 a 2026): el documento LaTeX, el archivo de referencias en BibTeX y el PDF compilado.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `main.tex` | Documento principal (archivo que se compila) |
| `referencias.bib` | Referencias en BibTeX, usadas por `biblatex` |
| `FORM_FB_01___Fichas_Bibliográficas___Fundamentos_de_SD_y_Arquitecturas_Distribuidas.pdf` | PDF compilado a partir de `main.tex` |
| `README.md` | Este archivo |

## Requisitos

- **Compilador:** `pdfLaTeX`.
- **Procesador de bibliografía:** `biber` (**no** `bibtex`; el documento usa `biblatex` con `backend=biber`).
- **Dónde compilar:** Overleaf (en línea, sin instalar nada) o TeXstudio con una distribución de LaTeX (TeX Live o MiKTeX).
- **Paquetes de LaTeX:**
  `inputenc`, `fontenc`, `lmodern`, `babel` (con soporte para español), `microtype`, `csquotes`, `geometry`, `fancyhdr`, `xcolor`, `tcolorbox` (con la biblioteca `most`), `biblatex` (con el estilo `ieee`) e `hyperref`.

Overleaf ya incluye todos los paquetes. En TeXstudio, una instalación completa de TeX Live (por ejemplo `texlive-full`) también los trae, y MiKTeX los instala automáticamente la primera vez que se compila.

## Archivos de entrada

- **Archivo principal:** `main.tex`
- **Archivo de referencias:** `referencias.bib`

El `.bib` no se importa a mano: `main.tex` lo carga con la línea `\addbibresource{referencias.bib}` y las referencias salen con `\fullcite{...}` y `\printbibliography`. Solo hace falta que `main.tex` y `referencias.bib` estén en la **misma carpeta** y que el nombre del `.bib` coincida con el de esa línea. Si lo renombras, cámbialo también en `main.tex`.

## Orden de compilación

Estos son los pasos que debe ejecutar el compilador, en este orden:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

1. La primera pasada de `pdflatex` genera los archivos auxiliares con las citas.
2. `biber` procesa `referencias.bib`. Se escribe el nombre **sin** extensión.
3. Las dos pasadas finales de `pdflatex` resuelven las referencias y la numeración.

El resultado es `main.pdf`, que corresponde al PDF incluido en el repositorio (con otro nombre). Overleaf y TeXstudio ejecutan estos pasos desde sus menús, como se explica a continuación.

## Opción A: Overleaf

1. En Overleaf, crea un proyecto nuevo con **New Project → Upload Project** (subiendo los archivos del repositorio en un `.zip`) o sube `main.tex` y `referencias.bib` a un proyecto vacío.
2. Abre **Menu** (arriba a la izquierda) y en **Settings** elige:
   - **Compiler:** `pdfLaTeX`.
   - **Main document:** `main.tex`.
3. Pulsa **Recompile**. Overleaf ejecuta `pdflatex` y `biber` las veces necesarias de forma automática.
4. Descarga el PDF con el botón **Download PDF**.

## Opción B: TeXstudio

1. Abre `main.tex` en TeXstudio (**Archivo → Abrir**). Deja `referencias.bib` en la misma carpeta.
2. Comprueba la configuración en **Opciones → Configurar TeXstudio → Compilar**:
   - **Compilador predeterminado:** `PdfLaTeX`.
   - **Herramienta de bibliografía predeterminada:** `Biber`.
3. Compila siguiendo el orden de la sección anterior, con el menú **Herramientas** o con los atajos de teclado:
   1. **Compilar** (`F6`)
   2. **Bibliografía** (`F8`)
   3. **Compilar** (`F6`)
   4. **Compilar** (`F6`)
4. Abre el PDF resultante con **Ver** (`F7`). También puedes usar **Compilar y ver** (`F5`), pero la primera vez conviene hacer los cuatro pasos manualmente para asegurarte de que las referencias se resuelvan.

## Problemas frecuentes

- **Las referencias salen como `[?]` o la bibliografía está vacía:** no se ejecutó `biber`, o se ejecutó `bibtex` en su lugar. En TeXstudio, revisa que la herramienta de bibliografía predeterminada sea `Biber` y repite la secuencia. En Overleaf, usa **Recompile from scratch** (desde el menú desplegable junto al botón **Recompile**).
- **Overleaf no encuentra `referencias.bib`:** el archivo debe estar en el mismo proyecto y carpeta que `main.tex`, con el nombre exacto.
- **Error de versión entre `biblatex` y `biber`** (mensaje del tipo *"Found biblatex control file version X, expected version Y"*): las versiones de `biblatex` y `biber` no coinciden. En TeXstudio, actualiza ambos desde tu distribución de TeX. En Overleaf, prueba con otra versión de TeX Live en **Menu → Settings**.
- **Resultados viejos tras cambiar el `.bib`:** en TeXstudio, usa **Herramientas → Limpiar archivos auxiliares** y vuelve a compilar. En Overleaf, usa **Recompile from scratch**.
