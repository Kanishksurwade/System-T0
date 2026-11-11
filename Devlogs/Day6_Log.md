# Day 6: Asset Integration & The AI Tooling Roadblock

## 📌 Executive Summary

Day 6 focused on preparing the visual identity of **System: T-0** and attempting to move the interface closer to its final asset-driven design.

The primary achievement reported today was generating, removing backgrounds from, and organizing the main gamified art assets: characters, faces, icons, weapons, and clothing. The goal is to replace temporary emoji placeholders with real visual assets.

Progress on direct implementation was limited by AI coding-tool constraints. Cursor's premium Agent allowance was exhausted after one prompt, and clearing the Expo cache with `npx expo start -c` did not address the limitation. This exposed a practical issue with relying on premium autonomous agents for large file-manipulation tasks under limited free-tier usage.

The decision for now is to pause heavy AI-agent-driven coding and evaluate more sustainable options: alternative IDEs such as Windsurf or a more manual React Native workflow.

> **Day 6 status:** Asset preparation and organization progressed locally. Further UI integration is reported, but the updated source files and image assets were not available in the connected GitHub repository at the time this log was published, so those changes are not represented here as verified repository changes.

## 🎨 1. Asset Preparation

The reported asset work covered the main visual categories needed for the gamified interface:

| Asset category | Reported work |
|---|---|
| Characters | Generated and background-removed character assets |
| Faces | Prepared face/avatar assets |
| Icons | Prepared custom UI icon assets |
| Weapons | Prepared weapon artwork |
| Clothes | Prepared clothing artwork |

**Tools used:** ChatGPT Image Generation and remove.bg.

The assets were organized in the local project structure with the intention of bundling them into the Expo application as transparent PNGs.

## 🧩 2. UI Refactoring Attempts

The reported UI work focused on moving away from emoji placeholders and improving visual consistency:

- Attempted to update `src/screens/ProfileScreen.js` to use local image assets.
- Changed the Stamina bar color from purple to blue.
- Adjusted `BottomTabBar` spacing so the active capsule background would not overlap neighboring icons.
- Used local image references in the form `require('../assets/images/filename.png')`.
- Adjusted Flexbox spacing properties such as `gap` and `paddingHorizontal`.

These edits were described in the daily handoff, but the source files were not present in the connected repository tree. They therefore remain **reported local changes, not verified GitHub changes**.

## 🛠️ 3. Tools & Workflow

| Tool | Intended role |
|---|---|
| **ChatGPT Image Generation** | Generate gamified visual assets |
| **remove.bg** | Remove backgrounds and prepare transparent PNGs |
| **Cursor (Grok 4.7)** | AI-assisted code editing and file manipulation |
| **Claude** | Coding assistance and implementation support |
| **Expo CLI** | Run and troubleshoot the Expo development workflow |

## 🚧 4. Challenges & Solutions

### Cursor Agent usage limit

**Problem:** Cursor's premium Agent limit was exhausted after one prompt, interrupting the planned AI-assisted file manipulation.

**Attempted troubleshooting:** Ran `npx expo start -c` to clear the Expo/Metro cache.

**Outcome:** Clearing the cache did not bypass the Agent usage restriction. The issue was a tooling allowance limit, not an Expo cache problem.

### A more sustainable development workflow

This experience highlighted a dependency risk: heavy file manipulation through premium AI agents can become unsustainable when free-tier or prompt allowances are limited.

**Decision:** Pause direct coding that depends on premium autonomous agents and evaluate alternatives:

1. Research free or more accessible AI-assisted IDEs, including Windsurf.
2. Consider a manual React Native learning path to reduce dependency on paid agents.
3. Use AI assistance selectively for focused tasks rather than making it the only way to edit or organize the codebase.

## 📍 5. Next Steps

| Priority | Next action | Purpose |
|---|---|---|
| 1 | Evaluate Windsurf and other IDE options | Find a sustainable coding environment |
| 2 | Consider structured React Native learning | Build the ability to debug and edit code independently |
| 3 | Verify local asset paths and imports | Ensure generated PNGs are correctly referenced by Metro |
| 4 | Revisit Profile and Bottom Tab UI changes | Confirm the local image integration and layout adjustments |
| 5 | Upload verified source and asset changes to GitHub | Make the local implementation reproducible and reviewable |

## 🔄 6. Day 6 Workflow Snapshot

```text
             SYSTEM: T-0 — DAY 6
                       |
             +---------+---------+
             |                   |
        ASSET CREATION       UI REFACTOR ATTEMPT
             |                   |
       ChatGPT Image Gen    ProfileScreen.js
             |              BottomTabBar.js
        remove.bg                 |
             |             Local image references
       Transparent PNGs      Spacing / color tweaks
             |                   |
       Local organization         |
             |                   |
             +---------+---------+
                       |
                CODING TOOL LIMIT
                       |
             Cursor Agent allowance
                  exhausted
                       |
             Cache clear did not help
                       |
              WORKFLOW REASSESSMENT
                       |
           +-----------+-----------+
           |                       |
       Evaluate IDEs         Learn React Native
        (Windsurf)           more independently
```

## 📝 Day 6 Takeaway

Today was a reminder that a productive development setup needs to be sustainable, not just powerful. Custom assets are an important step toward the intended look of System: T-0, but implementation cannot depend entirely on limited premium AI-agent usage.

The next phase is about choosing a workflow that keeps progress moving while building enough React Native knowledge to stay in control of the codebase.

**Day 6 outcome:** Asset preparation progressed locally; AI-agent limits exposed a workflow bottleneck; tooling strategy is being reassessed.
