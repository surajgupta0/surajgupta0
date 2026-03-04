# 🛠️ README Setup Guide — Surajkumar Gupta

## Step 1 — Create Your Profile Repo
Go to GitHub → New Repository → Name it **exactly** `surajgupta0` (same as your username)
✅ Make it **Public** + check **"Add README"**

## Step 2 — Paste the README.md
Replace the default content with the full README.md content provided.

## Step 3 — Enable the Snake Animation 🐍
The snake contribution graph needs a GitHub Action.

Create this file in your profile repo:
📁 `.github/workflows/snake.yml`

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"   # Runs every day at midnight
  workflow_dispatch:        # Manual trigger

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

After pushing this file, go to:
**Actions tab → "Generate Snake" → Run workflow**

The snake SVG will appear at:
`https://raw.githubusercontent.com/surajgupta0/surajgupta0/output/github-snake-dark.svg`

## Step 4 — Services Used (All Verified Working on GitHub)

| Service | Used For | Status |
|---------|----------|--------|
| `capsule-render.vercel.app` | Header/Footer wave | ✅ Reliable |
| `readme-typing-svg.demolab.com` | Animated typing | ✅ Reliable |
| `img.shields.io` | All badges | ✅ Very reliable |
| `github-readme-stats.vercel.app` | Stats + Top Langs | ✅ Reliable |
| `streak-stats.demolab.com` | Streak card | ✅ Reliable |
| `github-readme-activity-graph.vercel.app` | Activity graph | ✅ Reliable |
| `github-profile-trophy.vercel.app` | Trophy display | ✅ Reliable |
| `komarev.com/ghpvc` | Profile view counter | ✅ Reliable |
| GitHub Actions / Platane/snk | Snake animation | ✅ Self-hosted |

## Notes
- The coding-freak GIF (`matrix.svg` from rodrigograca31) is a raw SVG from GitHub itself — always works
- All `img.shields.io` badges are static and never break
- Stats cards may show "failed" if your repos are private — make some public!
