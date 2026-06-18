# Compendio de Actas de Reunión - Trazabilidad y Gobernanza del Proyecto

## Logo
![Logo Byte Busters](assets/img/bytebusters/logo_horizontal.png)

## Insignias
[![LaTeX](https://img.shields.io/badge/LaTeX-Project-008080.svg?style=flat&logo=latex&logoColor=white)](https://www.latex-project.org/)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![Methodology: SCRUM](https://img.shields.io/badge/Methodology-SCRUM-orange)](https://scrumguides.org/)

## Perfil de Github - Introducción
Este repositorio proporciona una infraestructura documental en **LaTeX** diseñada para compilar y mantener el **registro cronológico de las Actas de Reunión** sostenidas por la grupo-empresa **Byte Busters S.R.L.** durante el desarrollo del proyecto. Cada acta constituye la evidencia formal de la trazabilidad y gobernanza del proyecto, en el marco de la Facultad de Ciencias y Tecnología de la UMSS.

## Características
* **Trazabilidad Formal:** Documenta para cada sesión la fecha, modalidad, asistentes, orden del día, desarrollo de las ceremonias ágiles y los acuerdos alcanzados.
* **Identidad Visual Corporativa:** Tipografías y colores institucionales de Byte Busters S.R.L. preconfigurados para una presentación uniforme.
* **Diseño de Layout:** Documento a doble cara (`twoside`) con interlineado optimizado para la lectura e impresión de un compendio extenso de actas.
* **Componentes Especializados:** Macros visuales para bloques informativos (`infoBox`), marcado semántico de componentes y bloques de firma de los socios fundadores.
* **Gestión de Compilación:** Redirección automática de archivos auxiliares a la carpeta `/build` para mantener el directorio limpio.

## Tecnología
* **Lenguaje de Marcado:** LaTeX.
* **Motor de Compilación:** `pdflatex` con soporte interactivo.
* **Automatización:** `latexmk` para gestión de dependencias y `Makefile` para atajos de terminal.
* **Editor Sugerido:** Visual Studio Code con extensión *LaTeX Workshop*.

## Perfil de Github - Habilidades
* **Documentación de Gobernanza:** Registro de actas y acuerdos de proyecto.
* **Gestión Ágil:** Documentación de ceremonias SCRUM (Sprint Planning, Daily, Review, Retrospective).
* **Typesetting:** LaTeX.
* **Project Management:** Estructura documental organizada para Taller de Ingeniería de Software (TIS).

## Instalación
Para utilizar este repositorio localmente, clónalo y asegúrate de tener una distribución de LaTeX instalada (TeX Live o MiKTeX):

```bash
git clone [https://github.com/dpardo23/documentacion-actas.git](https://github.com/dpardo23/documentacion-actas.git)
cd documentacion-actas
```

## Corre Localmente
Utiliza el `Makefile` o `latexmk` incluido para gestionar el ciclo de vida del documento:

```bash
# Compilar el compendio de actas completo
latexmk -pdf -outdir=build main.tex

# Limpiar archivos temporales y la carpeta build
make clean
```

## Ejecutando Pruebas
Para validar que el entorno está correctamente configurado y que el documento compila sin errores, ejecute:
1. `make clean`
2. `make all`
3. Verifique la existencia del PDF en `build/main.pdf`.

## Uso/Ejemplos
Cada acta reside en su propio archivo dentro de `/sections` y se incorpora al documento maestro mediante `\include`. La estructura de una sección de acta sigue este patrón:

```latex
\newpage
\section{Acta Número 01}
\label{sec:acta01}

\noindent \textbf{Fecha de la sesión:}\par
Lunes, 02 de marzo de 2026

\noindent \textbf{Datos de la Sesión}
\begin{itemize}[noitemsep]
    \item \textbf{Modalidad:} Virtual - Google Meet.
    \item \textbf{Hora de Inicio:} 18:00
    \item \textbf{Hora de Fin:} 20:00
\end{itemize}

% ... Orden del Día, Asistentes, Desarrollo del Acta y Firmas
\espacioFirma{ruta/firma.png}{Pardo Pozo Juan Diego}{0000000}
```

Para añadir una nueva acta, cree el archivo en `/sections` con la numeración correlativa y regístrelo en `main.tex` con `\include{sections/30_acta_...}`.

## Variables de Entorno
La configuración del flujo de trabajo se define en `.latexmkrc`:
* `$out_dir = 'build'`: Todos los binarios y archivos temporales se guardan aquí.
* `$pdf_mode = 1`: Fuerza la generación de salida en formato PDF.

## Capturas de Pantalla
El diseño final respeta los siguientes estándares de identidad corporativa y trazabilidad:
* **Portada Institucional:** Datos de la grupo-empresa Byte Busters S.R.L. y del proyecto.
* **Tabla de Contenidos:** Índice navegable de todas las actas registradas.
* **Bloques de Firma:** Espacios de firma con imagen, nombre y C.I. de los socios fundadores como evidencia de aprobación.

## Documentación
El documento maestro (`main.tex`) está organizado de la siguiente manera:
* **Portada:** Identificación del compendio y de la grupo-empresa.
* **Tabla de Contenidos:** Acceso directo a cada acta.
* **Actas de Reunión del Proyecto:** Capítulo único que recopila el registro cronológico de todas las actas, cada una con su fecha, modalidad, asistentes, orden del día, desarrollo y firmas de aprobación.

## Hoja de Ruta
* [ ] Plantilla automatizada para la generación de nuevas actas a partir de un formato base.
* [ ] Integración de un índice de acuerdos para rastrear el cumplimiento de tareas entre sesiones.
* [ ] Anexo de evidencias (capturas de ceremonias y tableros ágiles) por sesión.

## Optimizaciones
* **Resumen de Capítulo:** Uso de la macro `\resumenCapitulo` para contextualizar el contenido del compendio.
* **SyncTeX:** Habilitado para navegación bidireccional entre el código fuente y el PDF generado.
* **Modularidad:** Cada acta es un archivo independiente, facilitando la edición colaborativa sin conflictos.

## Relacionado
* Manual Técnico de Byte Busters S.R.L.
* Documentación de la Convocatoria Pública CPTIS-2302-2026.

## FAQ

**¿Cómo agrego una nueva acta al compendio?**
Cree un nuevo archivo en `/sections` siguiendo la numeración correlativa (ej. `30_acta_15-06-26.tex`) y añádalo en `main.tex` con `\include{...}` al final de la lista de actas.

**¿Cómo cambio el nombre del PDF de salida?**
Modifique la variable `DOCNAME` en el archivo `Makefile`.

## Lecciones
Durante el desarrollo de este compendio se priorizó la separación de intereses, manteniendo toda la lógica de diseño y macros en la carpeta `/config`, de modo que cada redactor solo deba concentrarse en documentar el contenido de las actas en `/sections`.

## Autores
* **Razón Social:** Byte Busters S.R.L.
* **Representante Legal:** Juan Diego Pardo Pozo
* **Consultor TIS:** Corina Justina Flores Villarroel

## Feedback y Apoyo
Para reportar errores o solicitar soporte, escriba a: contacto.bytebusters@gmail.com.

## Licencia
Este proyecto se distribuye bajo la licencia CC0 1.0 Universal (Public Domain Dedication). Puedes copiar, modificar y distribuir el trabajo, incluso con fines comerciales, sin pedir permiso.
