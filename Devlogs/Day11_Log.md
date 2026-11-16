# Day 11 — Profile Functionality & Character Asset Preparation

## Overview

Day 11 focused on making the Profile screen more interactive and preparing the character artwork for a future modular customization system.

## Completed and tested

- Implemented the Edit Name flow on the Profile screen using a modal and text input.
- Verified that the name can be changed, saved, reopened and cancelled on an iPhone using Expo Go.
- Restored gender selection in the Edit Profile flow with these options: Male, Female, Non-binary, Transgender, Others and Prefer not to say.
- Connected Male to the Leonhart character and Female to Emilia.
- Added a third **Coming Soon** carousel placeholder for the remaining gender options.
- Kept manual carousel navigation available across the three slides.
- Corrected the Emilia image mapping using the existing asset file: `assets/Characters/Male & female/Emilia (Female).webp`.
- Tested the two character images, carousel arrows and Edit Profile flow on the iPhone.

## Character asset preparation

Prepared separate face and hair artwork folders for male and female characters. Several hair variations are available, and face assets have been prepared separately.

Clothing artwork is available with arms and legs attached, but clothing customization is planned as premium content for a later stage.

## Important technical decision

The current character artwork is being moved toward a modular, layered setup. Face and hair customization are the initial priorities. The assets still need alignment checks, consistent canvas sizing and in-app compositing before the customization feature can be considered implemented.

## Not completed yet

- Face and hair layer alignment and integration in the React Native app.
- Functional Hair and Face customization controls.
- Clothing and weapon customization.
- Persistent storage for edited profile name and gender selection.

## Next steps

1. Inspect the prepared face and hair assets for canvas size, transparency and alignment.
2. Build a controlled layered preview for Leonhart first.
3. Verify that changing hair or face does not shift the rest of the character.
4. Repeat the process for Emilia.
5. Implement the initial Face and Hair selection UI after the assets align correctly.

## Day 11 outcome

The Profile screen has working name editing, gender selection and a three-slide character carousel, tested on a physical iPhone. The next phase is asset alignment and modular character rendering—not yet full customization.

---
*System: T-0 — Development log*
