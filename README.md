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
    └── Day17_Log.md
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

## Current Milestones

- **Profile:** first functional screen completed; character and profile experience tested.
- **Calendar:** completed for the current scope and confirmed working by the user on iPhone.
- **Goals, Widgets and Shop:** navigation destinations exist, but their full feature sets remain future work.
- **Progression:** initial progress architecture exists; the complete goal-to-reward loop still needs integration and validation.
- **Premium:** UI entry and popup are prototypes; live purchase/subscription integration is not claimed.

## Next Priorities

1. Define the minimum complete user journey across the remaining core screens.
2. Build and test the Goals experience and connect task completion to shared progression.
3. Validate persistence for all user-critical data, not only Calendar tasks.
4. Develop progression and rewards only after their rules are clearly defined.
5. Add optional features after the core experience is reliable and easy to use.

## Project Principles

- **Simple to use:** essential actions should be obvious, even to a first-time user.
- **Incremental development:** prefer focused changes over broad rewrites.
- **Preserve working features:** regression-test existing screens after changes.
- **Device-first validation:** do not mark features complete based only on syntax checks.
- **Accurate documentation:** clearly separate tested features from prototypes and plans.
- **Sustainable workflow:** retain project decisions outside individual AI chats.

---

*System: T-0 is a work in progress. Product scope, visuals and technical architecture may evolve as implementation and testing continue.*
