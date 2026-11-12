# System: T-0

> A gamified personal productivity and daily-planning app built around RPG-inspired progression.

System: T-0 is being developed as a mobile application that turns everyday goals and routines into a game-like progression experience. The product direction combines a character profile, quests/goals, streaks, rewards, health and stamina indicators, and a custom visual identity.

## Project Status

**Development stage:** Active prototype / UI implementation

The project has progressed from initial concept and visual design into a working Expo + React Native application previewed on a physical iPhone through Expo Go. The Profile screen is being refined with custom character and interface assets.

This repository currently serves as the project's documentation and development-log repository. The local application source and complete asset library are not yet represented here, so this README does not claim that the repository itself contains a reproducible app build.

## Product Direction

| Area | Intended experience |
|---|---|
| Profile & character | A player profile with a customizable RPG character, class, level and rank |
| Goals / quests | Everyday tasks presented as goals that contribute to progression |
| Streaks | Consecutive-day progress with visual reward tiers |
| Rewards & coins | Earned in-app currency linked to completed goals |
| Health & stamina | Game-inspired progress indicators |
| Customization | Hair, face, clothing and weapon appearance options |
| Shop & premium | Earnable items alongside premium-locked content (monetization design remains future work) |
| Calendar & widgets | Daily planning and at-a-glance progress surfaces |

These are product goals and planned capabilities; individual features may still be under design or implementation.

## Current Technology Direction

| Technology / Tool | Role |
|---|---|
| Expo | React Native application development and device preview |
| React Native | Cross-platform mobile UI |
| Expo Router | Application navigation foundation |
| EAS (Expo Application Services) | Expo project/build-service integration |
| Expo Go | Preview and test the app on a physical iPhone |
| Cursor | Local code editor |
| Claude / ChatGPT | AI-assisted implementation, code review and documentation |
| Canva | UI concept and visual design work |

The local project has been reported as using Expo SDK 58. Verify the current local `package.json` before relying on exact dependency versions.

## Visual Direction

The current design direction includes:
- Glassmorphism-inspired cards and soft gradient backgrounds.
- Pixel-art RPG character artwork.
- Custom PNG badges and stat icons.
- A profile experience centered around the character **Leonard**.
- A modular customization menu for Hair, Face, Clothes and Weapon.

## Development Workflow

The current workflow is intentionally incremental:

1. Inspect the existing component and asset paths.
2. Define one focused change.
3. Generate or review the code with an AI assistant.
4. Apply the change manually in Cursor.
5. Save and run the Expo app.
6. Verify the result on a physical iPhone using Expo Go.
7. Record verified progress and unresolved issues in the daily development log.

This approach helps keep changes understandable and reduces unnecessary rewrites.

## Repository Structure

```text
System-T0/
└── Devlogs/
    ├── Day1_Log.md
    ├── Day2_Log.md
    ├── Day3_Log.md
    ├── Day4_Log.md
    ├── Day5_Log.md
    ├── Day6_Log.md
    └── Day7_Log.md
```

> The tree above describes the documentation currently tracked in this repository. The working Expo app and local asset folders are maintained separately at this stage.

## Development Log

| Day | Focus | Summary |
|---|---|---|
| [Day 1](Devlogs/Day1_Log.md) | Product concept | Initial System: T-0 idea and core direction |
| [Day 2](Devlogs/Day2_Log.md) | Product and UI planning | Early interface and feature planning |
| [Day 3](Devlogs/Day3_Log.md) | AI tooling experiments | OmniRoute / coding workflow exploration |
| [Day 4](Devlogs/Day4_Log.md) | Visual design | Canva UI design and native-app direction |
| [Day 5](Devlogs/Day5_Log.md) | App foundation | Expo setup, EAS linking and first physical-device preview |
| [Day 6](Devlogs/Day6_Log.md) | Asset preparation | Character/icon asset preparation and coding-tool bottlenecks |
| [Day 7](Devlogs/Day7_Log.md) | Profile UI refinement | Custom asset integration, layout adjustments and Metro path troubleshooting |

## Current Priorities

1. Complete the Profile screen's crown and streak-icon presentation.
2. Verify streak artwork tier selection against the intended duration rules.
3. Confirm all local static asset paths and final Profile layout on device.
4. Continue implementing character customization in small, testable steps.
5. Bring the local application source and required assets into a reproducible repository structure when ready.

## Build & Run

The Expo application source is currently maintained locally and is not yet included in this documentation repository. Once the app source is added, this section should be updated with the verified installation, environment and run commands from the actual project.

For now, consult the [development logs](Devlogs/) for the recorded setup history and implementation progress.

## Project Principles

- **Incremental development:** prefer focused, reviewable changes over large rewrites.
- **Visual consistency:** use a coherent custom RPG asset system.
- **Device-first validation:** verify important UI changes on a real device.
- **Accurate documentation:** distinguish implemented, tested, planned and unverified work.
- **Sustainable tooling:** avoid depending entirely on limited premium AI-agent usage.

---

*System: T-0 is an active work in progress. Features, visuals and technical architecture may change as implementation and testing continue.*
