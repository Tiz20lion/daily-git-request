# Daily Git Request

A GitHub Actions workflow that automatically updates your repository's README.md file every day at midnight UTC. Perfect for maintaining an active commit history or keeping your repository fresh with daily updates.

## 👨‍💻 Developer

**Created by:** [Tiz](https://github.com/Tiz20lion)

## ✨ Features

- 🤖 **Automated Daily Updates**: Runs automatically every day at midnight UTC
- 📝 **README Updates**: Updates your README.md with current date and time
- 🔄 **Commit History**: Maintains a consistent daily commit history
- 🎯 **Manual Trigger**: Can be manually triggered via GitHub Actions UI
- ⚙️ **Easy Setup**: Simple configuration with no additional setup required

## 🚀 Quick Start

### Prerequisites

- A GitHub repository
- GitHub Actions enabled (enabled by default for public repos)

### Setup Instructions

1. **Clone or create your repository**
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   ```

2. **Copy the workflow file**
   
   Create the `.github/workflows/` directory if it doesn't exist:
   ```bash
   mkdir -p .github/workflows
   ```
   
   Copy the `daily-update.yml` file to `.github/workflows/daily-update.yml`

3. **Push to GitHub**
   ```bash
   git add .github/workflows/daily-update.yml
   git commit -m "Add daily README update workflow"
   git push
   ```

4. **Verify the workflow**
   - Go to your repository on GitHub
   - Click on the "Actions" tab
   - You should see "Daily README Update" workflow
   - The workflow will run automatically at midnight UTC, or you can trigger it manually using "Run workflow"

## 📋 How It Works

1. **Scheduled Execution**: The workflow runs daily at midnight UTC using a cron schedule (`0 0 * * *`)

2. **Repository Checkout**: The workflow checks out your repository using the latest version

3. **README Update**: Updates the README.md file with:
   - Current date and time (UTC)
   - Formatted date string
   - Entry in the "Recent Updates" section

4. **Auto-Commit**: Automatically commits and pushes the changes back to the repository

## ⚙️ Configuration

### Change Update Schedule

To change when the workflow runs, edit the cron expression in `.github/workflows/daily-update.yml`:

```yaml
schedule:
  - cron: '0 0 * * *'  # Change this to your preferred schedule
```

Cron format: `minute hour day month day-of-week`
- `0 0 * * *` = Every day at midnight UTC
- `0 12 * * *` = Every day at noon UTC
- `0 0 * * 1` = Every Monday at midnight UTC

### Customize README Update Format

Edit the `Update README` step in the workflow file to customize what gets written to your README.md:

```yaml
- name: Update README
  run: |
    # Your custom update logic here
```

### Manual Trigger

You can manually trigger the workflow at any time:
1. Go to your repository on GitHub
2. Click on the "Actions" tab
3. Select "Daily README Update" from the workflow list
4. Click "Run workflow" button

## 🔧 Troubleshooting

### Workflow Not Running

- **Check Actions tab**: Ensure the workflow file is in `.github/workflows/` directory
- **Verify permissions**: The workflow needs `contents: write` permission (already included)
- **Check schedule**: Verify the cron expression is correct
- **Repository settings**: Ensure GitHub Actions is enabled in repository settings

### Changes Not Being Committed

- **Check workflow logs**: Go to Actions tab and view the workflow run logs
- **Verify GITHUB_TOKEN**: The token should be automatically available (no setup needed)
- **Check branch protection**: If you have branch protection rules, you may need to adjust them

### README Not Updating

- **Check file path**: Ensure the workflow is updating the correct README.md file
- **View workflow logs**: Check for any errors in the workflow execution
- **Manual trigger**: Try manually triggering the workflow to test

## 📝 Example Output

After the workflow runs, your README.md will be updated with:

```markdown
# Daily Git Request

This repository is automatically updated daily via GitHub Actions.

## Last Updated
Last update: 2024-01-15 00:00:00 UTC
Date: Monday, January 15, 2024

## Update History
This README is automatically updated every day at midnight UTC.

### Recent Updates
- Monday, January 15, 2024 - Automated daily update
```

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

This project is open source and available for use.

## 🙏 Acknowledgments

- Created by [Tiz](https://github.com/Tiz20lion)
- Built with GitHub Actions

---

**Note**: This workflow requires write access to your repository. The `GITHUB_TOKEN` provided by GitHub Actions automatically has the necessary permissions for public repositories. For private repositories, ensure Actions have write access in repository settings.
