# The Ultimate Planner — Prototype

A digital productivity planner designed to feel like opening a physical planner every morning,
rather than a project-management app. Built from a product brief calling for a calm, paper-like
alternative to Notion/Trello/ClickUp-style tools.

## Status

Working front-end prototype, single self-contained HTML file. No backend — all data is
in-memory for the current browser session and resets on refresh. This is intentional at this
stage: the goal so far has been to prove out the interaction model (drag-and-drop scheduling,
Day/Month/Year views, archive, review flow) before committing to a data layer.

## Run it

Open `ultimate-planner-prototype.html` in any modern browser. No build step, no install.

## What's implemented

- **Today I Want To** — daily intention field
- **Calendar — Day / Month / Year views**, toggled via buttons above the calendar:
  - *Day* — hourly view (6am–9pm) with drag-and-drop scheduling and prev/next day navigation
  - *Month* — traditional Monday-first grid, today highlighted, event-count dots, click a day to
    open it in Day view
  - *Year* — twelve mini-month calendars with prev/next year navigation and event dots; click any
    day to jump straight to Day view for that date
- **To-Do list** — tasks with P1/P2/P3 priority and an editable title (click into any task to
  rename it); drag tasks onto the calendar to schedule, drag calendar items back onto the To-Do
  list to unschedule; status is Not Started / In Progress / Completed
- **Archive** — completing a task (checkbox or setting status to Completed) archives it
  immediately, keeping the To-Do list short. A searchable "Archive (N)" modal, linked from the
  To-Do list header, holds everything completed, each with a **Restore** action to bring a task
  back (as In Progress) if it turns out more work is needed
- **Late tag** — tasks not completed by the time you run "Carry forward & close day" in the Daily
  Review are flagged Late and unscheduled going into the next day
- **Notes** — free-form notes area
- **Global search** — across tasks, notes, calendar events, the daily intention, and the archive.
  Clicking a result jumps to that item: tasks/notes scroll into view, calendar results switch to
  the correct date in Day view, archive results open the Archive modal — all with a brief
  highlight so you can spot what you searched for
- **Daily review** — modal summarising tasks completed today vs. still open, with an explicit
  rollover warning next to each remaining item, and a carry-forward action

## Not yet built (from the original brief)

- Week view
- Weekly / monthly review flows (only the daily review exists so far)
- Goals layer (annual/quarterly/monthly/weekly)
- AI planning assistant layer
- Calendar sync (Google Calendar, Apple Calendar, Outlook)
- Persistence (cloud storage, auth, offline support)
- Native mobile/tablet apps

## Notes on this repo

- `.gitignore` is set up defensively for secrets and local config (`.env` files, credential
  JSON, cloud provider credentials, local DB files, etc.) even though the current prototype has
  no backend — this is so nothing sensitive slips in once a data layer / API keys are added.
- No dependencies, no package manager files yet — pure HTML/CSS/JS.
