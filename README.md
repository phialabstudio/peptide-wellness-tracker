# GLP-1 & Peptide Wellness Tracker

**A calm daily check-in experience for women on GLP-1 medications or peptide protocols.**

Private, browser-based, and built for busy days. No accounts. No cloud. No data sharing — everything stays on your device.

---

## Getting Started

1. Open `index.html` in any web browser
2. No installation, sign-up, or internet connection required
3. The "Start Here" guide on the Dashboard walks you through setup in under 2 minutes

---

## Features at a Glance

| Tab | What it does |
|---|---|
| 📊 Dashboard | Daily check-in, injection status, side effects, fuel, focus, motivation, weight progress |
| 💉 Injection Log | Full injection history — log, filter, edit, delete |
| ⚠️ Side Effects | Side effects, mood, hydration, and exercise tracking |
| ⚖️ Weight | Log weight, see progress toward your goal |
| 📏 Measurements | Track body measurements over time |
| 🍽️ Calories | Log meals with optional macro details |
| ⚙️ Settings | Appearance, units, medications, reminders, goals, data management |

---

## Dashboard — Your Daily 2-Minute Check-In

The dashboard is designed to feel like a calm morning check-in, not a medical spreadsheet. Each card answers one simple question.

### Phase Label
A small pill at the top showing your current week and protocol phase — for example, "Week 3 • Starter Phase." Hidden until you have injection data.

### Start Here *(first-time guide)*
Shown to all users until dismissed. A compact 4-box guide covering:
1. **Set your basics** — Add your medication, weight goal, and preferred units in Settings
2. **Log your latest injection** — Record the date, time, medication, dose notes, and injection site
3. **Track how you feel** — Log any side effects, mood, hydration, or wellness notes
4. **Prepare for your check-in** — Download your Doctor Summary before your appointment

Tap "Got it ✓" to hide permanently. Dismissed state saved in localStorage.

### How Are You Feeling Today?
Mood check-in with five quick options:
- 😊 Good — 😐 Okay — 😔 Rough — ⚠️ Side Effects — 🍫 Cravings

After selecting, a short supportive message appears. Your selection saves for the day and resets each morning.

### Next Injection
- Shows your next scheduled injection date with a countdown ("In 3 days," "Tomorrow," "Today!")
- Displays medication name and dose from your reminder settings
- "Log Injection" button opens the injection form directly

### Last Injection
- Shows date, time, medication, dose, and injection site of your most recent log
- Includes a gentle reminder to rotate your injection site

### Side Effects Today
Quick-tap chips to log what you're feeling right now:
- None 🙂, Nausea, Constipation, Headache, Fatigue, Other
- Tapping a chip saves it instantly to your side effects log
- "Add Full Details" links to the full Side Effects tab

### Gentle Fuel Reminder
- Protein progress bar vs. your daily protein goal
- Water/hydration progress bar vs. your daily hydration goal
- No calories shown here — intentionally simple
- "+ Log Protein" goes to the Calories tab; "+ Log Water" adds a serving directly

### Tiny Focus Today
One small encouraging daily focus — seeded by date, stays consistent all day. Examples:
- "Drink a glass of water before your morning coffee."
- "Add one protein snack before lunch today."
- "Take a gentle 10-minute walk after a meal."

Tap "Shuffle" to cycle to a different focus.

### Daily Motivation
A short rotating quote from your personal quote list — compact and soft.

### Weight Progress
- Shows Start Weight, Current Weight, and Total Change
- No chart on the dashboard — detailed history and trend chart are inside the Weight tab
- "View Full History" links to the Weight tab

---

## Tab Details

### 💉 Injection Log
- Log date, time, medication, dose, injection site, protocol phase, and notes
- Filter entries by medication or phase
- Edit or delete any past entry
- Full injection history lives here — not on the Dashboard

### ⚠️ Side Effects — 4 sub-tabs

