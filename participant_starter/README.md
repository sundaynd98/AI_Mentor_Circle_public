# Participant Starter Workspace

This is your project folder for AI Mentor Circle.

Click "Use this template" on GitHub to create your own copy of this repo, then clone it to your machine.

---

## Project Structure

```
your-project/
│
├── CLAUDE.md                    ← Claude's briefing doc — reads this automatically every session
│
├── .claude/
│   └── commands/                ← Custom slash commands (type /command-name in Claude Code)
│
├── .env.example                 ← Template for secret variables (safe to share — no real values)
├── .gitignore                   ← Tells Git what to never track (e.g. .env, node_modules)
├── README.md                    ← This file
│
├── docs/                        ← All project context, research, planning, and specs
│   ├── reports/
│   │   ├── participant_profile.md   ← Who you are and how you like to work (Session 1)
│   │   ├── decisions.md             ← Why you made key choices — append-only log
│   │   └── session_log.md           ← What you did and tried each session — running narrative
│   ├── problem_definition.md    ← What you're solving and why (Session 2)
│   ├── research/                ← User research notes, interview guides (Session 3)
│   └── specs/                   ← Design specs, UX spec, MVP specs (Sessions 4–5)
│
├── prompts/                     ← Prompt templates you write and refine (Sessions 3–4)
│
├── workflows/                   ← Course workflow guides — reference with @workflows/[name].md
│
└── src/                         ← Your source code — add this when you start building (Session 5+)
```

**Phase 2 folders (add when you need them):**
- `src/` — add when starting the POC build (Session 5)
- `data/` — add when you need to mock or store structured data
- `docs/eval/` — add for evaluation reports (Session 3–4)

---

## Artifacts You'll Produce (and where they go)

| Session | Artifact | Location |
|---------|----------|----------|
| 1 | participant_profile.md | docs/reports/ |
| 1 | CLAUDE.md | project root |
| 1 | problem_definition.md | docs/ |
| 1 | testing_prompt.md | prompts/ |
| 2 (homework) | evaluation_design_report.md | docs/ |
| 2 (homework) | evaluations_data.csv | data/ |
| 2 (homework) | spike/ | docs/research/ |
| 3 | user_research_plan.md | docs/ |
| 3 | interview_analysis_prompt.txt | prompts/ |
| 4 | evaluation_at_scale_design.md | docs/ |
| 4 | llm_as_judge_prompt.txt | prompts/ |
| 4 | user_experience_spec.md | docs/specs/ |
| 5 | implementation_design.md | docs/ |
| 5 | mvp_specs.md | docs/specs/ |
| 6 | architecture_spec.md | docs/specs/ |
| 6 | context_management_design.md | docs/ |

*Session numbers track when each artifact is first produced. The evaluation set (report, CSV, spike) is now front-loaded into Session 2 homework; the Session 3 column may shift slightly as that plan is finalized.*

---

## Key Habits

- **Update CLAUDE.md every session** — it grows with your project
- **Append to session_log.md at the end of every session** — run `/wrap-up` in Claude Code to walk through your reflection and draft the entry
- **Log major decisions to decisions.md** — never edit past entries, only append
- **Connect to GitHub** after Session 1 — first homework

---

## Getting Course Updates Into Your Project

Your project and the course repo are separate (you made yours from a template), so course updates — new or revised workflows, handouts, and session files — don't arrive on their own. Here's the full, safe way to bring them in.

**1. One-time setup — connect the course repo as a remote named `course`:**

```powershell
git remote add course https://github.com/sundaynd98/AI_Mentor_Circle_public.git
```

Run this once. Confirm it worked with `git remote -v` — you should see `course` listed alongside `origin`.

**2. Download the latest course files:**

```powershell
git fetch course
```

This downloads everything new from the course repo without changing any of your files yet.

**3. Bring the new and updated files in — let Claude Code do this so your own work isn't overwritten.** You've personalized some files (your root `CLAUDE.md`, your `docs/`, your `prompts/`), so don't blanket-overwrite. Ask Claude Code:

> "I just ran `git fetch course`. Compare `course/main` against my project and bring in every new or updated course file — especially anything in `workflows/` and any new `sessions/` materials — but don't overwrite files I've personalized (my root `CLAUDE.md`, `docs/`, `prompts/`). List what changed before we commit."

**4. Save the updates to your repo:**

```powershell
git add .
git commit -m "Bring in latest course updates"
git push
```

Do this whenever you're told a course file has changed (or at the start of a session, to be safe).

**5. OR create a skill to do this at the beginning of each class session:**

[enter info about skill here - TBD]

---

## Tips

Ask Claude to help with any of this:
- *"Help me write my participant_profile.md"*
- *"Append a session log entry for what we just did"*
