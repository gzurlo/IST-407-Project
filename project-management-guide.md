# Project Management Guide

This document explains how we will track and manage our group project throughout the semester.  
Our approach is intentionally lightweight — the goal is to form strong project management habits without adding unnecessary tool overhead.

---

## Why We Do This

- **Keep the team aligned** — Everyone should know the project vision, the current plan, and recent progress at all times.
- **Document decisions and changes** — Projects always evolve. A clear record of what changed, when, and why prevents confusion and helps with grading.
- **Support AI-assisted work** — Modern AI tools are powerful, but their memory is limited. Having structured, up-to-date documents gives AI agents the context they need to work effectively with you, even after restarts or when using multiple agents.
- **Integrate with git** — By keeping planning artifacts in the repository, you can link tasks in the plan directly to your commits, making it easy to correlate planning with execution.

The key is not to have a “perfect” system — it’s to **use a system reliably**.

---

## The Three Core Documents

All three documents live in the `admin/` folder of your project repository. Copy the
`*_sample.md` templates there to `VISION.md`, `WORKPLAN.md`, and `WORKLOG.md` and make them your
own — don't edit the samples themselves.

### 1. `VISION.md`
- **Purpose:** Defines the project’s “North Star” — what you are trying to accomplish and why.
- **Stability:** Should remain unchanged unless there’s a major pivot.
- **Version History:** If the vision changes, archive the old vision at the bottom with the date and reason for the change.

### 2. `WORKPLAN.md`
- **Purpose:** Outlines the current plan and keeps a weekly record of progress.
- **Two Sections:**
  - **Active Plan:** Forward-looking tasks that are not yet complete. Update freely.
  - **Weekly Checkpoints:** Append-only log of completed, blocked, revised, or abandoned tasks. Add notes on *why* changes happened.
- **Task Status Tags:**
  - ✅ `:white_check_mark:` DONE
  - ⏳ `:hourglass_flowing_sand:` IN PROGRESS
  - 🚫 `:no_entry_sign:` BLOCKED
  - ❌ `:x:` ABANDONED
  - 🆕 `:new:` NEWLY ADDED this week
  - 🔄 `:arrows_counterclockwise:` REVISED scope or details

