# Day 12 — Leonhart Layer Alignment Inspection & Customization Planning

> **Project:** System: T-0  
> **Work area:** Character asset preparation and Profile customization architecture  
> **Target character:** Leonhart  
> **Asset template:** 1199 × 1312 px  
> **Documentation status:** Based on the image-inspection report and planning decisions shared during Day 12. No application code was changed or tested on-device today.

## 1. Executive Summary

Day 12 focused on preparing the next phase of System: T-0's character customization system. The goal is to move from a single flattened character image to a modular character made from independent transparent layers.

The inspected Leonhart base, male face and red hair images were reported to share the same 1199 × 1312 px canvas. Their visible content bounds were measured, and a preliminary composite was inspected. The report indicated that the face covers the bald head and the hair sits above the eyebrows in the expected position.

This is a promising alignment result, but it is not yet a verified in-app result. No code was changed, no Expo Go test was performed, and the layered character has not yet been approved for implementation.

## 2. Image Inspection Findings

| Layer | Canvas size | Transparency | Reported visible bounds |
|---|---:|---|---|
| Leonhart base | 1199 × 1312 | Yes | x 442–739, y 302–599 (head area) |
| Male face | 1199 × 1312 | Yes | x 453–760, y 309–527 |
| Red hair | 1199 × 1312 | Yes | x 388–811, y 125–417 |

The inspection report states that all three images use the same canvas dimensions and that a preliminary stack (base → face → hair) appears aligned.

### Items to watch during the eventual phone test

- The hair is partially translucent in many pixels (reported opacity around 80–99%), so the underlying skin may show through faintly.
- Small black specks are visible around the face asset's edge.
- The face chin may overlap a small part of the blue collar.

These were recorded as visual checks, not reasons to edit the assets immediately. The plan is to preserve the current originals until the first app preview is evaluated.

## 3. Current App Architecture

The inspected code files were reported to work as follows:

- `src/screens/ProfileScreen.js` supplies the carousel slides. Leonhart currently uses the existing flattened character image.
- `src/components/AvatarCarousel.js` currently renders one image per slide.
- `assets/profileImages.js` stores static image imports.
- `package.json` identifies the current Expo / React Native project setup; no new dependency was considered necessary for the proposed layer stack.

The proposed implementation is intentionally small and limited to three files:

1. **`assets/profileImages.js`** — register the base, face and hair images.
2. **`src/components/AvatarCarousel.js`** — add support for rendering a stack of image layers while preserving the existing single-image and placeholder behaviour.
3. **`src/screens/ProfileScreen.js`** — change only Leonhart's slide to use the three layers.

This is a proposal only. None of these edits was applied on Day 12.

## 4. File Identity Check Still Required

Before implementation, the actual files on disk must be confirmed to be the same aligned versions that were inspected:

- `assets/Characters/Male & female/Leonhart_Base.png`
- `assets/Face/male faces/Male_Face_1.png`
- `assets/Hairs/Male hair/Red Hair.png`

There were earlier filename variations in the conversation, so exact local filenames and file identity must be checked before adding static `require()` imports. The older flat Leonhart image should remain available as a rollback option.

## 5. Decisions and Scope Boundaries

- Start with **Leonhart only**.
- Use one face and one hair asset for the first proof of concept.
- Leave Emilia on her existing flat image.
- Do not modify the artwork until the alignment and in-app result are evaluated.
- Do not touch the Edit Name modal, gender selection, carousel navigation, stats, or other working Profile features.
- Do not implement clothes, weapons, premium rules, or additional customization categories in this phase.
- Do not install new packages unless a genuine requirement appears.

The intended layer order is:

```text
Leonhart base
    ↓
Male face
    ↓
Red hair
    ↓
Layered character preview
```

## 6. Why the Work Was Paused

Claude 1's free-message limit was reached and its interface showed that messaging would resume the following day at 2:30 AM. The decision was to continue image preparation after the limit resets rather than rush into code changes with assets that may still need alignment work.

Claude 2's earlier inspection proposed the three-file implementation, but the team will not proceed with those edits until the image files and their exact on-disk paths are confirmed.

## 7. Verification Status

| Item | Day 12 status |
|---|---|
| Three image dimensions inspected | Reported as 1199 × 1312 |
| Transparent backgrounds | Reported present |
| Preliminary layer alignment | Visually inspected in the report; not yet tested in app |
| Local file identity and exact paths | Confirmation still required |
| Image asset modifications | None |
| Code modifications | None |
| Expo Go device test | Not performed |
| Leonhart layered preview in app | Pending |
| Emilia customization | Out of scope for this first test |

## 8. Next Session Plan

1. After Claude 1's message limit resets, upload the original male face and hair files in manageable batches (about six at a time).
2. Have the image assets aligned to the fixed 1199 × 1312 template without redesigning the pixel art.
3. Preserve backups and verify the returned PNGs and exact filenames.
4. Confirm the three local file paths.
5. Only then make the first small code edit in `assets/profileImages.js`.
6. Test incrementally before changing `AvatarCarousel.js` and then Leonhart's slide in `ProfileScreen.js`.

## 9. Day 12 Outcome

Day 12 established a measured, limited plan for the first layered Leonhart preview. The shared canvas size and preliminary alignment are encouraging, and the remaining visual issues have been documented for testing.

**Day 12 status:** Image inspection and implementation planning completed; asset identity confirmation, code integration and on-device validation remain pending.

---
*System: T-0 — Development log*
