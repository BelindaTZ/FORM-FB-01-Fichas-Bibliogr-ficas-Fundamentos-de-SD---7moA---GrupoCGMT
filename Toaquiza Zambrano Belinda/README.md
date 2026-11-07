# FORM-FB-01 — Fichas Bibliográficas — Fundamentos de SD y Arquitecturas Distribuidas
 
**Asignatura:** Aplicaciones Distribuidas
**Autora:** Belinda Betzabeth Toaquiza Zambrano
 
Instrucciones para compilar el documento desde la terminal (PowerShell), **Overleaf**, **TeXstudio** o **VS Code**.
 
## 1. Compilador
 
- **Compilador:** `pdfLaTeX`.
- **Procesador de bibliografía:** `biber` (no `bibtex`).
Dónde se configura en cada herramienta:
 
- **Terminal (PowerShell):** se usan directamente los comandos `pdflatex` y `biber`.
- **Overleaf:** `Menu` → `Settings` → `Compiler` → `pdfLaTeX`.
- **TeXstudio:** `Opciones` → `Configurar TeXstudio` → `Compilar`; compilador predeterminado `PdfLaTeX` y herramienta de bibliografía predeterminada `Biber`.
- **VS Code:** extensión `LaTeX Workshop` con la receta `latexmk`, que usa `pdflatex` y `biber`.
## 2. Archivo principal
 
`main.tex`
 
Carga las referencias de `referencias.bib` con `\addbibresource{referencias.bib}`. Ambos archivos deben estar en la misma carpeta.
 
## 3. Orden de comandos
 
```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```
 
| Comando | Qué hace |
|---|---|
| `pdflatex main.tex` | Compila el documento y registra las citas (las referencias aún salen como `[?]`). |
| `biber main` | Lee `referencias.bib` y prepara las referencias en formato IEEE. El nombre va sin `.tex`. |
| `pdflatex main.tex` | Vuelve a compilar e inserta las referencias preparadas por `biber`. |
| `pdflatex main.tex` | Ajusta la numeración y las referencias cruzadas; genera el PDF final. |
 
El resultado es `main.pdf`.
 
### Con la terminal (PowerShell)
 
Abre PowerShell en la carpeta del repositorio (clic derecho → `Abrir en Terminal`, o `cd` con la ruta de la carpeta) y comprueba con `pdflatex --version` que LaTeX esté instalado. Ejecuta los cuatro comandos en orden: se genera `main.pdf` en la misma carpeta, junto con archivos auxiliares (`.aux`, `.log`, `.bbl`, etc.) que se pueden ignorar. Si PowerShell no reconoce `pdflatex`, falta instalar una distribución de LaTeX (ver Dependencias).
 
### Con Overleaf
 
Crea un proyecto con `New Project` → `Upload Project` y sube el `.zip` del repositorio. En `Menu` → `Settings`, elige `Compiler`: `pdfLaTeX` y `Main document`: `main.tex`. Pulsa `Recompile`: Overleaf ejecuta la secuencia de comandos automáticamente. Descarga el resultado con `Download PDF`.
 
### Con TeXstudio
 
Abre `main.tex` desde la carpeta del repositorio y ejecuta, en orden, `F6` (Compilar), `F8` (Bibliografía), `F6` y `F6`; abre el PDF con `F7` (Ver). Antes, comprueba que la herramienta de bibliografía predeterminada sea `Biber` (no `BibTeX`).
 
### Con VS Code
 
Abre la carpeta del repositorio (`File` → `Open Folder`), abre `main.tex` y pulsa `Ctrl+Alt+B` (`Build LaTeX project`): la receta `latexmk` ejecuta la secuencia completa automáticamente. Abre el PDF con `Ctrl+Alt+V` (`View LaTeX PDF`). Requiere la extensión `LaTeX Workshop` y una distribución de LaTeX instalada.
 
## 4. Dependencias
 
- **Procesador de bibliografía:** `biber`.
- **Paquetes de LaTeX:** `inputenc`, `fontenc`, `lmodern`, `babel` (spanish), `microtype`, `csquotes`, `geometry`, `fancyhdr`, `xcolor`, `tcolorbox` (con `most`), `biblatex` (con `style=ieee`) e `hyperref`.
- **Distribución de LaTeX:** TeX Live o MiKTeX, necesaria para compilar con PowerShell, TeXstudio y VS Code. Una instalación completa ya incluye `biber` y todos los paquetes (MiKTeX los instala automáticamente la primera vez que se compila).
- **VS Code:** además, la extensión `LaTeX Workshop`.
- **Overleaf:** no requiere instalar nada; ya incluye todos los paquetes.
