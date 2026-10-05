# EDU_Tycoon

Videojuego de simulación y gestión escolar móvil desarrollado en **Kotlin** con **libGDX** y **libKTX**.

---

## 🛠️ Requisitos Previos

Antes de ejecutar el proyecto desde un clon limpio, asegúrate de contar con:

1. **Git** instalado.
2. **Java Development Kit (JDK)**: JDK 17 o JDK 21 (ej. OpenJDK / Amazon Corretto).
3. **Android Studio** (versión reciente: Ladybug, Koala o Hedgehog) con:
   - **Android SDK Platform 36** (o compatible con compileSdk 36).
   - **Android SDK Build-Tools 36.0.0** (o superior).
   - **Android SDK Command-line Tools** y **CMake / NDK** (si se requieren binarios nativos de libGDX).

> [!WARNING]
> **Rutas en Windows:** El Android Gradle Plugin rechaza rutas con caracteres no ASCII (acentos, ñ, espacios excesivos). Clona el repositorio en una ruta limpia, por ejemplo `C:\Proyectos\EDU_Tycoon` o `C:\Users\<Usuario>\AndroidStudioProjects\EDU_Tycoon`.

---

## 🚀 Guía de Ejecución desde un Clon Limpio

### 1. Clonar el repositorio
Abre tu terminal y clona el proyecto:

```bash
git clone https://github.com/MiguelCruz10/EDU_Tycoon.git
cd EDU_Tycoon
```

---

### 2. Configurar el SDK de Android (`local.properties`)
Gradle necesita conocer la ubicación de tu Android SDK. Crea un archivo llamado `local.properties` en la raíz del proyecto (`EDU_Tycoon/local.properties`):

- **En Windows:**
  ```properties
  sdk.dir=C\:\\Users\\<TU_USUARIO>\\AppData\\Local\\Android\\Sdk
  ```
- **En Linux / macOS:**
  ```properties
  sdk.dir=/home/<TU_USUARIO>/Android/Sdk
  # o en Mac:
  sdk.dir=/Users/<TU_USUARIO>/Library/Android/sdk
  ```
*(Nota: Si abres el proyecto en Android Studio por primera vez, este archivo se genera automáticamente).*

---

### 3. Ejecución desde Android Studio (Recomendado)

1. Abre **Android Studio**.
2. Selecciona **Open** y elige la carpeta raíz del proyecto (`EDU_Tycoon`).
3. Espera a que termine la sincronización inicial de Gradle (*Gradle Sync*).
4. Conecta tu dispositivo Android físico por USB (con **Depuración por USB** activada) o inicia un Emulador Android (AVD).
5. En la barra superior, asegúrate de tener seleccionada la configuración de ejecución **`android`** (o `app`).
6. Presiona el botón **Run ▶** (`Shift + F10`).

---

### 4. Ejecución y compilación por Línea de Comandos

El proyecto incluye el Gradle Wrapper listo para compilar y ejecutar tareas.

#### Correr pruebas unitarias:
- **Windows:**
  ```cmd
  gradlew.bat test
  ```
- **Linux / macOS:**
  ```bash
  ./gradlew test
  ```

#### Compilar el APK de depuración (Debug):
- **Windows:**
  ```cmd
  gradlew.bat android:assembleDebug
  ```
- **Linux / macOS:**
  ```bash
  ./gradlew android:assembleDebug
  ```
El archivo APK resultante se generará en:  
`android/build/outputs/apk/debug/android-debug.apk`

#### Instalar y ejecutar directamente en un dispositivo conectado (vía ADB):
```bash
./gradlew android:installDebug
```

---

## 📁 Estructura del Proyecto

- **`core/`**: Lógica central del videojuego, motores de ciclo (`GameCycleEngine`), economía (`EconomyEngine`), eventos (`EventEngine`), interfaces de Scene2D y pantallas (`GameScreen`).
- **`android/`**: Módulo Android, manifiesto, configuración de pantalla landscape y lanzador `AndroidLauncher`.
- **`assets/`**: Recursos del juego (sprites, mapas Tiled `.tmx`, fuentes tipográficas, texturas e interfaces).
- **`docs/`**: Documentación académica, evidencias de ejecución por integrante y matrices de pruebas.
