---
description: Design a specific workout for today or a given day
argument-hint: [workout type or time available, e.g. "1 hour sweetspot" or "easy spin"]
---

Design a single workout tailored to the athlete's current state, needs, and available time.

## Data to Retrieve

Pull from Intervals.icu:

- Current fitness summary (CTL, ATL, TSB) to assess fatigue
- Most recent wellness entry for recovery signals
- Recent activities (last 3-5 days) to understand what they've done recently
- Athlete profile for current FTP and zone settings

## Design Process

1. **Parse the request**: If `$ARGUMENTS` is provided, use it to determine the workout type and/or time constraint. If no arguments, assess what the athlete needs based on their recent training and current fatigue.

2. **Confirm available time**: If the athlete didn't specify a duration, ask how much time they have for this session using AskUserQuestion. Don't assume they have unlimited time — many training sessions need to fit into a specific window between work, family, or other commitments. Offer sensible options based on their historical ride durations.

3. **Check context**: What did they do yesterday? What's planned for tomorrow? Avoid stacking hard days unless there's a reason.

4. **Build the workout**: Design the session to fit the available time. Provide a complete, structured workout including:
   - Warm-up (duration, targets)
   - Main set (intervals or sustained effort with specific power/HR targets in both watts and % FTP)
   - Cool-down
   - Total duration and estimated TSS
   - RPE guidance
   - Cadence targets where relevant

   If time is tight (e.g., 45-60 minutes), compress warm-up and cool-down and focus the main set. A focused 50-minute session is better than trying to cram a 90-minute workout into 60 minutes.

5. **Explain the purpose**: Why this workout? What physiological adaptation is it targeting? How does it fit into the bigger picture?

6. **Execution tips**: Practical advice for getting the most out of the session (fueling, when to bail if feeling bad, mental cues).

Reference the workout templates in the cycling-coaching skill for structure guidelines. Customize based on the athlete's actual FTP and zones.

Offer to add the workout to their Intervals.icu calendar.
