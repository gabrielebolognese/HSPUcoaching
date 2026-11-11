# HSPU Coaching Plan

A single-file web app that walks through a 21-step plan for running handstand push-up (HSPU) coaching on Instagram.

It opens on what to do today, keeps a checklist for daily and weekly tasks, and holds a list of video ideas with the hook to say in the first two seconds.

## What is in it

- **Today:** the current step of the plan and the tasks for the day
- **Instagram stories:** a daily checklist of what to post, with a goal of at least 7 stories
- **Video ideas:** tap an idea once it has been posted to mark it as used
- **All steps:** the full 21-step plan, from setup onward
- **Account:** export and import a backup as a JSON file or as pasted text, and reset progress

The daily list resets every day and the weekly list every Monday.

## Running it

There is no build step and no dependencies. Open `index.html` in a browser, or serve the folder with any static server.

Progress is saved in the browser on the device you use, so use the backup in **Account** to move it to another phone.
