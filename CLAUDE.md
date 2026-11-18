# CLAUDE.md

## Overview

A personal notes organizer maintained by Claude Code.

## Folder Structure

```
raw/            -- documents containing unprocessed notes
processed/      -- documents containing processed notes
notes/          -- markdown pages for the organized notes (one page per topic)
notes/index.md  -- table of contents of all the notes pages
notes/log.md    -- append-only record of all operations
```

## Workflow

1. Read the unprocessed notes in the `raw/` folder. Look at every file inside `raw/`.
2. Process each document, and every note inside it, using the Processing Instructions below.
3. Once a document is processed, move it to the `processed/` folder.
4. Add an empty `New_Notes.md` file to `raw/` to collect new notes.

## Processing Instructions

When the user adds a new note to `raw/` and asks you to ingest it:

- Read `raw/New_Notes.md` and process every note in it.
  - If a note has one or more URLs, visit them and write an accurate short description.
  - For notes with text up to 100 characters, add the text verbatim. For longer notes, summarize to 100 characters or fewer.
- Read any other files added to `raw/` and process each file as a separate note.
- Identify the core concepts/topic of the resource.
- Identify the main topic and any related topics. If the resource fits neatly into a single main topic, a related topic is not required.
- Read `notes/index.md` first to find relevant topic pages.
- If there is no match, create a new topic page. See the List of Topics below for topics of interest.
- Add a new item to the main topic page, keeping newer notes at the top.
- Add back-links (`[[Page_Name]]`) to connect related topics. If a related topic page does not exist, create it.
- Update `notes/index.md` with any new pages and a one-line description of each.
- Append an entry to `notes/log.md` with the date, source name, and what changed.

## Update the Website

This vault is published as a MkDocs site on GitHub Pages (repo: `gavacharles/personal-notes`, site: https://gavacharles.github.io/personal-notes/). After ingesting new notes:

- Update the "Latest Finds" section in `notes/index.md` with the 3 most recently added notes, each from a different topic page.
- If a new topic page was created, add it to the `nav:` list in `mkdocs.yml`.
- Commit and push the changes to GitHub (`git add`, `git commit`, `git push`) so the site's GitHub Actions workflow rebuilds and redeploys automatically. `processed/` stays gitignored and is never pushed.

## List of Topics

Topics can be technology focused (e.g. Python, Xarray) or theme focused (e.g. Climate Change, Agriculture). When a note covers both, use the **theme-focused topic as the main topic** and link the technology topic as a related topic.

**Technology Topics**
- Machine Learning
- Embeddings
- Deep Learning
- SQL
- Python
- Data
- Agentic Coding

**Thematic Topics**
- Climate Change
- Urban Planning
- Agriculture
- Remote Sensing
- Cartography

## Topic Page Format

Every topic page must follow this structure:

```markdown
# Page Title

**Summary**: One to two sentences describing this page.
**Last updated**: Date of most recent update.

---

Main content goes here.
```

## Note Formatting Instructions

- Use Markdown for each note, with one bullet point per note.
- Notes with URLs:
  - Format: `[Title](url): <description> <keywords>`
  - Write a 1–2 line description based on the URL's content.
- Notes with just text:
  - Format: `*Title*: <description> <keywords>`
  - For text up to 100 characters, add it verbatim. For longer text, summarize to 100 characters or fewer.
- Add 3–6 keywords that best describe the note and will help recall it later.
- Link to related topics using `[[wiki-links]]` throughout the text.

Example:

```markdown
- [Xarray Docs](https://docs.xarray.dev): N-dimensional labeled arrays for Python, widely used for climate and raster data. `xarray` `netcdf` `arrays` `python` — see [[Python]]
- *Crop yield idea*: Use NDVI time series to predict wheat yield per field. `ndvi` `yield` `wheat` `time-series` — see [[Remote_Sensing]]
```

## Rules

- Page names use Title Case with underscores (e.g. `Machine_Learning.md`).
- Write in clear, plain language.
- Always update `notes/log.md` after any change.