_Note: Github supports a [wide range of emojis](https://gist.github.com/rxaviers/7360908) - Use what you want!_

- **Hierarchy:** Use nested lists to break down milestones into sub-tasks. Conventionally use _Milestones_ to groups _Tasks_ that are related to the same goal.  Maintain hierarchy in the **weekly checkpoints** section.

### 3. `WORKLOG.md`
- **Purpose:** Personal contributions log for each team member.
- **Format:** Date, your name, what you worked on, and which WORKPLAN task it relates to.
- **Historical only:** Never edit old entries — always append new ones.

---

## How to Maintain These Documents

### VISION.md
1. Write the initial vision in the “Current Vision” section.
2. If a major pivot happens:
   - Move the old vision to the “Version History” section with date and reason.
   - Write the new vision at the top.

### WORKPLAN.md
1. Keep the **Active Plan** current:
   - Add new tasks with 🆕 and the date.
   - Update statuses as work progresses.
   - Remove completed/blocked/revised/abandoned tasks by moving them to Weekly Checkpoints.
2. At the end of each week:
   - Move all finished/changed tasks into **Weekly Checkpoints** with date and notes.
   - Leave the Active Plan showing only remaining work.
3. If the project changes significantly:
   - For a **pivot**: Archive the entire Active Plan into Weekly Checkpoints under a “Project Pivot” heading, then start fresh.
   - For **major adaptations**: Move affected tasks to Checkpoints, tag them ❌ or 🔄, and add new ones to the Active Plan.
   - For **minor additions**: Just add 🆕 tasks under the relevant milestone.

### WORKLOG.md
1. Add an entry every time you do meaningful work.
2. Be specific — “worked on code” is not enough; say what part and why.
3. Reference the related WORKPLAN task so it’s easy to trace progress.

---

## Using These Documents with AI

You can copy relevant sections of these files into AI prompts to:
- Summarize current status.
- Generate next-step suggestions.
- Identify blockers and propose solutions.
- Update the plan automatically.

Because these files are plain Markdown, they can be read, edited, and version-controlled by both humans and AI.

---

## Linking to Git Commit History

When you make commits:
- Reference the related WORKPLAN task in the commit message.
- Example: 

~~~
git commit -m "✅ Implement PCA for feature reduction — relates to Milestone 2, task 'Reduce feature set'"
~~~

- This creates a clear link between your commits and your project plan, making it easy to see how plans translate into work.

---



## Worked Examples

Below are two example scenarios showing how `VISION.md`, `WORKPLAN.md`, and `WORKLOG.md` evolve in response to real-world project changes.

---

### Example 1: Major Pivot

#### Before Pivot
**VISION.md**
```

## Current Vision

Date: 2025-09-05
We aim to predict disease diagnoses using patient EHR data.

## Key Constraints

* Source: Public EHR dataset from XYZ University
* Primary method: Random Forest classifier

## Version History

(none yet)

```

**WORKPLAN.md (Active Plan excerpt)**
```

### Milestone 1: Data Prep

* [ ] ⏳ Acquire EHR dataset (Alice)
* [ ] Clean data (Bob)
* [ ] Feature engineering (Carol)

```

**WORKLOG.md**
```

2025-09-06 — Alice: Downloaded EHR dataset and began schema review.

```

#### Pivot Happens (Week 5)
- EHR dataset turns out to be simulated and unusable.
- Team switches to predicting educational success outcomes with school performance data.

**VISION.md after pivot**
```

## Current Vision

Date: 2025-10-03
We aim to predict student educational success outcomes using school performance and attendance data.

## Key Constraints

* Source: National School Performance Database
* Primary method: Random Forest (bagging)

## Version History

### 2025-10-03 — Pivot

Previous vision: Predict disease diagnoses using EHR data.
Reason: Dataset quality issues made the approach infeasible.

```

**WORKPLAN.md**
```
## Active Plan

### Milestone 1: Data Prep (New Vision)

* [ ] 🆕 Clean and preprocess dataset (Bob)
* [ ] 🆕 Define predictive features (Carol)

## Weekly Checkpoints

### **Week 5 (10/03)**

### Milestone 1: Data Prep (New Vision)

* ✅ Acquire school performance data (Alice)

**Project Pivot**

Archived old plan due to dataset pivot:

### Milestone 1: Data Prep

* ✅ Acquire EHR dataset (Alice)
* ❌ Clean data (Bob) — abandoned due to pivot
* ❌ Feature engineering (Carol) — abandoned due to pivot
```

**WORKLOG.md**
```

2025-10-03 — Alice: Located and downloaded school performance dataset; documented data schema.

```

---

### Example 2: Minor Evolution

#### Before Change
**VISION.md**
```

## Current Vision

Date: 2025-09-05
We aim to predict market movements using consumer sentiment extracted from social media data.

```

**WORKPLAN.md (Active Plan excerpt)**
```

### Milestone 2: Feature Engineering

* [ ] ⏳ Extract sentiment scores from tweets (Bob)
* [ ] Aggregate scores into daily indicators (Alice)

```

**WORKLOG.md**
```

2025-09-14 — Bob: Wrote initial sentiment extraction pipeline.

```

#### Minor Change Happens (Week 4)
- Team decides to add PCA-based dimensionality reduction to improve model performance.

**WORKPLAN.md after change**
```

## Active Plan

### Milestone 2: Feature Engineering

* [ ] Aggregate scores into daily indicators (Alice)
* [ ] 🆕 Implement PCA for dimensionality reduction (Carol, added 9/26)

## Weekly Checkpoints

### **Week 4 (9/26)**

### Milestone 2: Feature Engineering
* ✅ Extract sentiment scores from tweets (Bob)
* 🆕 Implement PCA for dimensionality reduction — added this week.

```

**WORKLOG.md**
```

2025-09-26 — Carol: Researched PCA parameters for feature reduction. Added initial PCA transform to pipeline.

```

---

## Final Notes

- Commit updates to these documents **at least once a week**.  This is a large part of your project grade!
- Consistency matters more than perfection — aim for accurate, current, and readable updates.
- Use these documents as living tools, not just grading requirements. If you keep them well-maintained, they will make your work easier and your AI assistance more effective.

