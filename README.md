# Demo Tracker

A single-page web app I built to run my own sales pipeline while working as an academic counsellor at an EdTech company. It replaced a spreadsheet and became my daily system of record for four months.

**Live:** [skrrill.github.io/demo-tracker](https://skrrill.github.io/demo-tracker)

## The problem

I booked trial classes with parents in the US and Canada from India. Every demo meant juggling two time zones, sending reminders on WhatsApp and email, explaining the curriculum for the child's grade, and building a price quote. The team had no tool that did this, so I built one.

## What it does

- **Demo pipeline:** add, edit, filter and delete demos, with live stats at the top.
- **Two time zones at once:** every demo time is stored in UTC and shown in both the parent's local time and IST. The parent's time zone can be looked up from their city.
- **Reminders:** browser notifications and an in-app banner before each demo, with a record of which ones already fired.
- **One-click messages:** editable message templates with placeholders, sent through WhatsApp, SMS or Gmail compose, plus a formatted HTML email that pastes cleanly into Gmail.
- **Calendar:** adds a demo to Google Calendar in one click.
- **Curriculum by grade:** shows what a child of that grade will build, for sharing with parents.
- **Pricing configurator:** plan cards, discounts and payment options, with quotes saved against a demo and reopened later.
- **Backup:** export and import all data as JSON.

## How it works

| Part | Choice |
|---|---|
| Front end | Plain HTML, CSS and JavaScript in a single file, no framework |
| Auth | Firebase Authentication with Google sign-in |
| Data | Cloud Firestore with real-time listeners (`onSnapshot`), so changes sync across phone and laptop instantly |
| Offline cache | `localStorage` for templates, pricing state and notification history |
| Hosting | GitHub Pages |

## How I built it

I designed the features from my own daily workflow and built the app with AI-assisted development, iterating whenever something slowed me down on real calls. The time zone handling (storing UTC, converting wall-clock time per zone) and the real-time sync were the parts that took the most iterations to get right.

## Run it locally

Open `index.html` in a browser. Sign-in and sync need a Firebase project; replace `firebaseConfig` in `index.html` with your own.
