# Lift Log

A single-page dashboard for workout data exported from the [Strong](https://www.strong.app/) app.

Open `index.html` in a browser, tap **Load Strong CSV**, and pick your export. The file is read in the browser and never uploaded anywhere.

## What it shows

- Totals: workouts, this year, last 30 days, week streak, total volume, exercises
- Per-exercise progress over time: estimated 1RM, heaviest set, session volume or most reps, with PRs marked
- Workouts per week (last 26 weeks) and monthly volume
- A personal records table with change since you started each lift

## Exporting from Strong

1. In Strong, open the Profile tab, then the gear icon for Settings.
2. Tap **Export Strong Data**.
3. Save the CSV to Files (iPhone) or Downloads (Android).

The export doesn't record your unit, so set lb or kg on the page to match your Strong settings.

## Notes

- Warm-up sets (`W`) are excluded from records and volume; rest timer rows are ignored.
- Estimated 1RM uses the Epley formula, `weight × (1 + reps / 30)`, on sets of 12 reps or fewer.
- Works with comma- or semicolon-delimited exports.
