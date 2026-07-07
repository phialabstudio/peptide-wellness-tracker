[README.md](https://github.com/user-attachments/files/29753098/README.md)
# GLP-1 Wellness Tracker

A private, local-first app for people on GLP-1 medications to track doses, weight, protein, hydration, side effects, and progress — and to generate a clean, doctor-ready summary for appointments.

Built by **Phia Lab Studio**. Live at **app.phialabstudio.com**.

> **What makes this different:** your data never leaves your device. No account, no login, no cloud, no server storing your weight or dose history. Everything lives on your device, under your control.

*Developer documentation is in [DEVELOPERS.md](DEVELOPERS.md).*

---

## What it tracks

- **Injections / doses** — log each shot (medication, dose in mg, date). Default medications are GLP-1 only: Semaglutide (Ozempic / Wegovy), Tirzepatide (Mounjaro / Zepbound), and Liraglutide (Saxenda). You can add any other medication as a custom entry.
- **Weight & body composition** — weight, body fat %, skeletal muscle %, muscle mass, and visceral fat over time. Fat weight is calculated automatically from weight and body-fat %.
- **Scan your scale report** — photograph or screenshot your clinic scale printout and the app reads the values for you, entirely on your device — the image is never uploaded. You confirm the numbers before anything is saved.
- **Protein & food** — log protein in grams or ounces, with quick-add chips for common foods. When you use a quick-add chip you can tag the meal type (Breakfast / Lunch / Dinner / Snack); it defaults sensibly by time of day, and you can override it before tapping. Calories and macros (carbs, fats) ride along. The protein ring shows your progress honestly — no goal set means a dash, not an invented number.
- **Hydration** — track water intake in your preferred unit.
- **Exercise** — log workouts with an optional average heart-rate field (bpm). A built-in calculator estimates your personal fat-burn heart-rate zone.
- **Side effects & mood** — record nausea, fatigue, cravings and other effects with daily mood check-ins, plus gentle food-noise support prompts, so patterns become visible over time.
- **Measurements** — track body measurements as they change.
- **Reminders** — set custom reminders (e.g. your weekly shot) to stay consistent.
- **Streaks & insights** — see consistency streaks and an Insights view of your trends.
- **Doctor Summary** — generate a printable summary of your dose history, weight trend, and key stats to bring to or send ahead of an appointment.

## Privacy

No sign-up, no login. Everything is stored locally in your browser. Nothing is transmitted to a server — this is a deliberate design choice. Your health data is yours.

**The trade-off:** because your data lives only on your device, it isn't automatically backed up. If you clear your browser data, uninstall, or switch phones, your history goes with it — unless you back it up.

## Backing up your data (important)

Use the built-in **Backup** to export a file with all your data. Do this regularly, and especially before:

- clearing your browser cache or site data,
- switching phones or browsers,
- a major OS update.

To move to a new device, install the app there and use **Restore** with your backup file. Every backup is validated before importing, and a recovery copy of your existing data is kept first — so a bad restore can be undone.

## Installing the app

It's a progressive web app (PWA), so you can add it to your home screen and use it like a native app:

- **iPhone/iPad (Safari):** Share button → **Add to Home Screen**.
- **Android (Chrome):** menu → **Install app** / **Add to Home Screen**.

Once installed it works offline and launches full-screen.

## First time here?

Look for the **Start Here** card when you open the app — it walks you through your first dose, weight entry, and protein goal.

---

*Private by design. Your data stays on your device.*
