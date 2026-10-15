# Working on the OWWC website

Static HTML site for the Ozark Wilderness Waterways Club, served by GitHub Pages from `main` at owwckc.org.
Everything committed to this repo is public, including Markdown files like this one.

## Content rules (apply to every page and every committed file)
1. **No links to the members' group or mailing-list services.** Do not put a URL, a link, or an email address for
   any group-membership or email-list service on the website or in any committed file. Blocked: Google Groups
   (groups.google.com), Mailchimp (mailchimp.com, list-manage.com), groups.io, Meetup (meetup.com), and
   Constant Contact (constantcontact.com), plus any address `@` those domains. Members receive the group link when
   they join. Say "the members' mailing list" if it must be mentioned at all.
2. **No phone numbers.** None, for anyone, including the club.
3. **One public contact: `owwckc@gmail.com`.** Use it for every point of contact (questions, joining, trip
   proposals, archive access). Never publish personal email addresses.
4. **No current member names.** Say "the trip coordinator", "a member", "the club". Exceptions: history from
   20 or more years ago may name people as the source does (e.g. "OWWC Past" items for 2006 and earlier, as of 2026);
   founder Oz Hawksley; and people quoted in published sources (e.g. *Missouri Conservationist*, Ray Heady's book).
   History items from the last 20 years are rewritten without names.
5. **Meeting naming.** The monthly events are **Club Meetings** (potluck, then business meeting), held on the second
   Saturday of the month. Call them club meetings; the second Saturday is when they happen, not their name.
   Don't write "Second Saturday meetings."
6. **Neutral on where members live.** Do not frame trips or members by distance from Kansas City: no "Close to Home"
   or "Ozark" tags on calendar events, no "around the metro" or "carpool from Kansas City". The club meets in Kansas City,
   and that fact can be stated. History items may keep historical names such as "the Close-to-Home group".
7. Private source files (newsletters, calendars, minutes) are never committed: `incoming/` and `archive/` are git-ignored.

## Processing new information
Follow [docs/processing-incoming.md](docs/processing-incoming.md) whenever files appear in `incoming/`.

## Deploying
Committing straight to `main` and pushing is approved; the site redeploys automatically and the maintainer
checks the live site. Rollback = `git revert` the commit and push (or re-run the Pages deploy).
