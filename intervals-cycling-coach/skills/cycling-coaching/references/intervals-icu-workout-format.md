# Intervals.icu Workout Format

Plain-text syntax for writing structured workouts that Intervals.icu can parse. Use this format when creating workouts to add to the athlete's calendar.

## Structure

A workout is made up of **sections** and **steps**.

- **Section headers**: Lines without a `-` prefix. Common names: `Warmup`, `Main Set`, `Cooldown`. Can include repeat counts (e.g., `Main Set 5x`).
- **Steps**: Lines starting with `-`. Each step defines a duration/distance, intensity target, and optional cadence.
- **Blank lines** between sections for readability (one is enough).

```
Warmup
- 10m ramp 50%-75% 90rpm

Main Set 3x
- 8m 88-94%
- 4m 55%

Cooldown
- 10m 50%
```

## Time & Distance

### Time

| Unit      | Syntax      | Examples                              |
| --------- | ----------- | ------------------------------------- |
| Hours     | `h`         | `1h`                                  |
| Minutes   | `m`         | `10m`, `5m`                           |
| Seconds   | `s`         | `30s`, `90s`                          |
| Combined  |             | `1m30`                                |
| Shorthand | `'` and `"` | `5'` (5 min), `30"` (30 sec), `1'30"` |

### Distance

| Unit       | Syntax | Examples       |
| ---------- | ------ | -------------- |
| Kilometers | `km`   | `2km`, `0.4km` |
| Miles      | `mi`   | `1mi`, `4.5mi` |

**Important:** `m` means minutes, not meters. Use `km` or `mi` for distance (e.g., `0.4km` instead of `400m`).

## Intensity Targets

### Cycling (Power)

| Type     | Syntax | Examples                |
| -------- | ------ | ----------------------- |
| % of FTP | `N%`   | `75%`, `88%`, `95-105%` |
| Watts    | `Nw`   | `220w`, `200-240w`      |
| Zones    | `ZN`   | `Z2`, `Z4`              |

### Heart Rate

| Type        | Syntax    | Examples                  |
| ----------- | --------- | ------------------------- |
| % of max HR | `N% HR`   | `70% HR`, `75-80% HR`     |
| % of LTHR   | `N% LTHR` | `95% LTHR`, `90-95% LTHR` |
| Zones       | `ZN HR`   | `Z2 HR`, `Z3 HR`          |

### Running (Pace)

| Type      | Syntax    | Examples             |
| --------- | --------- | -------------------- |
| % of pace | `N% pace` | `78-82% pace`        |
| Zones     | `ZN Pace` | `Z2 Pace`, `Z3 Pace` |

### Ranges

Use `a-b` for target ranges: `85-90%`, `200-240w`, `70-80% HR`.

## Ramps

Use the `ramp` keyword (case-insensitive) for gradual intensity changes:

```
- 10m ramp 50%-75%
- 15m ramp 60%-90% 85rpm
- 10m ramp 60-80% pace
```

## Freeride

Use `freeride` for ERG-off steps (no power target):

```
- 20m freeride
```

## Cadence

Append `rpm` to any step:

```
- 10m 75% 90rpm
- 5m 88% 70rpm
- 12m 85% 90-100rpm
```

## Repeats

Two forms:

1. **In a section header:** `Main Set 5x`
2. **Standalone line before a block:** `5x`

Nested repeats are not supported.

## Text Prompts

Any text before the first duration/intensity becomes the step cue:

```
- Recovery 30s 50%        # cue: "Recovery"
- Low cadence 4m 100%     # cue: "Low cadence"
```

Repeated blocks automatically append `k/N` to the first step's cue (e.g., "Main set 1/6").

### Timed Text Prompts

Add prompts that appear at specific times within a step. Use `time^` for timing and `<!>` to separate prompts from the step definition:

```
- First prompt at 0s 33^ 2nd prompt at 33s <!> 10m ramp 25-75%
```

Time is in seconds from step start. The `<!>` separator is required when using timed prompts.

## Parsing Rules Summary

- Section headers = lines without `-` prefix
- Steps = lines starting with `-`
- Repeats = `<Section> nx` or standalone `nx` line
- Sport type determined by workout metadata (Run → pace; otherwise power), but steps may use HR explicitly
- Keywords are case-insensitive (`Ramp` = `ramp`)
- Free text allowed anywhere in a step; text before first duration/intensity becomes the cue

## Cycling Zones Reference

| Zone | Name      | % of FTP |
| ---- | --------- | -------- |
| Z1   | Recovery  | < 55%    |
| Z2   | Endurance | 56-75%   |
| Z3   | Tempo     | 76-90%   |
| Z4   | Threshold | 91-105%  |
| Z5   | VO2 Max   | 106-120% |
| Z6   | Anaerobic | > 120%   |
