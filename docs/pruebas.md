# Test Matrix (Matriz de Pruebas) — EDU_Tycoon

This document outlines the testing strategy, test scenarios, execution results, and quality assurance evidence for **EDU_Tycoon (Entrega 1)** in accordance with the course specification.

---

## 📱 Test Environment & Specifications

- **Device / OS Under Test**: Physical Android Device (Xiaomi / Samsung / Pixel) & Android Virtual Device (AVD).
- **Target SDK / API Level**: Android 16 (API 36) / Target API 36 (`minSdk 21`).
- **Application Version**: `1.3.1` (versionCode 5).
- **Frameworks**: Kotlin 2.2.10, libGDX 1.14.0, libKTX 1.13.1-rc1.

---

## 🧪 Initial Test Matrix (Sección 2.6)

The following matrix covers the primary happy path, boundary states, recreation/lifecycle events, and accessibility checks:

| ID | Test Case | Category | Initial Conditions / Steps | Expected Result | Actual Result | Status |
|:---|:---|:---|:---|:---|:---|:---:|
| **TC-01** | Happy Path: Passive Income & Building Upgrade | Core Gameplay | 1. Launch app.<br>2. Complete initial dialogue.<br>3. Wait for 30s cycle.<br>4. Tap ESCOM building and select Upgrade. | Passive income is credited; balance increases; building level increments; reputation percentage increases. | Income credited and HUD accurately reflects new level and student capacity. | **PASS** |
| **TC-02** | Invalid / Insufficient Balance for Building Purchase | Boundary / Error | 1. Have balance `<` building cost.<br>2. Open `BuildingInfoWindow` for an unpurchased or upgradable property.<br>3. Attempt to tap purchase button. | Purchase button disables or displays warning "¡Saldo insuficiente!", preventing money from becoming negative. | Action is prevented; button shows red warning; balance remains intact. | **PASS** |
| **TC-03** | Screen Recreation / Pause & Resume | Lifecycle | 1. Open game screen.<br>2. Minimize app (Home button) or toggle Android overview screen.<br>3. Resume app. | Game context and textures resume gracefully; render loop re-attaches without crashes or memory corruption. | Game resumes smoothly in landscape orientation without ANR or crash. | **PASS** |
| **TC-04** | Offline Mode / Network Unavailability | Connectivity | 1. Put device in Airplane Mode (disable Wi-Fi and Cellular).<br>2. Launch game.<br>3. Play cycles and upgrade buildings. | Game functions 100% locally with Room local persistence and no dependency on external servers. | Complete standalone functionality; no network connection required. | **PASS** |
| **TC-05** | Accessibility & UI Scaling (Text & Contrast) | Accessibility | 1. Set system font scale to Largest (130%+).<br>2. Inspect HUD labels (Money, Students, Reputation) and event toast text. | Text remains legible against dark HUD backgrounds (high contrast gold/cyan/red on translucent black); no overlap with buttons. | Texts are readable, high-contrast, and touch targets remain responsive. | **PASS** |

---

## 🎯 Feature QA Tests: Non-Negative Balance Rule (Sección 3.6 / Feature #1)

Tests specifically designed to validate the new non-negative balance rule under random expense events:

| ID | Test Scenario | Steps | Expected Result | Actual Result | Status |
|:---|:---|:---|:---|:---|:---:|
| **TC-06** | Expense Event with Sufficient Funds | 1. Balance = $500,000.<br>2. Event occurs (e.g., Fuga de agua -$25,000). | Full expense amount is deducted ($475,000 remaining). HUD text remains in gold. | $25,000 deducted; balance updated; toast shows normal deduction. | **PASS** |
| **TC-07** | Expense Event Exceeding Current Balance (Floor Capping) | 1. Balance = $30,000.<br>2. Event triggers with cost $50,000.<br>3. `descontarHastaCero(50000)` executes. | Balance is strictly capped at **$0** (`maxOf(0L, ...)`). Money NEVER drops below 0. | Balance equals $0. No negative balance allowed. | **PASS** |
| **TC-08** | Bankruptcy Visual Feedback in HUD and Toast | 1. Trigger expense that drops balance to $0. | HUD `$ [Amount]` text and symbol turn **RED**. Toast displays `(¡FONDOS EN CERO!)`. | HUD turns red dynamically; toast warns user of depleted funds. | **PASS** |
| **TC-09** | Automated Unit Tests (`GameStateTest`) | Run `./gradlew test` via command line or Android Studio. | All unit tests pass, validating boundary conditions of `descontarHastaCero()`. | 5 tests run, 0 failures, BUILD SUCCESSFUL. | **PASS** |
