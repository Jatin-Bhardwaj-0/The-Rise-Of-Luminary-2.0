<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=230&section=header&text=The%20Rise%20of%20Luminary&fontSize=54&fontColor=fff&animation=twinkling&fontAlignY=40&desc=A%20Cinematic%20Educational%20RPG&descAlignY=60&descFontSize=20" width="100%"/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Cinzel+Decorative&size=17&pause=1200&color=FFD700&center=true&vCenter=true&width=650&lines=Answer+questions.+Deal+damage.+Level+up.;Knowledge+is+your+weapon.;Fantasy+RPG+%C3%97+Anime+Combat+%C3%97+Education;Built+in+C%2B%2B17+with+SFML+3.0.2;30+story+chapters+%C3%97+5+subjects+%C3%97+440%2B+questions)](https://git.io/typing-svg)

<br/>

![C++17](https://img.shields.io/badge/C%2B%2B-17-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![SFML](https://img.shields.io/badge/SFML-3.0.2-8CC445?style=for-the-badge&logo=sfml&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-3.10%2B-064F8C?style=for-the-badge&logo=cmake&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-nlohmann%2Fjson-F7C948?style=for-the-badge&logo=json&logoColor=black)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

</div>

---

## What is The Rise of Luminary?

A **turn-based educational RPG / roguelike deck-builder** built in C++17 with SFML 3.0.2.

Learning is fused directly into combat. Answer real educational questions to attack, build combo streaks, trigger critical hits, earn XP, and advance through story chapters. The design goal is singular: **make education feel like a power fantasy, not a quiz.**

> _Fantasy RPG × Anime-inspired combat × Cinematic particle feedback_
>
> _Inspired by: Persona · Slay the Spire · Honkai: Star Rail · RPG Maker_

---

## ⚔️ Gameplay Loop

```
[ QUESTION APPEARS ]
        │
        ├─ Correct Answer ──► You attack!  Damage = stats × elemental affinity
        │                          └─ Streak builds ──► Combo multiplier activates
        │                                                    └─ CRIT? ──► Screen shake + particle burst!
        │
        └─ Wrong Answer ──► Enemy counterattacks  ·  Streak resets
```

Every correct answer in a row multiplies your damage. Chain enough hits and the screen erupts.

### Combat Systems

| System | Description |
|:---|:---|
| ⚡ Elemental Affinity | 6 elements — Fire, Water, Lightning, Nature, Dark, Light — each with damage multipliers |
| 💥 Combo & Streak | Consecutive correct answers multiply damage exponentially |
| 🎇 Particle System | Visual burst effects on every hit, combo, and critical |
| 📳 Screen Shake | Camera shake tied to damage magnitude |
| 📊 Animated HP Bars | Real-time health display with battle log |
| 🌄 Parallax Backgrounds | Scrolling layered scenes during combat |
| 📖 Story Mode | 30-chapter narrative per subject, with boss battles |

---

## 📚 Subjects × Grade Levels

**440+ questions across 24 JSON files**, auto-filtered at runtime by the player's grade and subject — no manual selection needed.

|  | Preschool | Elementary | Middle School | High School | College Prep |
|:---|:---:|:---:|:---:|:---:|:---:|
| ➕ Mathematics | ✅ | ✅ | ✅ | ✅ | ✅ |
| 🔬 Science      | ✅ | ✅ | ✅ | ✅ | ✅ |
| 🏛️ History      | ✅ | ✅ | ✅ | ✅ | ✅ |
| 📖 Literature   | ✅ | ✅ | ✅ | ✅ | ✅ |
| 🎨 Arts         | ✅ | ✅ | ✅ | ✅ | ✅ |

Each subject ships with a **30-chapter story mode** — narrative cutscenes, chapter bosses, and escalating difficulty.

---

## 🗺️ Game Flow

```
┌──────────────────────────────────────────────────┐
│            SPLASH VIDEO (80-frame intro)          │
└─────────────────────┬────────────────────────────┘
                      │
             ┌────────▼────────┐
             │    MAIN MENU    │
             └────────┬────────┘
              ┌───────┴────────┐
   ┌──────────▼───────┐  ┌────▼──────────────┐
   │  PROFILE SELECT  │  │   REGISTRATION    │
   │  (returning)     │  │   (new player)    │
   └──────────┬───────┘  └────────┬──────────┘
              └──────────┬────────┘
                ┌────────▼────────┐
                │CHARACTER SELECT │
                └────────┬────────┘
                  ┌──────▼──────┐
                  │TRAINING HUB │
                  └──────┬──────┘
            ┌────────────┴─────────────┐
    ┌────────▼───────┐        ┌────────▼──────┐
    │ LESSON VIEWER  │        │  STORY MODE   │
    └────────┬───────┘        └───────────────┘
    ┌────────▼───────┐
    │  BATTLE STATE  │  ◄── Core gameplay loop
    └────────────────┘
```

---

## 🔧 Building

### Prerequisites

- **CMake** 3.10 or newer
- **SFML 3.0.2** (headers + libraries)
- A **C++17** compiler — MSVC 2019+, GCC 9+, or Clang 10+

### Build Steps

```bash
git clone <repo-url>
cd THE-RISE-OF-LUMINARY-main

mkdir build && cd build
cmake ..
cmake --build . --config Release
```

> The CMake build automatically copies `assets/` and `data/` into the output directory after each build.

### Running

**Always launch from the project root.** All asset and data paths are relative — running from a different directory will silently fail all file loads.

```bash
.\build\Release\LuminaryRPG.exe
```

---

## 📁 Project Structure

<details>
<summary><b>Click to expand</b></summary>

```
THE-RISE-OF-LUMINARY-main/
│
├── src/
│   ├── Game.cpp / Game.hpp                Main loop, state machine, shared player data
│   ├── TrainingState.cpp / .hpp           Core battle + question system
│   ├── TrainingStoryState.cpp / .hpp      Story mode battle integration
│   ├── BattleSystem.cpp / .hpp            Turn-based combat engine
│   ├── Character.cpp / .hpp               Player stats, XP, rarity progression
│   ├── Enemy.cpp / .hpp                   Enemy generation and scaling
│   ├── ElementSystem.cpp / .hpp           Elemental damage type multipliers
│   ├── SaveManager.cpp / .hpp             JSON save/load for player profiles
│   ├── ParticleSystem.cpp / .hpp          Visual particle burst effects
│   ├── ScreenShake.cpp / .hpp             Camera shake on hits
│   ├── ParallaxBackground.cpp / .hpp      Scrolling layered combat backgrounds
│   ├── Card.cpp / .hpp                    Card mechanics
│   ├── Button.cpp / .hpp                  Animated UI button system
│   ├── StoryManager.hpp                   Story JSON loading
│   ├── TrainingHubState.cpp / .hpp        Chapter / lesson selection hub
│   ├── LessonViewerState.cpp / .hpp       In-game lesson viewer UI
│   └── ...                                Menu, registration, character select states
│
├── assets/
│   ├── fonts/                             arial.ttf
│   ├── images/                            Character portraits, backgrounds, UI art
│   ├── sounds/                            Theme song (MPEG)
│   └── video/frames/                      Intro animation — 80 PNG frames + WAV audio
│
├── data/
│   ├── questions/
│   │   ├── Class_Preschool/               Preschool_{Subject}.json × 5
│   │   ├── Class_Elementary/              Elementary_{Subject}.json × 5
│   │   ├── Class_MiddleSchool/            MiddleSchool_{Subject}.json × 5
│   │   ├── Class_HighSchool/              HighSchool_{Subject}.json × 5
│   │   └── Class_CollegePrep/             CollegePrep_{Subject}.json × 5
│   └── stories/
│       └── {Subject}_Stories.json         30 chapters × 5 subjects
│
├── saves/                                 Auto-generated JSON player profiles
└── CMakeLists.txt
```

</details>

---

## 🗂️ Key Source Files

| File | Role |
|:---|:---|
| `Game.cpp / hpp` | Main loop, state switching, shared player data |
| `TrainingState.cpp / hpp` | Core battle + question system |
| `BattleSystem.cpp / hpp` | Combat engine, damage calculation |
| `Character.cpp / hpp` | Player stats, XP, rarity tier system |
| `ElementSystem.cpp / hpp` | Elemental damage type multipliers |
| `ParticleSystem.cpp / hpp` | Visual particle burst effects |
| `ScreenShake.cpp / hpp` | Camera shake on damage |
| `Button.cpp / hpp` | Animated UI buttons with full state machine |
| `TrainingHubState.cpp / hpp` | Chapter / lesson selection hub |
| `LessonViewerState.cpp / hpp` | In-game educational content viewer |
| `SaveManager.cpp / hpp` | JSON save / load for player profiles |
| `ParallaxBackground.cpp / hpp` | Scrolling layered combat backgrounds |

---

## 💾 Save System

Player profiles live in `saves/` as human-readable JSON files. Each profile tracks:

- Player name, grade level, and selected subject
- Selected character and unlock status
- XP, level, and derived combat stats
- Streak history and battle performance
- Story chapter progress per subject

---

## 🗺️ Roadmap

- [ ] Full story mode — dialogue cutscenes and chapter-by-chapter boss progression
- [ ] Skill trees and card unlock reward system
- [ ] Statistics screen — performance tracking per subject and grade
- [ ] XP curve balancing across all 5 grade levels
- [ ] Per-element and per-action sound effects
- [ ] Boss battle visual sequences and special animations

---

## 👥 Credits

### Team

|     | Name               | Role                                                                                                                          |
| --- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| 🎨  | **Jatin Bhardwaj** | **Lead UI, UX & Gameplay Developer** — UI redesign, character systems, asset creation, interaction systems, gameplay presentation |
| ⚙️  | **Ishan**          | **Core Systems Developer** — backend architecture, game framework, state management                                           |
| 🛠️ | **Jishnu Kaushik** | **Gameplay Systems Developer** — TrainingState development, question integration, lesson systems                              |
| 🔊  | **Yuvraj Chillar** | **Audio Resources** — sound assets and audio resources                                                                        |
| 🎮  | **Aditya Sain**    | Team Member                                                                                                                   |

---

### Jatin Bhardwaj — Implemented Changes

**🎨 UI & Visual Redesign**

* Led the redesign and modernization of the game's visual presentation
* Redesigned the battlefield interface, HUD layout, question panels, answer panels, and combat presentation
* Improved visual consistency, readability, spacing, and overall user experience across multiple game states
* Refined menu layouts and presentation throughout the project

**🖱️ Mouse Interaction & Navigation Systems**

* Integrated mouse-based navigation across game interfaces that previously relied primarily on keyboard navigation
* Added hover detection, hover feedback, visual highlighting, and interactive UI behaviour
* Improved usability and responsiveness throughout menus and gameplay interfaces
* Converted multiple interfaces from keyboard-focused navigation to full mouse-supported interaction

**🎭 Character Selection System**

* Reworked and expanded the Character Selection System
* Implemented character card rendering and card asset integration
* Developed unlock systems and developer/demo mode functionality
* Improved character presentation, selection flow, and user interaction

**🖼️ Asset Creation & Integration**

* Designed and produced visual assets used throughout the project
* Designed and integrated custom character cards, battlefield artwork, UI assets, and visual themes used throughout the game
* Integrated character cards, UI artwork, battlefield backgrounds, menu assets, and presentation graphics
* Managed scaling, rendering, positioning, and asset pipeline implementation within the game

**⚔️ Battlefield & Gameplay Presentation**

* Redesigned combat UI presentation and HUD structure
* Reworked health bar presentation, battlefield layout, answer interfaces, and combat feedback systems
* Performed extensive iteration, testing, debugging, and visual improvements across gameplay systems

**🔧 Project Integration & Maintenance**

* Coordinated integration of visual systems with existing backend functionality
* Performed debugging, balancing, compatibility fixes, and gameplay polish
* Managed GitHub repository setup, version control, and project maintenance

---

### Jishnu Kaushik — Implemented Changes

* Development and expansion of TrainingState systems
* Question loading, processing, and educational content integration
* Lesson viewer functionality and training workflow implementation
* Supporting gameplay systems related to educational progression
* Training-related gameplay features and system integration

---

### Ishan — Implemented Changes

* Initial project architecture
* Core backend systems
* State management framework
* Fundamental gameplay infrastructure
* Base game systems and engine foundation



</details>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer" width="100%"/>

_Personal educational game project — All rights reserved_

</div>
