# HSPU Coaching Plan

A single-file, phone-first web app that walks a calisthenics athlete through a 21-step plan for starting an online handstand push-up (HSPU) coaching business on Instagram and TikTok. It combines the step-by-step plan with a daily and weekly task tracker, a library of video ideas with ready-made hooks, and an account page that stores your setup and backs up your progress. Everything runs in the browser and is saved on the device; there is no server, no login and no build step.

It is written for one specific use: a coach who can already do HSPU, archer HSPU and 90° HSPU and wants a checklist to follow from profile setup to the first paying clients.

## Features

### Plan (21 steps in 5 stages)

- Stages: **Set up** (steps 1-5), **Start posting** (6-8), **Free value first** (9-12), **First clients** (13-17), **Grow** (18-21).
- Each step shows its stage, a time estimate, a checklist of tasks with short explanations, and, where relevant, a reason why the step matters.
- Copy-ready text blocks with a **Copy** button: one-liner, Instagram and TikTok bios, story formula and example, form-check story text, a draft 4-week starter routine, the coaching offer, the "taking clients" announcement and three DM reply scripts.
- Step 5 has six free-text questions ("Write your story") whose answers are saved as you type.
- **Back** / **Next step** navigation, a progress bar, and a "Step N of 21" and "N of 21 done" header.
- **All steps** sheet: every step grouped by stage, marked *Done* or *Here*, tap to jump. It also holds **Reset all plan progress** (tap twice to confirm), which clears the plan checkboxes only.

### Today

- **Today's video**: the video type for the current weekday (Tip, Story, Proof or Reply) with a suggested idea, **Another idea** to cycle, and **Mark idea as used**.
- Two weekly schedules, switchable at the top: **Month 1: free value** (three tips, two stories, one proof and one reply video a week) and **Month 2+: more stories** (three stories, two tips, one proof and one reply). A seven-day strip shows the whole week's plan.
- **Every day** checklist: post on TikTok, post on Instagram Reels, reply to every comment and DM, train and film clips, write tomorrow's hook.
- **Instagram stories** counter with a goal of 7 per day, plus a fold-out list of what to post in seven stories.
- **I have clients** toggle that adds two daily client tasks.
- **This week** checklist: two filming sessions, the free form-check story, the "taking clients" story and the Sunday review.
- A day streak, and a badge on the Today tab with the number of tasks still open.
- The daily list starts fresh every day and the weekly list every Monday; past days and weeks are kept as history.

### Ideas

- 31 video ideas in four types: 15 Tips, 8 My story, 5 Proof, 3 Replies. Each has the hook line and, for most, a note on how to film it.
- Filter by type, tick an idea once it has been posted, and see the "N of 31 used" count. Used ideas are no longer suggested on the Today tab.

### Account

- Stats: plan steps done, current step, day streak, full days done.
- **My setup**: editable name, Instagram and TikTok usernames, what you coach, one-liner, both bios, price, offer text and start date.
- **My story**: the six answers from step 5, with a link back to edit them.
- **My choices**, **Plan progress** per step (tap to jump) and the **last 14 days** of daily tasks and story counts.
- **Backup**:
  - **Export** downloads `hspu-plan-backup-YYYY-MM-DD.json` containing the plan, setup, story answers, ideas used and every day's and week's tasks.
  - **Import** reads a backup file, shows a summary of what it contains, and asks for confirmation before replacing the progress on the device.
  - The backup can also be shown as text to copy, and imported by pasting text, for browsers or views where file download is not available.
  - A dot on the Account tab and a highlighted box remind you when there is progress and no backup in the last 7 days.

### General

- Light and dark theme following the system setting.
- Layout built for a phone: one 560px column, fixed bottom tab bar, safe-area insets.
- The open tab is kept in the URL hash (`#plan`, `#today`, `#ideas`, `#account`).

## Getting started

### Prerequisites

- A current web browser. Nothing else: no Node.js, no package manager, no dependencies to install.
- An internet connection is only needed for the two Google Fonts (Archivo and Public Sans). Without it the app still works and falls back to system fonts.

### Download

```bash
git clone https://github.com/gabrielebolognese/HSPUcoaching.git
cd HSPUcoaching
```

### Run

Open `index.html` in a browser. Alternatively, serve the folder with any static file server and open it from there.

There are no environment variables and no configuration files.

## Deploy

The app is one static file, so it can be put on any static host by uploading `index.html`. The repository contains no deployment configuration or CI workflow, and no hosted copy is set up from this repo.

To use it like an app on a phone, open the hosted page in the phone's browser and add it to the home screen. Note that progress is stored per browser and per address, so always open it from the same place.

## Usage

1. Start on the **Plan** tab. Do the steps in order: tick each task, then tap **Next step**. Use **All steps** to jump around.
2. In step 5, answer the six story questions. They feed the story videos later in the plan.
3. From step 8 onward, open the **Today** tab every day: check the day's video type, pick an idea, tick the daily tasks and count your Instagram stories. Completing every daily task and at least 7 stories counts the day toward the streak.
4. Switch the schedule to **Month 2+: more stories** when you reach that stage, and turn on **I have clients** once you have some.
5. Use the **Ideas** tab to browse hooks and tick the ones you have posted.
6. In **Account**, fill in your setup and export a backup about once a week. To move to another phone or browser, export there and import here.

## Project structure

| Path | Purpose |
| --- | --- |
| `index.html` | The whole application: markup, CSS and JavaScript, including the plan, idea, schedule and checklist data |
| `README.md` | This file |

Inside the script, the content lives in plain arrays that can be edited directly: `STAGES` and `STEPS` (the plan), `IDEAS` (video ideas), `SCHED` (weekly video schedules), `DAILY`, `CLIENT` and `WEEKLY` (checklists), and `SETUP` (account fields).

Progress is stored in the browser's `localStorage` under keys prefixed with `hp:`.

## Tech stack

- HTML, CSS and vanilla JavaScript (ES5 style) in a single file, with no framework or build tooling
- `localStorage` for persistence
- Blob download and `FileReader` for JSON backup export and import
- Google Fonts: Archivo and Public Sans

## Status

A personal tool, written for one coach and one niche; the plan text, bios and video ideas are hard-coded for handstand push-up coaching. There are no tests, and data exists only in the browser where it is used, so the backup in **Account** is the only way to keep or move it.
