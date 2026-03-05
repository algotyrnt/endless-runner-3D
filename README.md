# Adventure Runner – 3D

An endless runner mobile game built with **Unity 3D**. Guide your character through a procedurally generated 3D track, dodge obstacles, collect coins, unlock new characters and maps, and compete for the highest score.

---

## Table of Contents

- [Gameplay Overview](#gameplay-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Opening the Project](#opening-the-project)
  - [Running the Game](#running-the-game)
- [Controls](#controls)
- [Progression System](#progression-system)
- [Scripts Overview](#scripts-overview)
- [Credits](#credits)

---

## Gameplay Overview

Adventure Runner – 3D is an infinite runner for mobile platforms. The player runs forward automatically along a procedurally-generated track. The speed increases over time, making the game progressively harder. Avoid boxes and rocks, collect coins, and aim for a new high score every run.

---

## Features

- **Procedural map generation** – track segments are spawned dynamically ahead of the player so the run never repeats.
- **Obstacle system** – randomly placed box and rock barriers that trigger different death animations.
- **Coin collection** – gather coins during a run; they carry over between sessions as your in-game currency.
- **Score system** – distance-based score that increases every second; high score is persisted across sessions.
- **Speed progression** – player and jump speed increase automatically every time the score crosses a milestone.
- **Character selection** – choose from four character color variants (Blue, Black, White, Red). Characters can be unlocked by spending coins.
- **Map selection** – Day and Night skybox maps; the Night map is unlockable via the in-game shop.
- **Level / rank system** – five ranks unlocked by reaching cash and high-score thresholds.
- **Main menu UI** – includes map picker, character picker, level tracker, high score display, and coin counter.
- **Ad integration** – Unity interstitial ads shown between sessions via `InterstitialAdsScript`.
- **Joystick input** – mobile virtual joystick (Joystick Pack) for movement and jumping.

---

## Project Structure

```
Assets/
├── Animations/         # Character and UI animation clips & controllers
├── Art By Kandles/     # Environment art assets
├── Barriers/           # Obstacle prefabs (boxes, rocks)
├── Footsteps - Essentials/ # Audio – footstep sounds
├── Img/                # UI sprites and icons
├── Joystick Pack/      # Virtual joystick asset
├── Lava/               # Lava/death-zone assets
├── Map/ & Maps/        # Map-related prefabs and materials
├── Player/             # Player model, materials, and prefabs
├── Scenes/
│   ├── MainMenu.unity  # Main menu scene
│   └── Game.unity      # Gameplay scene
├── Scripts/            # All C# game-logic scripts (see below)
├── SkyBox/             # Skybox materials (Day / Night)
├── Tex & Mat/          # Shared textures and materials
└── coins/              # Coin prefabs and related assets
```

---

## Getting Started

### Prerequisites

| Tool | Version |
|------|---------|
| [Unity Editor](https://unity.com/releases/editor/archive) | 2020.3 LTS or later (check `ProjectSettings/ProjectVersion.txt` for the exact version) |
| Android Build Support module | Required for Android builds |
| iOS Build Support module | Required for iOS builds |

### Opening the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/algotyrnt/endless-runner-3D.git
   ```
2. Open **Unity Hub**, click **Open**, and select the cloned project folder.
3. Unity will import all assets automatically on the first launch.

### Running the Game

1. In the Unity Editor, open `Assets/Scenes/MainMenu.unity`.
2. Press **Play** in the Editor toolbar to run the game in Play Mode.
3. To build for Android or iOS, go to **File → Build Settings**, select your target platform, and click **Build**.

---

## Controls

| Input | Action |
|-------|--------|
| Joystick **Up** (≥ 0.5) | Jump |
| Joystick **Left** (≤ -0.2) | Move left |
| Joystick **Right** (≥ 0.2) | Move right |

---

## Progression System

| Rank | Cash Required | High Score Required |
|------|--------------|-------------------|
| 1 | 500 | 500 |
| 2 | 1,000 | 1,000 |
| 3 | 5,000 | 5,000 |
| 4 | 10,000 | 10,000 |

**Unlockable items:**

| Item | Cost |
|------|------|
| Red / White / Black character skins | 1,000 coins each |
| Night map | 10,000 coins |

---

## Scripts Overview

| Script | Description |
|--------|-------------|
| `PlayerMovement.cs` | Handles player movement (forward run, lateral movement, jumping) and speed-up calls. |
| `MapGenerator.cs` | Spawns randomised track segments ahead of the player using a prefab list. |
| `SpawnBarriers.cs` | Randomly places an obstacle prefab on each new track segment. |
| `Dead.cs` | Manages the death state, shows the game-over panel, and triggers death animations. |
| `BoxDead.cs` / `RockDead.cs` | Collision detectors for box and rock obstacles. |
| `ScoreSystem.cs` | Tracks and displays the live score, updates the high score, and triggers speed increases. |
| `CountDown.cs` | Countdown timer at the start of each run. |
| `Game.cs` | Applies the selected map (skybox) and character skin at scene load. |
| `MainMenu.cs` | Controls the main-menu panels (map, character, level selection) and persists preferences. |
| `Level.cs` | Evaluates cash and high-score thresholds to advance the player's rank. |
| `Unlockable.cs` / `UnlockableObj.cs` | Handle purchasing and unlocking new characters and maps. |
| `ButtonManager.cs` | General button event handling. |
| `CameraControll.cs` / `CameraStable.cs` | Camera follow and stability logic. |
| `DeleteObj.cs` | Destroys old track segments that are behind the player. |
| `InterstitialAdsScript.cs` | Integrates Unity Ads interstitial ad placements. |

---

## Credits

- **Developer / Studio:** StudioPunjitha
- **Joystick asset:** Joystick Pack (Unity Asset Store)
- **Footstep audio:** Footsteps – Essentials
- **3D art:** Art By Kandles

