# Lift Log

A single-page dashboard for workout data exported from the [Strong](https://www.strong.app/) app.

Open `index.html` in a browser, tap **Load Strong CSV**, and pick your export. The file is read in the browser and never uploaded anywhere.

## What it shows

- Totals: workouts, this year, last 30 days, week streak, total volume, exercises
- Per-exercise progress over time: estimated 1RM, heaviest set, session volume or most reps, with PRs marked
- Workouts per week (last 26 weeks) and monthly volume
- Cardio: time and distance exercises (elliptical, runs, rows), with minutes per week and totals per exercise
- A personal records table with change since you started each lift

## Exporting from Strong

1. In Strong, open the Profile tab, then the gear icon for Settings.
2. Tap **Export Strong Data**.
3. Save the CSV to Files (iPhone) or Downloads (Android).

The export doesn't record your unit, so set lb or kg on the page to match your Strong settings.

## Daily steps from iPhone

Web pages can't read Apple Health, so a Shortcut writes your daily steps to `lift-log-steps.csv` in iCloud Drive › Shortcuts, and you load that file with **Load steps**. The page has step-by-step instructions for building the Shortcut (Find Health Samples → Repeat with Each → Format Date → Text → Combine Text → Save File).

The file is plain CSV, one row per day:

```
Date,Steps
2026-09-21,8412
```

Each file you load merges into the steps already saved; for a day that appears in both, the newer file wins. The panel shows the latest day, 7- and 30-day averages, days at 10,000+ steps and your best day, plus a 90-day chart.

## Add to your iPhone home screen

Open https://heidenreich.github.io/lift-log/ in Safari, tap Share, then **Add to Home Screen**. It opens full screen with the Lift Log icon. The home-screen app keeps its own storage, separate from Safari, so load your CSV once from inside it.

## Notes

- Warm-up sets (`W`) are excluded from records and volume; rest timer rows are ignored.
- Rows with no reps but a time or distance count as cardio. Distance follows the unit switch: mi with lb, km with kg.
- Estimated 1RM uses the Epley formula, `weight × (1 + reps / 30)`, on sets of 12 reps or fewer.
- Works with comma- or semicolon-delimited exports.
