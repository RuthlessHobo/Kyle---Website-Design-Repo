# Push this repo to your GitHub

This folder is already a git repo with one commit. Two ways to get it onto GitHub.

## Option A — GitHub CLI (easiest)
```bash
cd kyle-website-design-repo
gh repo create "kyle-website-design-repo" --private --source=. --remote=origin --push
```
(Use `--public` instead of `--private` if you want it public.)

## Option B — Manual
1. Create an empty repo on github.com named `kyle-website-design-repo` (no README/license — this folder has them).
2. Then:
```bash
cd kyle-website-design-repo
git remote add origin https://github.com/<YOUR_USERNAME>/kyle-website-design-repo.git
git branch -M main
git push -u origin main
```

## Connect it to Claude Design
Once it's on GitHub, connect the repo as project knowledge (or paste DESIGN.md + the relevant references/ files) before a build, so Claude Design reads the constraints first.
