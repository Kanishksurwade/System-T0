# System: T-0

> A gamified personal productivity app that turns everyday goals into an RPG-inspired journey.

System: T-0 is an active mobile-app project built with Expo and React Native. Its product direction combines daily planning, quests, character customisation, progression, rewards and a distinctive visual identity.

## Project Status

**Stage:** Active prototype with Profile and Calendar screens implemented and tested on a physical iPhone through Expo Go.

This repository is currently the project's documentation and development-log repository. The working application source and complete asset library are maintained locally and are not included here. Development logs distinguish implemented, tested, planned and unverified work.

## Product Direction

| Area | Intended experience |
|---|---|
| Profile & character | Player identity, character selection and customisation |
| Goals / quests | Simple daily tasks that contribute to progress |
| Calendar | Date-based planning, task completion and history |
| Progression | Levels, streaks, XP and rewards |
| Health & stamina | Game-inspired progress indicators |
| Customisation | Character appearance, clothing and equipment |
| Widgets & Shop | At-a-glance information and item catalogue |
| Settings & Premium | Preferences and future premium access |

Some areas remain planned or under development; a visible navigation item does not necessarily mean its full feature is implemented.

## Technology & Workflow

| Tool | Role |
|---|---|
| Expo / Expo Router | App runtime and navigation |
| React Native / JavaScript | Mobile UI and application logic |
| AsyncStorage | Local persistence for Calendar tasks |
| Expo Go | Physical-device preview and testing |
| Cursor | Local code editor; changes are applied manually |
| Claude / ChatGPT | Focused code generation, review and technical planning |
| Photopea / Canva | Asset preparation and visual design |

The local project has been reported as using Expo SDK 58 and React Native 0.88.1. Check the local `package.json` before relying on exact versions.

### Development workflow

1. Inspect the current file and relevant assets.
2. Agree on one focused change.
3. Generate or review the proposed code.
4. Apply changes manually in Cursor.
5. Run the app from the project root.
6. Test on the iPhone using Expo Go.
7. Record the verified result and remaining work.

## Repository Structure

```text
System-T0/
├── README.md
└── Devlogs/
    ├── Day1_Log.md
    ├── ...
    ├── Day17_Log.md
    ├── Day18_Log.md
    ├── Day19_Log.md
    └── Day20_Log.md
```

The app source and assets are maintained separately in the local project at this stage.

## Development Log

| Day | Focus | Outcome |
|---|---|---|
| [Day 1](Devlogs/Day1_Log.md) | Product concept | Initial idea and direction |
| [Day 2](Devlogs/Day2_Log.md) | Product and UI planning | Early feature and interface planning |
| [Day 3](Devlogs/Day3_Log.md) | AI tooling | Coding workflow experiments |
| [Day 4](Devlogs/Day4_Log.md) | Visual design | Initial visual design work |
| [Day 5](Devlogs/Day5_Log.md) | App foundation | Expo setup and device preview |
| [Day 6](Devlogs/Day6_Log.md) | Asset preparation | Character and icon assets |
| [Day 7](Devlogs/Day7_Log.md) | Profile UI | Profile refinement and setup troubleshooting |
| [Day 8](Devlogs/Day8_Log.md) | Retrospective | Placeholder pending verified notes |
| [Day 9](Devlogs/Day9_Log.md) | Retrospective | Placeholder pending verified notes |
| [Day 10](Devlogs/Day10_Log.md) | Retrospective | Placeholder pending verified notes |
| [Day 11](Devlogs/Day11_Log.md) | Profile & character assets | Name, gender selection and character options |
| [Day 12](Devlogs/Day12_Log.md) | Character-layer planning | Asset inspection and customization planning |
| [Day 13](Devlogs/Day13_Log.md) | Character asset preparation | Male and female face/hair asset preparation |
| [Day 14](Devlogs/Day14_Log.md) | Asset diagnosis | Face alignment investigation and correction |
| [Day 15](Devlogs/Day15_Log.md) | Customization redesign | Shift to pre-composed character artwork |
| [Day 16](Devlogs/Day16_Log.md) | Profile milestone | Functional Profile UI, character catalogue and progress foundation |
| [Day 17](Devlogs/Day17_Log.md) | Calendar milestone | Bulk tasks, sorting, clearing, persistence, history indicators and device testing |
| [Day 18](Devlogs/Day18_Log.md) | Widgets planning | Researched widget concepts and set a Windows/Expo implementation direction |
| [Day 19](Devlogs/Day19_Log.md) | Rest day | No app development work recorded |
| [Day 20](Devlogs/Day20_Log.md) | Rest day | No app development work recorded |
| [Day 21](Devlogs/Day21_Log.md) | Widget Store and Android checks | First Widget Store visual and Android testing |
| [Day 22](Devlogs/Day22_Log.md) | Streak Guardian design | Finalized three voxel companion moods and documented shared-progress integration plan |

## Current Milestones

- **Profile:** first functional screen completed; character and profile experience tested.
- **Calendar:** completed for the current scope and confirmed working by the user on iPhone.
- **Goals, Widgets and Shop:** navigation destinations exist, but their full feature sets remain future work.
- **Progression:** initial progress architecture exists; the complete goal-to-reward loop still needs integration and validation.
- **Premium:** UI entry and popup are prototypes; live purchase/subscription integration is not claimed.

## Current Development Starting Point — Day 23

The next session resumes from Day 22. The Streak Guardian visual direction is finalized for this iteration: one voxel companion with happy, neutral, and sleepy moods; a fire icon and streak count; and a seven-day MON–SUN completion row. The design intentionally excludes progress bars, percentages, extra descriptions, and unnecessary controls.

The next engineering task is to inspect the local task and progress architecture before implementing synchronization. Calendar task records should remain the single source of truth for Goals, Profile, progression, and Streak Guardian. Do not create separate counters for each screen. Confirm the exact empty-day and late-evening mood rules before coding. The Day 22 log records what is designed, what remains unverified, and the required test plan.

Native iOS widgets remain a later technical investigation because the current development environment is Windows with Expo/React Native; native iOS widget build/signing workflows require a macOS/Xcode path or a suitable cloud Mac service.

## Next Priorities

1. Inspect the current local app structure and shared data before changing code.
2. Build the first minimal in-app Widgets screen and test it on iPhone through Expo Go.
3. Reuse existing task, streak and character data rather than creating duplicate systems.
4. Inspect and unify task-to-progress calculations so Calendar, Goals, Profile, and Streak Guardian stay synchronized.
5. Integrate the three mascot mood assets and test task completion, undo, clearing, app restart, and date rollover.
6. Add optional features only when they strengthen the core experience without clutter.

## Project Principles

- **Simple to use:** essential actions should be obvious, even to a first-time user.
- **Incremental development:** prefer focused changes over broad rewrites.
- **Preserve working features:** regression-test existing screens after changes.
- **Device-first validation:** do not mark features complete based only on syntax checks.
- **Accurate documentation:** clearly separate tested features from prototypes and plans.
- **Sustainable workflow:** retain project decisions outside individual AI chats.

---

*System: T-0 is a work in progress. Product scope, visuals and technical architecture may evolve as implementation and testing continue.*
