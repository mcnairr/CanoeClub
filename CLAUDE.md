# Working on the OWWC website

Static HTML site for the Ozark Wilderness Waterways Club, served by GitHub Pages from `main` at owwckc.org.
Everything committed to this repo is public, including Markdown files like this one.

## Content rules (apply to every page and every committed file)
1. **No links to the members' group site.** Do not put the club's mailing-list group URL, or anything a bot or
   person could use to find it, on the website or in any committed file. No `@groups.io` email addresses.
   Members receive the group link when they join. Say "the members' mailing list" if it must be mentioned at all.
2. **No phone numbers.** None, for anyone, including the club.
3. **One public contact: `owwckc@gmail.com`.** Use it for every point of contact (questions, joining, trip
   proposals, archive access). Never publish personal email addresses.
4. **No current member names.** Say "the trip coordinator", "a member", "the club". Exceptions already on the
   site: founder Oz Hawksley, and people quoted in published sources (e.g. *Missouri Conservationist*, Ray Heady's book).
   When adding "OWWC Past" history items, rewrite them without names.
5. **Meeting naming.** The monthly event is the **club meeting** (potluck, then business meeting). It is held on the
   second Saturday; mention that as the schedule, not as the event's name. Don't write "Second Saturday meetings."
   By contrast, Kansas City Crossroads **First Fridays** is the event's actual name; call it First Fridays.
6. Private source files (newsletters, calendars, minutes) are never committed: `incoming/` and `archive/` are git-ignored.

## Processing new information
Follow [docs/processing-incoming.md](docs/processing-incoming.md) whenever files appear in `incoming/`.

## Deploying
Committing straight to `main` and pushing is approved; the site redeploys automatically and the maintainer
checks the live site. Rollback = `git revert` the commit and push (or re-run the Pages deploy).
