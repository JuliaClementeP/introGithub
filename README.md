<p align="center">
  <img src="https://www.uah.es/export/sites/uah/.galleries/imagenes-estructura/logo1.png_105938625.png" alt="UAH">
</p>

# DESCARGAR LA HERRAMIENTA
  <p align="center">
    <a href="https://github.com/FranLapina/Herramienta-de-Aprendizaje-Git-y-GitHub-en-Linux/releases/tag/Herramienta_Aprendizaje_Git_UAH">
      <strong>👉👉👉👉 PULSA AQUÍ PARA DESCARGAR LA HERRAMIENTA 👈👈👈👈</strong>
    </a>
  </p>
  
También puedes acceder mediante el botón de "Releases" en la parte derecha. Se puede ver en el lateral derecho de la pantalla

# Herramienta para aprender git

Aplicación de escritorio interactiva para el aprendizaje progresivo de **Git y GitHub**, desarrollada como Trabajo de Fin de Grado del **Grado en Ingeniería de Computadores de la Universidad de Alcalá**.

El proyecto busca ofrecer un entorno guiado, visual y organizado por niveles para introducir al estudiante en el uso de Git y GitHub, combinando explicaciones teóricas, ejemplos de comandos, capturas y actividades guiadas.

> **Importante:** la aplicación tiene finalidad educativa. No ejecuta comandos Git reales ni modifica repositorios del usuario.

---

## Características principales

- Aplicación de escritorio desarrollada con **Electron**.
- Contenidos organizados en cuatro niveles:
  - **Inicio**
  - **Principiante**
  - **Intermedio**
  - **Avanzado**
- Contenidos almacenados localmente.
- Navegación mediante menú lateral.
- Carga dinámica de unidades didácticas.
- Ejemplos de comandos Git.
- Capturas de terminal y Visual Studio Code.
- Actividades guiadas de consolidación.
- Visor modal para ampliar imágenes y diagramas.
- Estructura modular pensada para facilitar la incorporación de nuevos contenidos.
- Interfaz desarrollada con tecnologías web estándar.

---

## Tecnologías utilizadas

- **Electron**
- **Node.js**
- **JavaScript**
- **HTML5**
- **CSS3**
- **npm**
- **Electron Builder**

---

## Código fuente y modificación libre

El código fuente completo de la aplicación se encuentra disponible en este repositorio.

El proyecto puede utilizarse como base para estudiar su estructura, modificar la interfaz, reorganizar los contenidos, incorporar nuevas lecciones, añadir funcionalidades o desarrollar una versión diferente a partir del código existente.

La intención es que el proyecto pueda **reutilizarse, modificarse y ampliarse libremente**. No es necesario conservar la estructura, apariencia o contenidos originales: cada usuario o desarrollador puede adaptarlo a sus propias necesidades respetando los términos de la licencia del repositorio.

---

## Añadir nuevas lecciones

La aplicación se ha organizado de forma modular para que sea sencillo ampliar el itinerario formativo.

Las unidades disponibles se registran en la estructura `tutorialData`, situada en:

```text
js/script.js
```

Cada entrada relaciona el nombre mostrado en el menú con el archivo HTML correspondiente:

```js
{
    name: 'git status',
    file: 'comandos/principiante/git-status.html'
}
```

Para añadir, por ejemplo, una nueva lección sobre `git tag`:

### 1. Crear el nuevo módulo HTML

```text
comandos/intermedio/git-tag.html
```

### 2. Añadirlo a `tutorialData`

```js
{
    name: 'git tag',
    file: 'comandos/intermedio/git-tag.html'
}
```

El sistema de navegación existente generará automáticamente su opción en el menú y reutilizará la misma lógica de carga que para el resto de unidades.

Si la nueva lección necesita imágenes, pueden añadirse dentro del directorio:

```text
imagenes/
```

---

## Seguridad y aislamiento

La ventana de Electron se configura con:

```js
nodeIntegration: false,
contextIsolation: true
```

Estas opciones reducen los privilegios del proceso de renderizado:

- **`nodeIntegration: false`** impide que el código de la interfaz acceda directamente a las APIs de Node.js.
- **`contextIsolation: true`** separa el contexto de la página del contexto utilizado por el script de precarga.

La aplicación no necesita ejecutar comandos Git ni acceder directamente a los repositorios del usuario desde la interfaz.

---

## Requisitos para ejecutar el código fuente

Para ejecutar el proyecto desde el código fuente es necesario disponer de:

- **Node.js**
- **npm**

Puedes comprobar que están instalados con:

```bash
node -v
npm -v
```

---

## Instalación

Clona el repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_REPOSITORIO>
```

Instala las dependencias:

```bash
npm install
```

---

## Ejecución en desarrollo

Para iniciar la aplicación:

```bash
npm start
```

También puede utilizarse:

```bash
npm run dev
```

En modo de desarrollo se abren las herramientas de desarrollo de Electron para facilitar la depuración.

---

## Generar una versión distribuible

El proyecto utiliza **Electron Builder** para empaquetar la aplicación.

```bash
npm run build
```

Los archivos generados se almacenan en:

```text
dist/
```

La configuración incluida en `package.json` contempla actualmente:

### Windows

- Versión **portable**

### Linux

- **AppImage**

### MacOS

- Version **portable**

---


## Alcance y limitaciones

La aplicación está diseñada como una herramienta de aprendizaje guiado y consulta.

La versión actual:

- No ejecuta comandos Git reales.
- No modifica repositorios del usuario.
- No incorpora un terminal Git integrado.
- No dispone de simulación de repositorios.
- No corrige automáticamente las actividades.
- No registra el progreso del estudiante.
- Presenta los contenidos únicamente en español.

Las actividades propuestas están pensadas para que el estudiante pueda reproducir posteriormente los procedimientos en su propio entorno de trabajo.


