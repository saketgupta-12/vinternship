# Adding a New Cohort

To add a new cohort (e.g., Cohort 3), follow these steps:

## Step 1: Add Cohort Data
Edit `_data/cohorts.yml` and add the new cohort:

```yaml
cohort3:
  name: "NPTEL Cohort 3"
  display_name: "Cohort 3"
  start_date: "1st Mar 2026"
  status: "Upcoming"
  dashboard_available: false
  
  schedule:
    standups:
      days: ["Monday", "Wednesday", "Friday"]
      time: "9:00 PM IST"
```

## Step 2: Create Cohort Page
Create `_cohorts/cohort3.md`:

```markdown
---
layout: cohort-page
title: "Cohort 3"
cohort_id: cohort3
---
```

## Step 3: Create Dashboard File (if dashboard_available is true)
Create `dashboard-cohort3.html` in the root directory with your dashboard content.

## Step 4: Add Announcements (Optional)
Edit `_data/announcements.yml` to add cohort-specific announcements:

```yaml
- title: "Welcome to Cohort 3"
  date: "1st Mar 2026"
  cohorts: ["cohort3"]
  description: "Welcome message for the new cohort"
  content: "Your detailed announcement content here..."
```

That's it! The new cohort will automatically appear in the cohorts selection page at `/cohorts/`.

## File Structure

```
_data/
  cohorts.yml           # All cohort data
  announcements.yml     # All announcements

_layouts/
  cohort-page.html      # Unified cohort page template

_cohorts/
  cohort1.md            # Just 5 lines (uses layout)
  cohort2.md            # Just 5 lines (uses layout)
  cohort3.md            # Just 5 lines (uses layout)

cohorts.md              # Main landing page with cohort selection

dashboard-cohort1.html  # Separate dashboard for each cohort
dashboard-cohort2.html
dashboard-cohort3.html
```

## How It Works

This system uses **Jekyll Collections** (similar to `_projects/`):
- Each cohort page combines: General Info + Dashboard Link + Announcements
- Users select cohort from main landing page at `/cohorts/`
- Each cohort has its own dashboard HTML file
- All data is centralized in YAML files

## Benefits

✅ **Single cohort page**: Everything in one place per cohort  
✅ **Minimal duplication**: Each cohort file is just 5 lines  
✅ **Consistent styling**: All cohorts use shared template  
✅ **Easy navigation**: One landing page for cohort selection  
✅ **Separate dashboards**: Each cohort has its own dashboard file