**Side Effects**
- Pick symptoms from a list or type your own
- Choose severity: Mild / Moderate / Strong
- Add optional notes and date

**Mood & Wellness**
- Rate mood, energy, hunger, and sleep quality (1–10)
- Log cravings and notes

**Exercise**
- Choose activity type: Walking, Strength Training, Pilates, Yoga, Zumba, Cycling, Swimming, Stretching, or Other
- Log duration (minutes) and intensity (Low / Moderate / High)
- Add optional notes

**Hydration**
- Quick-add buttons (amounts adapt to your selected unit)
- Set a personal daily goal
- Progress bar shows how close you are
- Resets automatically each new day

### ⚖️ Weight
- Log weight with date and optional notes
- Goal progress visualization
- Weight history chart and table
- Supports lbs or kg

### 📏 Measurements
- Track chest, waist, stomach, hips, neck, thighs, calves, and arms
- Supports inches or cm
- Compare latest vs previous measurements

### 🍽️ Calories / Meals
- Log meal type (Breakfast / Lunch / Dinner / Snack) and description
- All nutrition fields are **optional** — fill in what you know
- Protein and carb level pickers: Low / Medium / High / Not sure
- Enter exact grams or use the level picker — whichever is easier
- Today's macro summary with progress bars and pie chart

---

## Settings

### Appearance
Choose a **Theme Color** that changes the accent color throughout the entire app. 5 options:

| Theme | Feel |
|---|---|
| Rose Calm *(default)* | Dusty rose & soft lavender |
| Lavender Soft | Purple-violet, soft and dreamy |
| Sage Wellness | Green-teal, fresh and calm |
| Peach Glow | Warm coral-peach, cozy |
| Mocha Neutral | Warm brown, grounded |

Theme is saved in localStorage and applied instantly on page load.

### Units & Display
- Weight: **lbs** or **kg**
- Measurements: **inches** or **cm**
- Hydration: **ml**, **oz**, or **cups**
- Custom macro metric: Fiber, Cholesterol, Water, Sodium, or Sugar

### Medication List
- Add the medications or peptides you want to track
- Set each one's dosage unit (mcg / mg)

### Medication Instructions
A personal notes section — not a calculator. Save:
- Medication name, prescribed dose, and unit
- Your injection schedule
- Notes from your prescriber or pharmacy label
- Questions to bring to your next appointment

> ⚕️ This section is for personal organization only. This app does not calculate doses or mixing instructions. Always follow your licensed healthcare provider or pharmacy label.

### Weight & Nutrition Goals
- Start weight and start date
- Goal weight and goal date
- Daily calorie, protein, carb, and fat targets

### Protocol Phases
- Add and name your own protocol phases (e.g. Onboarding, Maintenance, Loading Phase)

### Injection Reminders
- Set browser pop-up notifications for injection days
- Choose medication, time, and repeat schedule
- The Next Injection card on the Dashboard pulls from these reminders

### Motivational Quotes
- Add your own quotes to rotate on the Dashboard

---

## Your Data

All data is saved in your browser's **local storage** — it stays on your device and is never sent anywhere.

| Action | How |
|---|---|
| Save a backup | Settings → Download My Backup (saves as a `.json` file) |
| Restore a backup | Settings → Restore from Backup |
| Reset everything | Settings → Reset My Tracker |

> Download a backup regularly. If you clear your browser data, your tracker data will be lost.

---

## Doctor Summary

Generate a clean, printable health report to bring to your next appointment.

- Choose a date range: **Last 7 days**, **Last 30 days**, or **All time**
- Includes: injections, weight, side effects, mood, hydration
- Add personal notes or questions before printing
- Opens in a new tab — use **File → Print** to save as PDF

---

## Medical Disclaimer

This app is for personal organization only. It does not provide medical advice, dose calculations, mixing instructions, or any medical guidance. Always follow the guidance of your licensed healthcare provider or pharmacy label.
