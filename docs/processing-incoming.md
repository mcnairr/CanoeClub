# Processing files dropped in `incoming/`

The maintainer drops club material (newsletters, calendars, meeting minutes, notes from members) into
`incoming/`. An agent picks it up, files it, and updates the website. Read [CLAUDE.md](../CLAUDE.md) first:
its content rules apply to every change.

`incoming/` and `archive/` are git-ignored on purpose. The repo is public and GitHub Pages serves every
committed file, and source documents contain member names, phone numbers, and personal email addresses.
**Never commit source files.** Only the rewritten, rule-compliant website content gets committed.

## 1. Read everything
Open every file in `incoming/` completely (PDFs page by page; for saved web pages, read the visible text).
For each one, note what it is, which month or issue it covers, and its date.

## 2. File it in `archive/`
Move (don't copy) each file to the matching folder, renamed so it sorts by date:

| Content | Folder | Name pattern |
|---------|--------|--------------|
| Monthly newsletter | `archive/newsletters/YYYY/` | `YYYY-MM-newsletter-volNN-noN.pdf` |
| Unified calendar / trip schedule | `archive/calendars/` | `YYYY-YY-unified-calendar-as-of-YYYY-MM.pdf` |
| Meeting minutes | `archive/minutes/YYYY/` | `YYYY-MM-DD-minutes.ext` |
| Photos for the site | `archive/photos/YYYY/` (originals) | `YYYY-MM-place.jpg` |
| Saved web pages, how-to notes, anything else | `archive/reference/<short-topic>-YYYY-MM/` | keep the page and its `_files` folder together |

Create folders as needed. If a file doesn't fit, use `archive/reference/` and mention it in the report.

## 3. Decide what is newer
Compare each file's date with what the site already says (the newsletter page names the current issue).
Newer information replaces older; older information only fills gaps. Never overwrite something from a
later issue with something from an earlier one (for example, a planned trip that a later issue reports
as having happened somewhere else).

## 4. Update the site
Work through every page, not just the obvious one.

**A new monthly newsletter** (only when it is newer than the issue on `newsletter.html`):
- `newsletter.html`: replace the whole issue (title and date, greeting, calendar, recaps, OWWC Past).
  This page always holds only the latest issue.
- `trips.html` → Coming up: rebuild from the newsletter calendar. Drop events whose dates have passed.
- `index.html`, `conservation.html`, `history.html`: refresh any facts the issue changes (clean-up river and
  dates, the clean-up count, Stream Team testing dates, meeting place and times, dues, trip examples).
- Trip photos: save resized copies (about 640 px wide, JPEG) into `images/` and use them in the recaps.

**OWWC Past (the monthly history column), from every newsletter, old or new:**
- Add each item to `past.html` under its decade, in year order, then month order within a year, with the
  month in `<strong>`. Add the issue to the "Compiled from" line at the bottom.
- Items about events 20 or more years ago keep people's names as the column gives them. Rewrite more recent
  items without member names ("a member", "a family crew", "two members").
- If an item is a real milestone (a clean-up record, an anniversary, a first), also add it to the timeline
  on `history.html`, and to its prose if it says something about the club's traditions.

**Calendars:** update the Coming up table on `trips.html` and the trip examples on `index.html` and
`trips.html`. Keep calendar rows free of coordinator names, phone numbers, and emails.

**Meeting minutes:** until a minutes page exists, file them and pull only public facts (new trips, clean-up
plans, events) into the pages above. If the club decides minutes should be posted, add a page for them,
following the same privacy rules, and update this procedure.

**Instructions from club members about the website:** apply them if they don't conflict with CLAUDE.md;
if they do, stop and ask the maintainer.

## 5. Check before committing
Run from the repo root:

```sh
# Nothing should match. (Allowed: owwckc@gmail.com. CLAUDE.md names the blocked services only in its rule text.)
grep -nEi 'groups\.google|mailchimp|list-manage|groups\.io|meetup\.com|constantcontact|[0-9]{3}[-. )]+[0-9]{3}[-. ][0-9]{4}|@(hotmail|yahoo|aol|outlook|icloud|comcast)\.' -- *.html
grep -nEi '[[:alnum:]_.+-]@(googlegroups|groups\.io|meetup)|(groups\.google\.com|list-manage\.com|groups\.io|meetup\.com)/|[0-9]{3}[-. )]+[0-9]{3}[-. ][0-9]{4}' -- *.md docs/*.md
grep -n 'Second Saturday' -- *.html
git status --short   # no files from incoming/ or archive/ should appear
```

Then skim each changed page for current member names and fix any you find.
Open the changed pages in a browser (or read the diff carefully) for broken markup.

## 6. Commit and deploy
Commit straight to `main` and push; GitHub Pages redeploys in a minute or two. This is approved: traffic is
low, the maintainer checks the live site, and rollback is a `git revert` plus push.

Commit message: say which source files were processed and what changed on which pages.

## 7. Report
Tell the maintainer: where each file was filed, what changed on each page, anything left out on purpose
(and why), and anything that needs a human decision (add it to the To-do list in `README.md`).
