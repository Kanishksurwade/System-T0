# Day 13 — Character Asset Preparation

**Project:** System: T-0  
**Date:** 18 November 2026  
**Focus:** Male and female character assets, transparency, and layer alignment

## Daily Summary

Today’s work focused on preparing the character artwork so the app can support modular customization. The male character’s face and hairstyle assets were prepared and aligned. The female character’s assets were also prepared, including a bald base for the second female character, Mia. Hair and face assets for both male and female characters were made ready for the next coding stage.

The work involved careful image editing, removing backgrounds, creating clean transparent PNG assets, and matching the position and scale of the layers so they can stack correctly over each character base.

## Progress Overview

| Area | Day 13 result |
|---|---|
| Male character | Face and hairstyle assets prepared and aligned |
| Female character | Face and hairstyle assets prepared and aligned |
| Second female character | Mia’s base character prepared |
| Character bases | Bald bases prepared for separate face and hair layers |
| Transparency | Backgrounds removed; transparent assets prepared |
| Layer alignment | Face and hair positions adjusted to match the character bases |
| App integration | Assets prepared for the next coding and in-app testing stage |

## Technical Workflow and Code Context

The asset preparation was done using image-editing tools, including Photopea, with transparent PNG output and consistent canvas positioning as the key requirements.

The existing React Native / Expo layered-character implementation provides the code context for the next integration step:

| File | Responsibility |
|---|---|
| `assets/profileImages.js` | Registers image assets used by the app |
| `assets/characterLayers.js` | Defines character layer asset mappings |
| `src/components/LayeredCharacter.js` | Renders the character from stacked image layers |
| `src/components/AvatarCarousel.js` | Displays character slides in the profile carousel |
| `src/components/PartPickerModal.js` | Provides the face and hair selection interface |
| `src/screens/ProfileScreen.js` | Connects the character preview and customization controls |

**Code status:** No new code changes are recorded for Day 13. Today’s focus was asset creation, cleanup, transparency, and alignment. The prepared female assets and completed male assets are ready to be connected and tested through the existing layered-character flow.

## Key Quality Checks for Integration

- Keep the same canvas dimensions and character position across each base and its face/hair layers.
- Preserve genuine alpha transparency; do not leave a black or checkerboard background baked into the PNG.
- Keep the original pixel-art outlines, colors, and proportions.
- Test each character in the app before adding more customization options.

## Next Steps

1. Integrate the prepared male and female assets into the existing asset map.
2. Set sensible default face and hair selections for each character.
3. Test every hair and face option in the Profile screen on Expo Go.
4. Fix any visible alignment, overlap, or transparency issues before expanding to clothes and weapons.

## Day 13 Outcome

**Asset preparation completed; app integration and device testing are the next stage.**

The main achievement today was getting both male and female character assets ready for modular customization without changing the existing Profile screen functionality.
