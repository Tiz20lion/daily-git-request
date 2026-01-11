# Daily Git Request

Automatically updates your README.md every day at midnight UTC using GitHub Actions.

**Created by:** [Tiz](https://github.com/Tiz20lion)

## Requirements

- A GitHub account
- A GitHub repository (public or private)
- GitHub Actions enabled (enabled by default)

## Setup

### Option 1: Fork This Repository

1. Click "Fork" button on this repository
2. Your fork will automatically have the workflow
3. It will start running daily at midnight UTC

### Option 2: Use in Your Own Repository

1. Clone or create your repository:
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   ```

2. Copy the workflow file:
   ```bash
   mkdir -p .github/workflows
   # Copy .github/workflows/daily-update.yml to your repo
   ```

3. Push to GitHub:
   ```bash
   git add .github/workflows/daily-update.yml
   git commit -m "Add daily README update workflow"
   git push origin main
   ```

4. Done! The workflow runs automatically every day

## What It Does

- Updates the "Last Updated" section with current date/time
- Adds a new entry to "Recent Updates" each day
- Commits changes automatically with message: "Daily update: YYYY-MM-DD"

## Manual Trigger

Go to Actions tab → "Daily README Update" → "Run workflow"

## Last Updated
Last update: 2026-01-11 08:41:03 UTC
Date: Sunday, January 11, 2026

### Recent Updates
- Sunday, January 11, 2026 - Automated daily update
