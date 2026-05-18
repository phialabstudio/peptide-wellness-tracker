[README.md](https://github.com/user-attachments/files/27963950/README.md)
# GLP-1 & Peptide Wellness Tracker

Welcome to your calm GLP-1 & Peptide Wellness Tracker.

Use this app to organize your injections, symptoms, weight progress, wellness notes, and doctor-ready summaries — all in one place. Your data stays on your own device, and there's no monthly subscription.

Live demo: [peptide-wellness-tracker.vercel.app](https://peptide-wellness-tracker.vercel.app)

---

## What it does

- Track weekly injection schedules, medication, dose, and site
- Log side effects and spot patterns over time
- Monitor weight progress toward your goal
- Log meals, protein, and hydration daily
- Check in emotionally each day — the dashboard adapts to how you feel
- Write private end-of-day reflections (never included in reports)
- Generate a clean, printable Doctor Summary for consultations
- Set browser reminders or export to Google Calendar

---

## Features

### Dashboard
- **Dynamic hero card** — personalised greeting, emotional reassurance, and today's focus. Changes based on mood check-in.
- **Mood-adaptive layout** — selecting "Overwhelmed" simplifies the dashboard. Selecting "Proud" shows your streak and progress.
- **Injection countdown** — shows how many days until your next injection.
- **Doctor Summary highlight card** — quick access to your consultation report from the top of the dashboard.
- **Daily Motivation** — a short, calm one-liner that rotates daily.

### Injection Log
- Log date, time, medication, dose, injection site, and phase
- Filter by medication or protocol phase
- View full history in a table

### Weight Tracking
- Log weight with date and notes
- Track change from start weight to current
- Set a goal weight and target date

### Nutrition & Hydration
- Log meals with calories, protein, carbs, fats
- Track daily water intake with a visual progress bar
- Set custom daily hydration and nutrition goals

### Side Effects
- Quick-tap chips for common symptoms (Nausea, Fatigue, Headache, etc.)
- Log severity and notes
- View history by date

### Mood & Wellness
- Daily mood check-in (Proud, Good, Okay, Rough, Overwhelmed, Side Effects, Cravings)
- Mood drives the dashboard tone, message, and visible cards

### End-of-Day Reflection
- Two private prompts: "What felt hardest today?" and "What helped today?"
- Auto-saves as you type
- View the last 7 entries collapsed behind a toggle (not cluttered by default)
- Never included in Doctor Summary

### Doctor Summary
- Generates a printable HTML report for your next consultation
- Includes: injection log, side effects, weight progress, hydration, mood trend summary, and your personal notes
- Does **not** include private reflection entries
- Mood trend shown as a simple summary (e.g. "Most common this week: Okay")
- Filter by date range (Last 30 days, 90 days, All Time)

### Injection Reminders
- Set browser-based notifications for injection days and times
- **Google Calendar integration** — opens a prefilled weekly recurring event in Google Calendar. User taps Save to confirm.

### Settings
- Set your name (shows in dashboard greeting)
- Choose from 5 colour themes (Rose Calm, Lavender Soft, Sage Wellness, Peach Glow, Mocha Neutral)
- Set weight/measurement/hydration units
- Manage medications and protocol phases
- Add custom daily motivation quotes
- Load sample demo data (for screenshots or testing)
- Export and restore data as JSON
- Reset all data

---

## Privacy

- All data is stored locally in your browser using `localStorage`
- Nothing is sent to a server
- Data does not leave your device unless you export it manually
- Reflection entries are private and excluded from all reports

---

## Tech stack

| | |
|---|---|
| **Type** | Single-file HTML app |
| **Framework** | Vanilla JS — no dependencies |
| **Styling** | Custom CSS with CSS variables |
| **Font** | Plus Jakarta Sans (Google Fonts) |
| **Storage** | localStorage |
| **Hosting** | Vercel (static) |

No build step. No backend. No database. Open `index.html` directly in any browser.

---

## Getting started

```bash
# Download the file and open directly — no install needed
open index.html
```

Or deploy to Vercel, Netlify, or GitHub Pages by uploading `index.html`.

---

## Demo data

In Settings → Data Management, tap **🗂️ Load Sample Data** to populate the app with realistic demo entries for screenshots or testing. This includes injection logs, weight entries, side effects, meals, hydration, mood check-ins, and reflections.

---

## Disclaimer

This tracker is for personal organization only and does not replace medical advice. Always follow your clinician's guidance. This app does not provide diagnosis, treatment recommendations, or medical supervision.

---

## License

All rights reserved. This app is a commercial product. Do not copy, redistribute, or resell without permission.
