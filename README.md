<div align="center">

# Auto Git <img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square" />

### Automated GitHub Contribution Graph Generator

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Shell Script](https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)
![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)
![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)

<br/>

Automatically generates **realistic, human-like** GitHub contributions that simulate real coding activity.<br/>
Keep your contribution graph green — on autopilot.

</div>

---

## :sparkles: Features

<table>
<tr>
<td width="50%">

**:brain: Human-Like Patterns**<br/>
Variable commit frequency with realistic daily, weekly, and seasonal patterns

**:calendar: Smart Scheduling**<br/>
Weekday-heavy activity with reduced weekends — just like a real developer

**:sleeping: Natural Off Days**<br/>
85% Sunday skip rate, 60% Saturday skip rate, 10% random weekday skips

</td>
<td width="50%">

**:bar_chart: Variable Intensity**<br/>
1-30 commits/day creating light-to-dark green contribution squares

**:label: Conventional Commits**<br/>
Realistic messages: `refactor:`, `fix:`, `docs:`, `perf:`, `test:`, etc.

**:repeat: Fully Automated**<br/>
Set it once — GitHub Actions handles everything

</td>
</tr>
</table>

---

## :rocket: Quick Setup

### 1. Push to GitHub

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git branch -M main
git push -u origin main
```

### 2. Enable GitHub Actions

1. Go to **Settings** > **Actions** > **General**
2. Select **Read and write permissions**
3. Check **Allow GitHub Actions to create and approve pull requests**
4. Click **Save**

### 3. (Optional) Configure Git Identity

Add these as **repository variables** in **Settings** > **Secrets and variables** > **Actions** > **Variables**:

| Variable | Description |
|----------|-------------|
| `GIT_USER_NAME` | Your preferred display name |
| `GIT_USER_EMAIL` | Your GitHub-verified email |

---

## :gear: How It Works

### Schedule (UTC)

| Day | Times (UTC) | Behavior |
|-----|-------------|----------|
| Mon - Fri | `04:30`, `09:00`, `13:00` | Regular commits (90% chance) |
| Saturday | `05:00` | Occasional commits (40% chance) |
| Sunday | — | Usually skipped (15% chance) |

### Commit Intensity Per Day

| Day Type | Commits | Trigger |
|----------|---------|---------|
| :fire: High Activity | 20-30 | 1 day per week (rotates weekly) |
| :thumbsup: Normal | 1-10 | Most weekdays |
| :zzz: Low Activity | 9-20 | 1 day per week (different from high) |

### Contribution Graph Colors

| Color | Commits |
|-------|---------|
| :white_large_square: None | 0 |
| :green_square: Light green | 1 |
| :green_square: Medium green | 2-3 |
| :green_square: Dark green | 4+ |

---

## :open_file_folder: Project Structure

```
auto_git/
├── .github/
│   └── workflows/
│       └── daily.yml           # GitHub Actions workflow (cron-based)
├── app/                        # Expo React Native app
│   ├── (tabs)/
│   │   ├── _layout.tsx         # Tab navigator
│   │   ├── index.tsx           # Home screen
│   │   └── explore.tsx         # Explore screen
│   ├── _layout.tsx             # Root layout
│   └── modal.tsx               # Modal screen
├── components/                 # Reusable UI components
├── constants/                  # Theme & color definitions
├── hooks/                      # Custom React hooks
├── logs/
│   ├── activity.log            # Human-readable activity log
│   └── metrics.jsonl           # JSON metrics per session
├── scripts/
│   ├── redo-2025.sh            # Backfill script (human-like patterns)
│   └── reset-project.js        # Expo project reset utility
└── package.json
```

---

## :wrench: Customization

### Change Commit Frequency

Edit the cron schedules in `.github/workflows/daily.yml`:

```yaml
schedule:
  - cron: '0 9 * * 1-5'   # Once daily at 9:00 UTC on weekdays
```

### Change Skip Probability

Modify the percentage thresholds in the workflow:

```bash
# Sunday - change 85 to your preferred skip %
if [ $RANDOM_NUM -lt 85 ]; then
```

### Add Custom Commit Messages

Extend the `MESSAGES` array in the workflow:

```bash
MESSAGES=("your: custom message" ...)
```

---

## :test_tube: Manual Trigger

1. Go to **Actions** tab in your repository
2. Click **Daily Auto Commit**
3. Click **Run workflow** > Select branch > **Run workflow**

---

## :warning: Troubleshooting

| Problem | Solution |
|---------|----------|
| No green dots | Verify commit email matches your GitHub account |
| Workflow not running | Check Actions tab for errors; ensure YAML is valid |
| Commits not on profile | Must be on default branch (`main`) |
| Fork not counting | Use your own repo, not a fork |
| Private repo hidden | Enable "Private contributions" in profile settings |
| Workflow disabled | GitHub disables after 60 days inactivity — re-trigger manually |

---

## :clock1: Time Zone Reference

| Timezone | UTC Offset | `04:30 UTC` becomes |
|----------|------------|---------------------|
| IST (India) | +5:30 | 10:00 AM |
| EST (US East) | -5:00 | 11:30 PM (prev day) |
| PST (US West) | -8:00 | 8:30 PM (prev day) |
| GMT (UK) | +0:00 | 4:30 AM |
| CET (Europe) | +1:00 | 5:30 AM |

---

<div align="center">

### Built with :heart: using GitHub Actions

![GitHub Stars](https://img.shields.io/github/stars/zohaib-codes48/auto_git?style=for-the-badge&color=yellow)
![GitHub Forks](https://img.shields.io/github/forks/zohaib-codes48/auto_git?style=for-the-badge&color=blue)

</div>
