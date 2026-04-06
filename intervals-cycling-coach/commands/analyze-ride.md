---
description: Deep dive analysis of a specific ride
argument-hint: [ride name, date, or "latest"]
---

Perform a detailed analysis of a specific ride. If `$ARGUMENTS` specifies a ride (by name or date), find it. If the argument is "latest" or empty, analyze the most recent activity.

## Analysis Process

1. **Retrieve the activity** from Intervals.icu. Get the full activity details, intervals, and streams (power, HR, cadence).

2. **Ride Overview**: Summarize duration, distance, elevation, TSS, IF (Intensity Factor), NP (Normalized Power), average power, average HR.

3. **Power Analysis**:
   - Time in each power zone — was the intensity distribution appropriate for the ride's purpose?
   - Variability Index (NP/AP) — how steady was the effort? For endurance rides, closer to 1.0 is better.
   - Key efforts — identify notable sustained efforts or intervals and assess execution.

4. **Pacing Assessment**:
   - Did power fade over time (positive split) or stay steady/build (negative split)?
   - For long rides: compare first-half power to second-half power.
   - For rides with climbs: was climbing power well-paced?

5. **Heart Rate / Decoupling**:
   - Compare HR to power across the ride. Aerobic decoupling above 5% on endurance rides suggests aerobic base needs work.
   - Note any HR drift or unusual patterns.

6. **Coaching Takeaways**:
   - What went well?
   - What could improve?
   - How does this ride fit into their overall training? Was it the right workout at the right time given their current fatigue/fitness?
   - Specific, actionable suggestions for next time.
