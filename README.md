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

## Walking data from iPhone

Web pages can't read Apple Health, so three iPhone Shortcuts write CSV files to iCloud Drive › Shortcuts, and **Load Health files** reads them (you can select all three at once). The page has step-by-step instructions for building the Shortcuts.

| File | Header | One row per |
|---|---|---|
| `lift-log-steps.csv` | `Date,Steps` | day, e.g. `2026-09-21,8412` |
| `lift-log-distance.csv` | `Date,Distance` | day, Walking + Running Distance, e.g. `2026-09-21,2.4` |
| `lift-log-walks.csv` | `Date,Type,Duration,Distance` | workout, e.g. `2026-09-21 07:15,Walking,32 min,1.6` |

The Walking panel shows:

- **Daily steps**: latest day, 7- and 30-day averages, days at 10,000+, best day, and a 90-day chart with a goal line
- **Walking distance**: latest day, 7-day average, this week, last 30 days, best day, and weekly totals
- **Walks**: walks, time and distance over the last 30 days, longest walk, and the 10 most recent walks with pace

Only walking and hiking workouts are kept from the walks file. Durations can be minutes, seconds, `h:mm:ss` or text like `1 hr 20 min`. Each file you load merges into what's saved; for a day or walk that appears in both, the newer file wins. Distance follows the unit switch (mi with lb, km with kg), and walking data never changes workout counts or the streak.

## Add to your iPhone home screen

Open https://heidenreich.github.io/lift-log/ in Safari, tap Share, then **Add to Home Screen**. It opens full screen with the Lift Log icon. The home-screen app keeps its own storage, separate from Safari, so load your CSV once from inside it.

## Notes

- Warm-up sets (`W`) are excluded from records and volume; rest timer rows are ignored.
- Rows with no reps but a time or distance count as cardio. Distance follows the unit switch: mi with lb, km with kg.
- Estimated 1RM uses the Epley formula, `weight × (1 + reps / 30)`, on sets of 12 reps or fewer.
- Works with comma- or semicolon-delimited exports.
