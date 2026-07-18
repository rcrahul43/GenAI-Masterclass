# Sheet ↔ Doc ↔ Resource sync

## Model

| Layer | Role | Source of truth |
|-------|------|-----------------|
| **Sheet** (`Tracker/GenAI-Masterclass-Tracker.xlsx`) | Progress, weeks, projects, mocks | Status / minutes / scores |
| **Docs** (`Modules/…/*.md`) | Deep explanations, labs, diagrams | Chapter content |
| **Resources** (sheet + Further Reading) | Official links / papers | URLs (regenerated from docs) |

## Daily use

**Need the full topic?**  
Modules → **Open Doc** → read chapter → use Further Reading inside the doc or the Resources sheet.

**Only need a link?**  
Resources → filter **Item ID** (e.g. `04-01`) → **Open Resource** / click **URL**.

## Make Open Doc work

### On this Mac (Excel)
1. Open the sheet → **Config**
2. `Local Root` = repo root ending with `/`  
   Example: `/Users/rahulchaudhari/Documents/Learning/AI/GenAI-Masterclass/`
3. `Link Mode` = `Local`

### Anywhere (Google Sheets / other computers)
1. Push this repo to GitHub
2. Config → `GitHub Base` = `https://github.com/YOUR_ORG/YOUR_REPO/blob/main/`
3. `Link Mode` = `GitHub`
4. Upload the xlsx to Google Sheets (optional)

## Re-sync resources after editing docs

```bash
cd /path/to/GenAI-Masterclass
python3 Tracker/build_tracker_xlsx.py
```

**Warning:** rebuild recreates the workbook. Backup Status columns before rebuilding if you have progress logged.

## What syncs vs what doesn’t

| Auto (on rebuild) | Stays in sheet only |
|-------------------|---------------------|
| Resource URLs from docs | Module Status |
| File paths / Open Doc targets | DailyLog entries |
| Week plan structure | Interview scores |
| Resource Count formulas | STAR strength ratings |
