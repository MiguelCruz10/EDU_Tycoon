# EDU_Tycoon

Mobile school simulation and management game developed in **Kotlin** using **libGDX** and **libKTX**.

---

## 🛠️ Prerequisites

Before executing the project from a clean clone, make sure your environment meets the following specifications (based on the project build configuration):

1. **Git** installed on your system.
2. **Java Development Kit (JDK)**: OpenJDK 17 or OpenJDK 21 (e.g., Amazon Corretto 21). Note: The project compiles to Java 17 bytecode (`sourceCompatibility 17`, `jvmTarget JVM_17`).
3. **Android Studio** (recent release: Ladybug, Koala, or Hedgehog) configured with:
   - **Android SDK Platform 36** (`compileSdk 36`, `targetSdk 36`).
   - **Android SDK Build-Tools 36.0.0**.
   - **Android SDK Command-line Tools** and **CMake / NDK 25+** (for libGDX native libraries).

> [!WARNING]
> **Windows Path Restriction:** The Android Gradle Plugin strictly rejects workspace directories containing non-ASCII characters or accents (e.g. `C:\Users\...\Imágenes\...`). Always clone into a pure ASCII path such as `C:\AndroidStudioProjects\EDU_Tycoon` or `C:\Dev\EDU_Tycoon`.

---

## 🚀 Execution Guide from a Clean Clone

### 1. Clone the Repository
Open your terminal and clone the repository:

```bash
git clone https://github.com/MiguelCruz10/EDU_Tycoon.git
cd EDU_Tycoon
```

---

### 2. Configure Android SDK (`local.properties`)
Gradle requires the location of your local Android SDK. Create a file named `local.properties` at the root directory of the project (`EDU_Tycoon/local.properties`):

- **On Windows:**
  ```properties
  sdk.dir=C\:\\Users\\<YOUR_USERNAME>\\AppData\\Local\\Android\\Sdk
  ```
- **On Linux:**
  ```properties
  sdk.dir=/home/<YOUR_USERNAME>/Android/Sdk
  ```
- **On macOS:**
  ```properties
  sdk.dir=/Users/<YOUR_USERNAME>/Library/Android/sdk
  ```
*(Note: If you open the project directly in Android Studio, this file is created automatically).*

---

### 3. Running from Android Studio (Recommended)

1. Open **Android Studio**.
2. Select **File > Open...** and choose the root directory of the project (`EDU_Tycoon`).
3. Allow Gradle to download dependencies and finish project synchronization (*Gradle Sync*).
4. Connect a physical Android device via USB with **USB Debugging** enabled, or launch an Android Virtual Device (AVD).
5. In the top toolbar, ensure the run configuration is set to **`android`**.
6. Click the green **Run ▶** button (`Shift + F10`).

---

### 4. Running and Building via Command Line

The repository provides the Gradle Wrapper pre-configured with Gradle 9.5.0:

#### Run Unit Tests:
- **Windows:**
  ```cmd
  gradlew.bat test
  ```
- **Linux / macOS:**
  ```bash
  ./gradlew test
  ```

#### Assemble Debug APK:
- **Windows:**
  ```cmd
  gradlew.bat android:assembleDebug
  ```
- **Linux / macOS:**
  ```bash
  ./gradlew android:assembleDebug
  ```
The output APK will be placed at:  
`android/build/outputs/apk/debug/android-debug.apk`

#### Install and Run directly on a connected device (via ADB):
- **Windows:**
  ```cmd
  gradlew.bat android:installDebug
  ```
- **Linux / macOS:**
  ```bash
  ./gradlew android:installDebug
  ```

---

## 📁 Project Architecture

- **`core/`**: Multiplatform game logic written in pure Kotlin. Contains the game cycle engine (`GameCycleEngine`), passive economy calculations (`EconomyEngine`), event systems (`EventEngine`), and Scene2D/libKTX stages (`GameScreen`).
- **`android/`**: Android-specific module containing `AndroidManifest.xml` (landscape orientation), native libraries, asset packaging, and `AndroidLauncher`.
- **`assets/`**: Shared game assets including Tiled maps (`.tmx`), tilesets, UI textures, sprite sheets, and TrueType fonts (`font.ttf`).
- **`docs/`**: Project documentation, academic delivery materials, testing matrices, and execution evidence.
