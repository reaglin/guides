# Guides Repo — Claude Code Instructions

## What This Repo Is

This is Dr. Ron Eaglin's personal guide catalog. It collects HTML instructional 
guides created across various projects and courses, organizes them by topic, and 
publishes them via a styled index.html page.

## Directory Structure

```
Guides/
├── index.html          ← Styled card/grid catalog of all guides
├── README.md
├── CLAUDE.md           ← This file
├── .claude/
│   └── commands/
│       └── sync-guides.md
└── [topic-folders]/    ← One subfolder per topic category
    └── *.html
```

## Where Guides Come From

Search recursively under:
- `~/Documents/` (primary location)

A file qualifies as a guide if it is an `.html` file AND its `<title>` tag or 
first `<h1>` contains instructional keywords (Guide, Tutorial, Reference, 
Overview, Introduction, How to, etc.), OR if its content appears to be 
structured educational material.

**Exclude** from search:
- Files already present anywhere inside this Guides repo directory
- Files inside `node_modules`, `.git`, or temp directories
- Files under `Documents/My Github/` (those are other repos, not source guides)

## Topic Categories

Use these categories as the default subfolder names. Create new ones if a guide 
clearly doesn't fit any of these:

| Folder name    | Use for |
|----------------|---------|
| `database`     | SQL, stored procedures, database design, T-SQL |
| `git`          | Git workflow, GitHub, version control |
| `web-dev`      | HTML, CSS, JavaScript, web development |
| `engineering`  | Engineering topics, stormwater, BMP, calculations |
| `dotnet`       | C#, .NET, WinForms, MAUI, Visual Studio |
| `python`       | Python scripts, Colab, data analysis |
| `linux`        | Linux commands, shell scripting |
| `algorithms`   | Data structures, algorithms, computer science |
| `ai-tools`     | AI, Claude, prompting, LLMs |
| `course-tools` | D2L, LearnDash, LMS, instructional design |
| `robotics`     | Kinova, robot programming, kinematics |
| `other`        | Anything that doesn't fit elsewhere |

When unsure about a category, ask before placing.

## index.html Requirements

The index.html must be a **self-contained, styled page** (no external CSS 
dependencies beyond Google Fonts). Design requirements:

- Card/grid layout (responsive, 3 columns on desktop, 1-2 on mobile)
- Each card contains:
  - Guide title (from the guide's `<title>` or `<h1>`)
  - 1–2 sentence description (summarized from the guide's content)
  - Category badge (colored label matching the folder name)
  - "View Guide" link button pointing to the relative file path
- Page header with title "Ron's Guide Collection" and a subtitle
- Clean, professional color scheme (navy/blue tones, white cards, subtle shadows)
- A search/filter bar that filters cards by title text (vanilla JS, no libraries)
- Footer with last-updated date

When regenerating index.html, scan all `.html` files in topic subfolders to 
rebuild the full list. Do not rely on a cached list.

## Git Workflow

After any file changes:
1. `git add -A`
2. `git commit -m "[brief description of what changed]"`
3. `git push origin main`

Always push at the end of a sync operation. If push fails due to authentication,
remind the user to check their GitHub credentials.

## Behavior Notes

- Always ask for confirmation before creating a new topic category not in the 
  list above.
- If a guide's title is generic (e.g., "Untitled" or "index"), read its content 
  briefly to determine a better title before using it in index.html.
- When copying a guide, preserve its original filename.
- Never modify the source guide files — only copy them.
