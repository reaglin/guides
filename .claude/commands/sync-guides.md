# Sync Guides

Search `~/Documents/` recursively for HTML files that qualify as instructional 
guides (see CLAUDE.md for qualification criteria).

For each HTML file found that is NOT already present somewhere in this Guides 
repo directory:

1. Read the file's `<title>` tag and first `<h1>` to determine its title.
2. Skim its content to write a 1–2 sentence description.
3. Determine the best topic category from the list in CLAUDE.md.
4. If the category is not in the standard list, ask for confirmation before 
   creating it.
5. Copy the file into the appropriate topic subfolder in this repo.

After processing all new files (or if no new files are found, still do this):

6. Regenerate `index.html` by scanning all `.html` files in all topic subfolders.
   Rebuild every card — do not skip existing guides.
7. Ensure the index.html matches the design spec in CLAUDE.md.
8. Update the "last updated" date in the footer to today's date.

Finally:

9. Stage all changes with `git add -A`
10. Commit with a message like: `"Sync: added N new guides, updated index"`
11. Push to GitHub with `git push origin main`

Report a summary of what was added and what was skipped.
