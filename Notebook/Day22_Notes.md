# Day 22 — Notebook Notes

**Date:** 27 November 2026  
**Project:** System: T-0

## Today's main goal

Finalize a simple, attractive Streak Guardian widget concept without making the user manage extra settings or creating unnecessary mascot animations.

## Decisions

- Use a voxel NPC companion that is separate from the player's Profile character.
- Keep one consistent companion design with three moods: happy, neutral, and sleepy.
- Keep the widget minimal: fire icon, streak number, companion, and seven-day status row.
- Use MON, TUE, WED, THU, FRI, SAT, SUN.
- Do not add a progress bar, percentage, extra description, or unnecessary buttons.
- Keep the purple/lavender visual direction and consistent companion scale and placement.

## Mood rules — current draft

| Mood | Draft condition |
|---|---|
| Happy | Today's tasks are all completed and at least one task exists. |
| Neutral | There are unfinished tasks and the day is still in progress. |
| Sleepy | No tasks today, a missed day, or the proposed late-day condition. |

The empty-day rule and late-day cutoff need a final decision. 8:00 PM was discussed as a configurable proposal; it is not yet validated.

## Functional requirement

Calendar task data must be the single source of truth. Goals, Profile, progress, and Streak Guardian must derive their displayed values from that same data. Completing, undoing, or clearing a task must update all dependent screens consistently.

## Work completed

- Reviewed the initial Streak Guardian design.
- Iterated on the widget visual direction.
- Created/reviewed three companion mood variations.
- Finalized the short weekday labels and minimal layout requirements.
- Reviewed progress synchronization risks and identified files that need inspection before coding.

## Not yet verified

- Final code integration.
- Persistent streak calculation.
- Shared updates across Calendar, Goals, Profile, and Widgets.
- Device testing of all three moods.
- Upload of the actual PNG assets to GitHub.

## Next session checklist

- [ ] Confirm the three mascot PNGs are in assets/mascot/.
- [ ] Inspect ProgressContext.js, progress.js, GoalsContext.js, and src/app/index.tsx.
- [ ] Recheck all progress callback references.
- [ ] Finalize empty-day and 8 PM rules.
- [ ] Implement shared progress derivation from dated tasks.
- [ ] Test completion, undo, clear, restart, and date rollover.
- [ ] Verify all three companion moods on the device.

## Key lesson

A polished widget is only useful if its numbers are trustworthy. Build the visual around one reliable task and progress system instead of creating separate counters for each screen.
