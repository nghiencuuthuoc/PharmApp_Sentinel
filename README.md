# PharmApp Sentinel

**See at a glance which of your scheduled jobs and startup programs passed, failed or never ran.**

PharmApp Sentinel is a small Windows desktop tool that watches the code you run through **Windows Task Scheduler** and the **Startup** list. It shows every job in one window, colours it by result, and lets you read its log without hunting through folders.

🇻🇳 Tiếng Việt: [README_VN.md](README_VN.md)

---

## What it does

- Lists every **user-installed scheduled task** (system and vendor tasks are skipped) and every **startup entry that runs code**.
- Gives each job its own **tab** with status, schedule, last and next run, result code, running processes, run history, the latest log and recent report files.
- Colours each job so problems stand out:

| Colour | Meaning |
|---|---|
| 🟢 Green | PASS – finished with exit code 0 |
| 🔴 Red | FAIL – non-zero result or error in the log |
| 🔵 Blue | Running now |
| 🟠 Orange | Interrupted (closed or Ctrl+C) |
| 🟡 Yellow | Warning – the task says OK but its log shows errors |
| 🩷 Pink | Script or target file is missing |
| ⚪ Grey | Disabled, not run yet or unknown |
| 🟣 Purple | **No log yet** – the job writes no log the tool can find |

- Jobs without a log are clearly marked **"No log yet"**, with a tip on how to add one, so you can improve them later.
- **Scans again automatically** (default every minute, adjustable from 30 seconds to 10 minutes, or off).
- **Remembers where you left off**: the previous data appears instantly when you reopen the app, then refreshes.
- **Read-only and safe**: it never runs, edits or deletes any task or script.

## Requirements

- Windows 10 or 11
- Nothing else to install – `PharmAppSentinel.exe` is a single portable file.

## Getting started

1. Download **`PharmAppSentinel.exe`** from this repository.
2. Double-click it. (If Windows SmartScreen warns that the publisher is unknown, choose **More info → Run anyway**.)
3. Wait a few seconds for the first scan. The **Overview** tab lists every job.
4. Click a job tab to see its details, or double-click a row in the Overview to jump to it.

## Using the app

**Overview tab**
- Click the coloured status buttons at the top (FAIL, PASS, No log yet…) to filter the list.
- Use the drop-downs and the search box to filter by source (Task Scheduler / Startup), status, or part of a name or path.
- Click a column header to sort.

**A job's tab**
- **Information** – command, script, working folder, schedule, state, last and next run.
- **Running processes** – live processes of the job and a progress bar when the log shows a percentage.
- **Run history** – earlier results, built from the log and from the app's own scans.
- **Log** – the latest log with errors in red, warnings in amber and successes in green. Switch between several logs, reload, or open the log file and its folder.
- **Reports** – recent output files near the script; double-click to open.
- Buttons at the top: open the folder, edit the script in Notepad, copy the command.

**Right-click menus** (also available from the keyboard menu key or Shift+F10)
- On a job: open details, edit, reveal in file manager, open a terminal there, log actions, copy name / path / command / diagnostic summary, open in Task Scheduler, pin, filter by this status or source, rescan, properties.
- On several jobs: copy names or paths, pin, export the selection to CSV, properties summary.
- On empty space: rescan, export the list to CSV, clear filters, open the data folder.
- In the log: copy, select all, filter by severity, follow the log live.
- Copied commands and diagnostics automatically **mask passwords and tokens**.

**Pinning** – pin important jobs; they appear first in the tab strip with a 📌.

**Other conveniences**
- **Language:** English (default) or Tiếng Việt – switch from the header or **View → Language**.
- **Appearance:** System, Light, Dark, Luxury Warm or Modern Blue-Gray.
- **Font size:** `Ctrl +` to enlarge, `Ctrl -` to shrink, `Ctrl 0` to reset.
- **Resizable areas:** drag the dividers to give more room to the tabs, the table or the log.
- **Footer:** shows for 9 seconds, then tucks away; hover the thin bar at the bottom to bring it back (or **View → Show Footer**).
- **Keyboard shortcuts:** `Ctrl /` shows the full list. Useful ones: `F5` rescan, `Ctrl+Alt+E` edit script, `Ctrl+Alt+R` reveal in folder, `Ctrl+Shift+C` copy path, `Alt+Enter` properties.

## Your data

Settings, the last scan and the run history are stored in `%APPDATA%\PharmApp\Sentinel`. Delete that folder to reset the app.

## Good to know

- Log detection is a best guess based on the script and nearby `logs` folders; a log marked ★ is one the script refers to explicitly.
- Windows keeps no per-run history for tasks unless you turn it on, so history starts building from the first scan.
- Scripts that print only to the console have no log to read – they will show as **No log yet**.

---

© 2009-2026 Pharma R&D Platforms • PharmApp • [www.nghiencuuthuoc.com](https://www.nghiencuuthuoc.com) • [www.pharmapp.dev](https://www.pharmapp.dev)
