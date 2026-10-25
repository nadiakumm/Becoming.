# Becoming — installable web app starter

A beginner-friendly, black-and-white Progressive Web App (PWA) prototype for tracking habits, workouts, wellness, tasks, calendar dates, progress, and Christian practices.

## What works in this prototype
- Daily habit checklist with categories and daily completion
- Workout logging
- Weight, sleep, steps, mood, and water logs
- To-do lists by date
- Calendar date selection
- Scripture, prayer, and reflection journal
- Simple progress snapshot and JSON data export
- Offline shell via service worker
- iPhone Home Screen web app support

## Important limitations
- Data is saved in `localStorage` in the browser on this device. There is no account, secure cloud backup, or cross-device sync yet.
- The prototype does not connect to Apple Health or Garmin yet. See `INTEGRATIONS.md` before planning those features.
- This is a starter project, not a medically validated product. Do not use it as a medical record.
- The Google Fonts stylesheet is optional; the app uses system fallbacks if offline.

## Preview locally
For service workers/PWA behavior, serve the folder over localhost rather than opening `index.html` as a file. If Python is installed:
```bash
python3 -m http.server 8000
```
Then open `http://localhost:8000` in your browser.

## Publish it so your iPhone can install it
A PWA must be served over HTTPS (except localhost). Beginner path:
1. Create a GitHub account if you do not already have one.
2. Create a new repository called `becoming`.
3. Upload the files and the `icons` folder from this project.
4. Import the repository into Vercel and deploy it using the default static-site settings. No build command is needed; the root directory is the project folder.
5. Open the deployed HTTPS URL in Safari on your iPhone.
6. Tap Share → Add to Home Screen. If shown, enable “Open as Web App”, then tap Add.

See the Apple and MDN links in `INTEGRATIONS.md` for the current instructions.

## Suggested next build stages
1. Add a hosted database + sign-in before sensitive or long-term tracking.
2. Add editable habit schedules, reminders, weekly/monthly charts, and richer workout templates.
3. Decide whether Apple Health/Garmin data should be read-only import or two-way sync.
4. Implement the relevant integration with privacy controls and explicit consent.


## Workout Planner update
The Fitness section now includes a weekly workout schedule, custom workouts, an exercise library (built-in plus user-added exercises), and exercise details for sets, reps, weight, rest time, and notes. Custom workout entries are stored in the same local Becoming data as other features.
