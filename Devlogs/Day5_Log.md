# Day 5 Progress Report: From Design to a Live iPhone Preview

## 📌 Executive Summary

Day 5 marked the transition from static design work to a running application. I initialized the **Expo** project `system-t-zero`, connected it to **EAS (Expo Application Services)**, and successfully rendered a multi-component React Native interface with a glassmorphic visual style on a physical iPhone using **Expo Go**.

This is an important milestone for **System: T-0**: the project is no longer just a set of Canva screens. There is now a working mobile app foundation that can be iterated on directly from a real device.

The setup was not frictionless. Windows PowerShell execution-policy errors, an Expo account/owner mismatch, missing UI dependencies, and incorrect component paths all had to be resolved. Cursor Agent helped reorganize the generated component files into the Expo app structure and clear the module-resolution errors.

**Today's outcome:** the Expo app runs on a physical iPhone through Expo Go, and the EAS project is linked. The next focus is replacing temporary emoji placeholders with a consistent set of custom RPG sprites and polished UI icons.

## 🏆 Core Achievement

- Initialized the Expo application as **`system-t-zero`**.
- Linked the project to **EAS** for the cloud build workflow.
- Installed the required UI dependencies, including blur and gradient support.
- Rendered a multi-component **React Native glassmorphic UI** on a physical iPhone using **Expo Go**.
- Established a working foundation for implementing the System: T-0 screens in code.

> **Milestone:** A real-device preview is working. EAS is linked, but a production build or store deployment has not yet been completed.

## 🧰 Tools & Environment

| Tool | Role in today's workflow |
|---|---|
| **Cursor IDE** | Main development environment for editing and managing the Expo project |
| **Cursor Agent** | Assisted with file organization, path corrections, and resolving module imports |
| **Claude AI** | Generated the initial React Native UI components and supporting theme files |
| **Expo Go** | Loaded and previewed the app on a physical iPhone |
| **EAS CLI** | Linked the local Expo project to its EAS cloud project |
| **Windows PowerShell** | Terminal used to initialize, configure, and run the project |
| **Bing Image Creator** | Planned asset-generation tool for RPG character sprites and UI icons |
| **remove.bg** | Planned background-removal step for transparent PNG assets |

## 💻 Commands & Environment

| Command | Purpose | Result |
|---|---|---|
| `npx create-expo-app system-t-zero` | Initialize the Expo application | Created the project |
| `npx eas-cli@latest init --id [project-id]` | Link the local project to its EAS cloud project | Linked successfully |
| `npx expo install expo-blur expo-linear-gradient react-native-safe-area-context @expo/vector-icons` | Install the UI dependencies required by the components | Resolved missing dependency issues |
| `npx expo start` | Start the Metro development server | Started the app preview workflow |

### Environment notes

- **IDE:** Cursor
- **Terminal:** Windows PowerShell
- **App framework:** Expo + React Native
- **Cloud project management:** EAS
- **Device preview:** Physical iPhone running Expo Go

## 🧩 Challenges & Solutions

### 1. Windows PowerShell execution-policy error

**Problem:** PowerShell blocked the `npx.ps1` script because of the current execution-policy configuration.

**Resolution:** Worked around the PowerShell script-launch restriction so the Expo commands could run from the terminal. This cleared the initial setup blocker.

### 2. Expo account mismatch

**Problem:** The project configuration did not match the Expo account being used, which prevented the EAS linking step from completing cleanly.

**Resolution:** Updated the `owner` property in `app.json` to match the correct Expo account, then continued with the EAS initialization.

### 3. Missing UI dependencies

**Problem:** The generated interface referenced packages that were not yet installed in the Expo project, including blur, gradients, safe-area handling, and icon components.

**Resolution:** Installed the required packages with `npx expo install`, allowing the UI components to resolve their dependencies.

### 4. Incorrect component directory structure

**Problem:** Claude's initial component files—such as `GlassCard.js` and `theme.js`—were not located where the Expo app expected to find them. This caused **Module Not Found** errors.

**Resolution:** Used Cursor Agent to map the component imports, move the raw files into the correct `src/app/` directory structure, and align the file locations with the app's imports.

**Result:** The module-resolution errors were cleared and the multi-component interface could render on the iPhone.

## 🎨 Next Steps: Asset Creation Pipeline

The current interface still uses temporary emoji placeholders in places where the final art should appear. The next asset pass will give System: T-0 a more cohesive RPG identity.

Planned workflow:

1. Use **Bing Image Creator** to generate 16-bit RPG character sprites and 3D glossy UI icons.
2. Generate the assets on solid white backgrounds to make the subjects easier to isolate.
3. Batch-process the images through **remove.bg** to remove the white backgrounds.
4. Export the results as transparent PNG files.
5. Organize the assets in the app and replace the temporary emoji placeholders with the finished artwork.
6. Preview the updated screens again on the physical iPhone using Expo Go.

## 🔄 Visual Pipeline: Design, Assets & Deployment

The diagram below maps the intended end-to-end workflow. The app preview and EAS project link are complete; cloud builds and store deployment remain future steps.

```text
                    SYSTEM: T-0
                 DEVELOPMENT PIPELINE
                           |
             +-------------+-------------+
             |                           |
        UI IMPLEMENTATION           ASSET CREATION
             |                           |
       Claude AI components        Bing Image Creator
             |                           |
       Cursor IDE / Agent          RPG sprites + 3D icons
             |                           |
       Expo project structure      Solid white backgrounds
             |                           |
       React Native UI             remove.bg processing
             |                           |
       Glassmorphic screens        Transparent PNG assets
             |                           |
             +-------------+-------------+
                           |
                    INTEGRATION
                           |
               Replace emoji placeholders
                           |
                 Expo Go on iPhone
                           |
                  Real-device testing
                           |
                 +---------+---------+
                 |                   |
             ITERATION           EAS CLOUD
                 |                   |
          UI / asset fixes       Cloud build
                 |                   |
          Test again on iPhone   Build validation
                                     |
                              STORE PREPARATION
                                     |
                              iOS release process
```

## 📍 Status & Next Milestones

| Workstream | Day 5 status | Next milestone |
|---|---|---|
| Expo app initialization | ✅ Complete | Continue feature implementation |
| EAS project linking | ✅ Complete | Configure and run a cloud build |
| Required UI dependencies | ✅ Installed | Add dependencies as new features require |
| Glassmorphic UI preview | ✅ Running on physical iPhone | Refine layout and interactions |
| Component file structure | ✅ Organized | Keep imports and folders consistent |
| Custom RPG sprites | 🔜 Planned | Generate and process transparent assets |
| Glossy UI icon set | 🔜 Planned | Generate, remove backgrounds, and integrate |
| Production/store deployment | ⏳ Not started | Validate builds and prepare the iOS release |

## 📝 Day 5 Takeaway

Today was about getting the foundation running—not just making the code compile, but seeing the interface on an actual iPhone. The setup issues took time, but each fix moved the project closer to a repeatable development workflow.

**Next focus:** build the visual identity with custom RPG sprites and glossy icons, integrate those assets into the existing React Native UI, and continue testing on-device.

**Day 5 status:** Expo app initialized, EAS linked, and glassmorphic UI successfully previewed on a physical iPhone.