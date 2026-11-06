<div align="center">

```text
  _____       ____       _  _____ 
 |  __ \     |  _ \     / \|_   _|
 | |__) |    | |_) |   / _ \ | |  
 |  ___/     |  _ <   / ___ \| |  
 | |     _   | |_) | / /   \ \ |  
 |_|    (_)  |____/ /_/     \_\|_| 
```

# .BAT — Terminal MS-DOS Batch Studio & Generator

**Entorno interactivo híbrido (Python Desktop + Web Localhost) para aprender, diseñar compiladores y automatizar Windows mediante scripts Batch (.BAT / .CMD).**

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-00ff66.svg?style=for-the-badge&logo=python&logoColor=black)](https://www.python.org/)
[![Platform Windows](https://img.shields.io/badge/platform-Windows-00e5ff.svg?style=for-the-badge&logo=windows&logoColor=black)](https://www.microsoft.com/windows)
[![UI Retro CRT](https://img.shields.io/badge/ui-MS--DOS%20CRT-ffb000.svg?style=for-the-badge)](https://github.com/FluxzyCorporations/.BAT)
[![GitHub Repository](https://img.shields.io/badge/GitHub-FluxzyCorporations%2F.BAT-white.svg?style=for-the-badge&logo=github&logoColor=black)](https://github.com/FluxzyCorporations/.BAT)

[Sitio Web / Instalador](website/index.html) • [Repositorio Oficial](https://github.com/FluxzyCorporations/.BAT) • [Descargar ZIP v1.0](https://github.com/FluxzyCorporations/.BAT/releases/download/Scripts/BAT_v1.0.zip)

</div>

---

## 📌 ¿Qué es .BAT?

**.BAT** es una suite moderna con estética vintage inspirada en terminales **MS-DOS y monitores CRT de fósforo verde**. Su objetivo es simplificar radicalmente el aprendizaje y la creación de scripts en Windows.

A través de un lanzador de escritorio nativo en Python y una potente interfaz web local (`localhost:8888`), permite a desarrolladores, administradores de sistemas y usuarios entusiastas diseñar compiladores automáticos, crear menús interactivos tipo BIOS y generar utilidades de mantenimiento sin tener que escribir comandos oscuros de memoria.

---

## 🕹️ El Lanzador de Python (Desktop Launcher)

Al iniciar la aplicación (`launcher.py` o `INICIAR_APP.bat`), se presenta la consola retro de control con sus opciones principales:

| Botón | Función |
| :--- | :--- |
| **`[ 1 ] ▶ START`** | Enciende el servidor local en segundo plano y **abre automáticamente tu navegador web** en `http://localhost:8888`. |
| **`[ ⏹ ] DESACTIVAR LOCALHOST`** | *(Aparece dinámicamente al iniciar la web)*. Permite apagar el servidor; al hacerlo, la web muestra la alerta emergente **"el servidor se ha detenido"** y cierra la pestaña automáticamente. |
| **`[ 2 ] 📁 UBICACIÓN`** | Abre el explorador de carpetas de Windows para elegir dónde se guardarán todos los scripts `.bat` que generes en la plataforma. Tu elección se almacena en `config.json`. |
| **`[ 3 ] ✖ CERRAR`** | Detiene todos los procesos y cierra la aplicación limpiamente. |

---

## 🌐 Apartados de la Suite Web (`localhost:8888`)

La aplicación web cuenta con una barra lateral modular dividida en los siguientes apartados:

### 1. `[01] 📖 APRENDIZAJE .BAT`
- **Módulo 1: Fundamentos:** `@echo off`, `chcp 65001`, `pause`, `cls`, `title`, `color`, variables de entorno y comentarios (`rem` y `::`).
- **Módulo 2: Variables y Entrada:** `set /p` para capturar texto del usuario, `set /a` para operaciones aritméticas, argumentos de consola (`%1`..`%*`) y rutas dinámicas (`%~dp0`).
- **Módulo 3: Condicionales:** `IF`, `ELSE`, `IF EXIST`, `IF /I` (insensible a mayúsculas) y comparadores numéricos (`EQU`, `NEQ`, `GTR`, `GEQ`, `LSS`, `LEQ`).
- **Módulo 4: Bucles FOR:** `FOR %%i IN (*)`, `FOR /L` (contadores numéricos), `FOR /R` (búsqueda recursiva) y `FOR /F` (procesamiento de tokens).
- **Módulo 5: Funciones y Modularidad:** `GOTO`, `CALL :subrutina` con paso de parámetros y retornos limpios con `EXIT /B`.
- **Módulo 6: Elevación UAC:** Auto-elevar scripts a permisos de **Administrador** automáticamente mediante PowerShell en Batch.
- *Cada tema incluye botón para copiar el código y botón para guardarlo directamente como archivo `.bat` de práctica.*

### 2. `[02] ⚙️ COMPILADORES & BUILDERS`
Genera scripts listos para compilar proyectos en un solo clic:
- **Python:** Crear entorno virtual `.venv`, instalar `requirements.txt` y empaquetar a ejecutable `.exe` independiente mediante **PyInstaller** (`--onefile`, `--noconsole`, icono personalizado).
- **C / C++:** Compilación con **GCC / G++** (MinGW) o **MSVC** (`cl.exe`) con flags de optimización (`-O2`, `-Wall`, `-std=c++17`).
- **Java:** Compilación con `javac` y empaquetado en binario `.jar` ejecutable (`jar cvfe`).
- **Node.js / TypeScript:** Instalación de dependencias, transpilación con `tsc` y ejecución con Node.
- **Rust:** `cargo build --release` y `cargo run`.
- **C# / .NET:** `dotnet build` y `dotnet publish -c Release`.
- **Personalizado:** Flags y comandos arbitrarios para Make, CMake, Go, etc.
- *Opciones integradas: Pausar al terminar, guardar reporte en `build.log` y autoejecutar el binario generado.*

### 3. `[03] 📋 MENÚS INTERACTIVOS`
- Diseñador visual de menús interactivos estilo consola / BIOS.
- Soporta método **`CHOICE`** (pulsación de una sola tecla instantánea) y método **`SET /P`** (escribir número/texto y pulsar Enter).
- Selector de colores de consola (`0A` Verde Matrix, `0E` Ámbar, `1F` MS-DOS Azul, `0B` Cyan, `4F` Rojo Alerta).
- Plantillas de fábrica: *Mantenimiento de PC*, *Lanzador de Juegos y Apps* y *Toolbox del Programador*.
- Añade, edita y elimina opciones dinámicamente con previsualización de código en vivo.

### 4. `[04] ⚡ AUTOMATIZACIÓN`
- **Copia de Seguridad Robusta (ROBOCOPY):** Respaldo en espejo (`/MIR`), multi-hilo (`/MT:8`), reintentos y generación de informes de log.
- **Limpieza Profunda de Windows:** Vaciado de temporales de usuario (`%temp%`), temporales de sistema, Prefetch y limpieza de caché DNS.
- **Watchdog / Guardián de Procesos:** Monitor que vigila si un programa o servidor sigue corriendo; si se cae, lo relanza en automático.
- **Reparación de Red:** Liberación y renovación de IP DHCP, reinicio del catálogo Winsock y comprobación con ping.
- **Apagado Programado:** Temporizador cancelable en minutos con advertencia visual.

### 5. `[05] ✏️ CREADOR / EDITOR LIBRE`
- Editor de texto con fuente monospace y barra de inserción de snippets con un clic:
  - `+ Elevar a Administrador (UAC)`
  - `+ Cambiar a directorio del script (%~dp0)`
  - `+ Habilitar UTF-8 (chcp 65001)`
  - `+ Comprobar existencia de comando en PATH`
  - `+ Extraer marcas de fecha y hora`
  - `+ Barra de progreso simulada en consola`

### 6. `[06] 📁 MIS .BAT GENERADOS`
- Explorador en tiempo real de todos los scripts guardados en tu carpeta seleccionada.
- Información de tamaño y fecha de modificación.
- Botón **`▶ EJECUTAR`** para probar el script de inmediato en una ventana de CMD.
- Botón para abrir la carpeta directamente en el Explorador de Windows.

### 7. `[07] 🛠️ CONFIGURACIÓN & ESTILOS`
- Selector de paletas retro: **Fósforo Verde**, **Ámbar Retro**, **MS-DOS Azul**, **Cyber Cyan** y **Clásico Monocromo**.
- Conmutador de filtro de líneas de escaneo CRT (*scanlines*).
- Conmutador de efectos de sonido sintetizados nativamente con **Web Audio API** (teclas mecánicas y sonido de escritura de disquete).

---

## 📦 Instalación y Requisitos

### Requisitos Previos
- **Windows 10 / 11** (o Windows Server).
- **Python 3.10 o superior** instalado y agregado al `PATH`.
- Dependencias (incluidas en los entornos estándar):
  ```bash
  pip install fastapi uvicorn
  ```

### Puesta en Marcha Rápida
1. Clona este repositorio o descarga el paquete ZIP:
   ```bash
   git clone https://github.com/FluxzyCorporations/.BAT.git
   cd .BAT
   ```
2. Ejecuta el archivo de inicio:
   ```cmd
   INICIAR_APP.bat
   ```
   *(o alternativamente ejecuta `python launcher.py`)*.
3. En la ventana del lanzador, pulsa **`[ 1 ] ▶ START`**. Tu navegador abrirá automáticamente la plataforma en `http://localhost:8888`.

---

## 📂 Estructura del Proyecto

```text
.BAT/
├── INICIAR_APP.bat              # Lanzador rápido de un clic
├── launcher.py                  # Interfaz gráfica de escritorio en Python (Tkinter)
├── server.py                    # Servidor backend local (FastAPI / Uvicorn)
├── config.json                  # Archivo de configuración (ubicación de salida, puerto, tema)
├── mis_scripts_bat/             # Carpeta predeterminada para guardar los .bat generados
├── static/                      # Recursos del frontend web
│   ├── index.html               # Estructura de la aplicación web .BAT
│   ├── style.css                # Estilos retro CRT, scanlines y paletas vintage
│   └── app.js                   # Motor interactivo, generadores de código y sintetizador SFX
└── website/                     # Sitio web de presentación y descarga
    ├── index.html               # Landing page con capturas y botón de descarga
    ├── style.css                # Estilos web retro terminal
    └── downloads/               # Paquetes distribuibles (BAT_v1.0.zip)
```

---

## 💬 Cita Célebre

> *"Talk is cheap. Show me the code."*  
> *(Hablar es fácil. Muéstrame el código.)*  
> — **Linus Torvalds**, Creador del kernel Linux y Git.

---

## 🛡️ Firma Digital Oficial

```text
╔═══════════════════════════════════════════════════════════════════════════╗
║                  ★ DIGITAL SIGNATURE & VERIFIED BUILD ★                   ║
║                                                                           ║
║                 Desarrollado por FluxzyCorporation's Org                  ║
║                                                                           ║
║     OFFICIAL REPOSITORY: https://github.com/FluxzyCorporations/.BAT       ║
║     KEY IDENTIFIER: #FLUX-BAT-SYS-2026 • VERIFIED DEVELOPER RELEASE       ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

---

## 📄 Derechos Reservados

**`.BAT todos los derechos reservados`**  
Distribuido bajo la organización **FluxzyCorporation's Org**. Creado para la comunidad de desarrolladores y entusiastas del entorno de comandos de Windows.
