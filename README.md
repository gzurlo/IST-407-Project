# IST 407 — Group Project

Welcome to your group's project repository. **One repository per group** — the point of contact
created it, and everyone on the team is a collaborator. Do all of your project work here.

## Folders — use them as described

| Folder | What goes here |
|---|---|
| `admin/` | **All project-management files.** Copy the `*_sample.md` templates to `VISION.md`, `WORKPLAN.md`, and `WORKLOG.md` and make them your own — don't edit the samples. See `project-management-guide.md`. |
| `checkpoint1/` | **Proposal** (due Mon Sep 21) — rubric + your `proposal.md`. |
| `checkpoint2/` | **Checkpoint 2** (due Wed Oct 28) — rubric + `example.ipynb` + your `submission.ipynb`. |
| `final-presentation/` | **Final Presentation** (in class, Mon Dec 7) — rubric; put your slides here. |
| `final-report/` | **Final Report** (due Dec 15) — rubric + your `final_report.md` (or `.ipynb`). |
| `work/` | Create this for supporting work — exploratory notebooks, scratch analysis. Subfolders welcome. |
| `data/` | Create this for **small** (<100 MB) data files. |

**Each checkpoint's rubric names the exact file to submit** (`proposal.md`, `submission.ipynb`,
`final_report.md`). That named file is what I open to grade — put other work in `work/`. Follow the
rubrics. Whatever is on `main` at the deadline is what gets graded; late checkpoints lose 50%.

> ⚠️ **Never commit a data file larger than 100 MB.** GitHub will reject it and untangling the
> result is a mess I'll have to help you fix. For the final report, **link** to your data rather
> than committing it. See the data note in `final-report/`'s rubric.

## Regular activity is graded

There should be new commits **every week** from here on. Lack of regular, visible activity lowers
your grade even if the final result is excellent — individual contributions are tracked and used to
assign your individual project score.

## How your individual grade works

Your **individual** project score (30 of 100 points, scored 0/1/2 across three phases) reflects
*your* substantive contribution. Evidence comes from two places: your **commit history** and the
group's **`admin/WORKLOG.md`**.

**Keep `admin/WORKLOG.md` current and attribute every entry by name.** This is how contributions
that produce no commits — research, writing, analysis, talking to a stakeholder — get counted. If
your name isn't in the record for a phase, there's nothing to credit, and a late burst can't make
up for phases you sat out (a student who contributes only at the end scores 0/0/2). Keeping the log
current is part of the work.

## Working together: branches and pull requests

This is the repository where the branch-and-PR workflow matters — several people committing to one
repo. Pull `main` before you start; make a branch for your piece
(`git checkout -b <your-name>/<what-youre-doing>`); commit, push, and open a **pull request** into
`main`; have a teammate review and merge. Don't all commit straight to `main` — that's how you get
conflicts you can't untangle the night before a deadline.

## Setup

Clone this repo to a normal folder, open it in VS Code, and **"Reopen in Container"** (or start a
**Codespace**). Do **not** use "Clone Repository in Container Volume" — your files end up hidden
inside the Docker VM. The devcontainer here is identical to your individual course repo; see that
repo's README for the full setup walkthrough and troubleshooting.

---

**Read `project-management-guide.md` next** — it explains how `VISION.md`, `WORKPLAN.md`, and
`WORKLOG.md` work, with worked examples. Questions? Email the instructor with `[IST407]` in the
subject.
