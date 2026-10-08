# Licenses and Third-Party Attributions (docs/licencias.md)

This document establishes the licensing terms of the **EDU_Tycoon** repository as well as the provenance and licensing of all third-party libraries, frameworks, graphic assets, and audio resources utilized in the project.

---

## 📄 Project License

EDU_Tycoon is distributed under the **MIT License**.

```text
MIT License

Copyright (c) 2026 Emmanuel Juarez Palma, Miguel Cruz, Carlos Martinez

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📦 Third-Party Libraries and Frameworks

| Component / Dependency | Version | License | Usage / Purpose | Provenance / Repository |
|:---|:---|:---|:---|:---|
| **libGDX** | 1.14.0 | Apache 2.0 | Core cross-platform game framework (render, input, math, audio). | [libgdx/libgdx](https://github.com/libgdx/libgdx) |
| **libKTX** | 1.13.1-rc1 | Apache 2.0 | Kotlin extensions and DSLs for libGDX (Scene2D, math, assets). | [libktx/ktx](https://github.com/libktx/ktx) |
| **Android Gradle Plugin (AGP)** | 8.13.2 | Apache 2.0 | Android build and packaging toolchain. | Google / Android Open Source Project |
| **Kotlin Standard Library** | 2.2.10 | Apache 2.0 | Core Kotlin runtime. | [JetBrains/kotlin](https://github.com/JetBrains/kotlin) |
| **AndroidX Room** | 2.7.0-alpha13 | Apache 2.0 | Local SQLite persistence layer for game saves and state. | Google AndroidX |
| **VisUI** | 1.5.5 | Apache 2.0 | UI skin and components for libGDX Scene2D. | [kotcrab/vis-ui](https://github.com/kotcrab/vis-ui) |
| **FreeType (gdx-freetype)** | 1.14.0 | FreeType License / BSD | Dynamic TrueType font rendering from `font.ttf`. | libGDX project |

---

## 🎨 Graphic, Visual, and Audio Assets Provenance

| Asset Name / Path | Source / Creator | License | Description |
|:---|:---|:---|:---|
| **Map and Buildings** (`assets/Mapa/*.tmx`, `assets/Mapa/Edificios/*`) | Created by the EDU_Tycoon Development Team | CC BY-SA 4.0 / MIT | Isometric school campus tilesets, ESCOM building textures, and custom map layouts created with Tiled Map Editor. |
| **Character Sprites** (`assets/sprite_*.png`) | IPN Educational Tycoon Art Assets (Internal IPN Student Team) | Proprietary / Academic Use (IPN) | Character portraits for Ing. Lázaro Cárdenas dialogues. |
| **User Interface Textures** (`assets/menuicon.png`, `assets/logo_app.png`, etc.) | Created by the Development Team | MIT | Buttons, pause icons, and application branding. |
| **Typography** (`assets/font.ttf`) | Open Font License (OFL) / Apache 2.0 | SIL Open Font License | TrueType font embedded for in-game dialogs, HUD numbers, and labels. |
| **Background Music & Sound Effects** | Public Domain / CC0 / Internal Assets | CC0 1.0 Universal | Background ambient track and interactive audio feedback. |

---

## 🔒 Compliance & Integrity Declaration

All code, graphics, and dependencies included in this repository have been audited to comply with their respective open-source licenses. No proprietary, unlicensed, or copyleft-incompatible assets have been incorporated.
