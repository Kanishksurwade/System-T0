# Day 22 — Streak Guardian Design Finalization

**Project:** System: T-0  
**Date:** 27 November 2026  
**Focus:** Streak Guardian visual design, voxel companion moods, and shared progress planning  
**Status:** Visual direction finalized; code integration and device validation remain pending

## Daily Summary

Day 22 focused on turning the Streak Guardian from an early widget idea into a clearer visual direction. We reviewed the earlier widget concepts, explored a voxel-style companion, generated multiple visual iterations, and finalized three companion mood designs for the same widget layout.

The design keeps the experience focused: a prominent fire icon and streak count, one voxel companion, and a seven-day completion row. The weekday labels use short readable forms (MON, TUE, WED, THU, FRI, SAT, SUN). The design avoids extra progress bars, percentages, unnecessary descriptions, and additional controls.

We also discussed how this visual should eventually reflect real task activity across Calendar, Goals, Profile, and the Widgets screen. That integration is an architectural requirement, not a completed implementation.

## Work Completed Today

| Area | Work completed | Status |
|---|---|---|
| Widget concept | Refined Streak Guardian into a minimal streak-first layout | Design finalized |
| Companion style | Chose a voxel NPC companion, separate from the player's main character | Design direction selected |
| Mood artwork | Created happy, neutral, and sleepy visual variations using the same character concept | Visual assets prepared by the user |
| Layout iterations | Reviewed and iterated on generated widget visuals to improve consistency | Reviewed |
| Weekday labels | Specified MON–SUN labels instead of single-letter abbreviations | Final design requirement |
| Functional planning | Defined the need to derive streak and mood from real task history | Planned; not integrated |
| Technical review | Identified progress persistence and task-to-streak synchronization as areas needing careful review | Investigation required |

## Final Streak Guardian Design

The three mood states use one consistent voxel companion. Only the expression and pose should change; the widget layout, character proportions, lighting, background, and placement should remain consistent.

| Mood | Intended meaning | Visual direction |
|---|---|---|
| Happy | Today's task target is completed | Cheerful expression and upbeat pose |
| Neutral | Tasks remain unfinished and the day is still in progress | Calm, neutral expression |
| Sleepy | The day has been missed or the agreed sleepy condition is met | Sleepy expression and relaxed pose |

**Important:** The exact rule for an empty day and the late-evening cutoff still needs a final product decision and implementation test. The current discussion included an 8:00 PM cutoff as a configurable proposal, not a verified rule.

## Widget Layout

    ┌─────────────────────────────────────────────────────┐
    │                                                     │
    │   🔥  12 DAYS                         [VOXEL NPC]   │
    │                                                     │
    │  ┌───────────────────────────────────────────────┐  │
    │  │   MON   TUE   WED   THU   FRI   SAT   SUN     │  │
    │  │    ✓     ✓     ×     ✓     ✓     ✓     ○      │  │
    │  └───────────────────────────────────────────────┘  │
    │                                                     │
    └─────────────────────────────────────────────────────┘

The illustration above is a structural reference only. It is not a production screenshot and does not represent live app data.

## Mood Selection Flow

    [Read real task history]
                |
                v
       [Select today's tasks]
                |
                v
       {Is today's target complete?}
             /             \
           Yes              No
            |                |
            v                v
     [Happy companion]  {Sleepy condition met?}
                            /          \
                          Yes           No
                           |             |
                           v             v
                    [Sleepy mood]  [Neutral mood]
                           \             /
                            v           v
                     [Render streak and
                      weekly completion]

The chart describes the intended decision flow. The exact success threshold and sleepy condition must be implemented against the agreed product rules before this can be treated as live behaviour.

## Shared Data Requirement

The Calendar should remain the source of truth for dated tasks. Goals, Profile, progression, and Streak Guardian should read derived information from the same shared task data rather than maintain separate completion or streak counters.

    [Calendar task records]
              |
              v
    [Shared task + progress logic]
       /       |       |       \
      v        v       v        v
   [Goals] [Profile] [Streak] [Weekly history]
      |
      v
 [User completes or undoes a task]
      |
      └──────────────> [Calendar task records]

This is the target architecture. It is not yet confirmed as implemented. The next code review must inspect the current providers, task model, progress helpers, and app root before making changes.

## Technical Findings to Carry Forward

The earlier review of the progress files reported these risks:

1. Progress state was not persisted across app restarts.
2. The existing streak callback was not connected to Calendar task completion.
3. Undoing a completed task did not reliably recalculate the streak.
4. Progress and task state could therefore disagree.

These findings must be rechecked against the current local files before editing. The repository is a documentation repository; the working Expo application source is maintained locally.

## Asset Handling

The three mood images were prepared as transparent PNG assets and resized to a 512-pixel-wide canvas while retaining a consistent canvas size. The intended filenames are:

- streak_happy.png
- streak_neutral.png
- streak_sleepy.png

The user was instructed to place them in assets/mascot/. Their presence in the local app folder and their upload to this GitHub repository have not been verified. No image binary is included in this log.

## What Was Not Completed

- The Streak Guardian was not confirmed as fully integrated into the app code.
- Calendar-to-Goals-to-Profile-to-Widget synchronization was not implemented or device-tested today.
- AsyncStorage persistence and streak recalculation were not verified.
- The three PNG files were not confirmed in the GitHub repository.
- No claim is made that a production Android Home Screen widget exists; this work concerns the in-app widget experience and its visual direction.

## Next Session Plan

1. Confirm the three PNG files exist in the local assets/mascot/ folder.
2. Inspect ProgressContext.js, progress.js, GoalsContext.js, and src/app/index.tsx.
3. Search all current uses of progress callbacks and task mutation functions.
4. Agree on exact success, empty-day, missed-day, and late-evening rules.
5. Implement one shared progress calculation based on dated Calendar tasks.
6. Persist derived progress safely and ensure undo/clear operations recalculate it.
7. Connect the Streak Guardian to the shared data without duplicating task state.
8. Test task creation, completion, undo, clearing, app restart, and date changes on device.
9. Verify the three moods switch only when the real task data meets their rules.

## Day 22 Outcome

Day 22 produced a clear visual direction and a three-mood companion set for Streak Guardian. The most important technical decision is also clear: the widget must reflect the same real task history used by Calendar, Goals, and Profile. Visual design is finalized for this iteration; shared data integration remains the next engineering milestone.
