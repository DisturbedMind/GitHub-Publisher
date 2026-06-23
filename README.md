<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white">
  <img alt="GUI" src="https://img.shields.io/badge/GUI-Tkinter%20desktop-0f766e">
  <img alt="Git" src="https://img.shields.io/badge/Git-supported-F05032?logo=git&logoColor=white">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-blue">
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows-0078D4?logo=windows&logoColor=white">
</p>

<p align="center">
  <img src="assets/wolf-banner.png" alt="Wolf logo" width="720">
</p>

# GitHub Publisher GUI

A local Tkinter desktop app for publishing existing project folders to GitHub.

The app keeps the same look and feel as **YouTube Music Playlist Downloader**: dark wolf-branded header, light card panels, soft action buttons, and a dark command log. It runs local `git` commands only when you click an action.

## Features

- Browse for a local project folder or paste a path manually
- Inspect branch, remote, and changed files
- Initialize Git in a selected folder
- Set or update the `origin` remote URL
- Pull from GitHub with rebase
- Run the first-upload pull for unrelated histories
- Show conflicted files
- Continue after conflict markers are removed
- Commit all changes and push in one shortcut
- Push to the selected remote and branch
- Keep an on-screen action log of every command result

## Requirements

- Windows with Python 3.10+
- Git installed and available on `PATH`
- A GitHub account authenticated through Git Credential Manager or another Git credential flow

## Run From Source

```powershell
cd C:\Codex\Projects\GitHub-Publisher-GUI
python .\github_publisher_gui.py
```

You can also use:

```powershell
.\run.ps1
```

## Build The EXE

```powershell
.\build_exe.bat
```

The generated app is written to:

```text
dist\GitHubPublisher.exe
```

## Notes

- The app never stores GitHub tokens.
- Commands run only inside the project path you enter.
- If the project is not a Git repo yet, choose the folder and click **1. Initialize Git**.
- If GitHub rejects your push because the remote has a README, license, or `.gitignore`, click **3. Pull from GitHub**. If Git says the histories are unrelated, click **Fix A. First Upload Pull** once.
- If Git reports conflicts, click **Fix B. Show Conflicts**, edit the listed files, remove every `<<<<<<<`, `=======`, and `>>>>>>>` marker, save, then click **Fix C. Continue After Fix**.
