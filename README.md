# Ozark Wilderness Waterways Club website

Static site for the Ozark Wilderness Waterways Club (OWWC), Kansas City, hosted on GitHub Pages at **owwckc.org**.

## Pages
- `index.html` — Home: what the club does, a year on the calendar, the monthly club meeting, membership
- `history.html` — Founding in 1956, Oz Hawksley, river-protection milestones, timeline
- `past.html` — OWWC Past archive: every "OWWC Past" newsletter item, year by year; grows with each issue
- `trips.html` — The club calendar (Ozark and Close-to-Home trips), how a trip works, upcoming trips, photos, resources
- `conservation.html` — The annual river clean-up (since 1960) and Missouri Stream Team #41 on the Blue River
- `newsletter.html` — The latest monthly newsletter only (calendar, trip recaps, "OWWC Past"); back issues stay in the members-only Google Drive
- `404.html` — Friendly not-found page for old links
- `css/style.css` — shared styles (colors from the club pin, Fraunces + Source Sans 3 from Google Fonts)
- `images/` — club logo (`owwc-logo.webp`, header/footer/404), club pin photo, group photo, 2026 trip photos from the newsletter, favicon, contour-line background
- `CNAME` — primary custom domain (`owwckc.org`)

## Rules and procedures
- **[CLAUDE.md](CLAUDE.md)** — content rules for anyone (person or agent) editing the site: no members' group links,
  no phone numbers, `owwckc@gmail.com` as the only contact, no member names, meeting naming.
- **[docs/processing-incoming.md](docs/processing-incoming.md)** — how to process files dropped in `incoming/`
  (file them in the private `archive/`, update every page, commit to `main`).

## To-do
- [ ] **Replace the dead links on the members' group page.** The club's mailing-list group home page still links
  to the old Google Sites pages, which are offline:
  - `https://sites.google.com/site/owwckc/Home/monthly-newsletter`
  - `https://sites.google.com/site/owwckc/Home/membership-application`

  Find the original files (the members' Google Drive archive, or the Wayback Machine at web.archive.org) or
  create new ones, then update the group page:
  - Newsletter → `https://owwckc.org/newsletter.html`
  - Membership application → doesn't exist on the new site yet. The group page tells people to "print, complete,
    and mail the membership application found on OWWC's public webpage", so build a printable
    `membership.html` (or a PDF in `images/`/`docs/`) and link it from `index.html#join`. Needs: the current dues,
    the form fields from the old application, and whether to publish the club's mailing address (301 SE 7th Street,
    Lee's Summit, MO 64063, from the newsletter masthead).
- [ ] Decide whether monthly meeting minutes will be posted on the site (see the procedure).

## Things a human should confirm or fill in
Search the HTML for `class="edit"` (dotted underline on the site: a detail to confirm) and `class="tba"` (a visible "to be announced" chip: a detail to fill in).

| Where | What |
|-------|------|
| `index.html` → Join | **Dues** (currently $25/year per family or individual, from the old site) |
| `newsletter.html` | Replace with each new issue (see the editing notes at the top of the file) |
| `trips.html` → Coming up | Upcoming trips. Copy a table row; a template row is in an HTML comment. Delete rows once they've happened. |
| `trips.html` → Photos | Links to online photo albums |
| `conservation.html` → Clean-up box, Stream Team | Next clean-up river and dates; next Blue River testing date |

Meeting time (potluck 6:30 p.m., meeting 7:30 p.m.) and place (Camp Lake of the Woods dining hall, 5700 Oakwood Rd.) were confirmed from the October 2026 newsletter.

**Phone numbers are purposefully left off the website**, for everyone, including the club. Contact goes through owwckc@gmail.com; members get coordinators' phone numbers in the emailed newsletter.

**Privacy:** see [CLAUDE.md](CLAUDE.md). In short: no current member names, no phone numbers, no personal email addresses, and no links to the members' group or mailing-list services. Refer to "the trip coordinator"; members get contact details in the emailed newsletter. The public contact is owwckc@gmail.com.

Once a detail is confirmed, delete the `class="edit"` so the dotted underline goes away.

## Editing
Plain HTML. Edit a file on GitHub and commit to `main`; the site updates within a minute or two.

## Sources for the history
- Club's former website (sites.google.com/site/owwckc): founding by families in 1956, annual clean-up since 1960, Stream Team #41, meetings, schedules, dues
- *Missouri Conservationist*, June 2007, "Clean Water": Stream Team #41 formed June 13, 1989; 19 tons of trash from eight rivers; 7,749 volunteer hours; Judith Guyn quote
- Associated Press photo, July 24, 1970: club clean-up on the Current River
- American Whitewater and Terrain Magazine on Oz Hawksley and the founding of American Whitewater
- OWWC newsletter, October 2026 (Vol. 76 No. 10): meeting times and place, 2026–27 calendar, 67th annual clean-up, "OWWC Past" items
- OWWC newsletter, September 2026 (Vol. 76 No. 9) and the 2026–27 Unified Calendar: "OWWC Past" items (1966 Can Clean-Up, 1996 40th, 2006 50th, 2011 Big Piney clean-up), 2026 trip list
- Ray Heady, *Hard Head I* (1980), quoted in the club's own description of itself

## Domains
Primary: **owwckc.org** (served by GitHub Pages; `www.owwckc.org` redirects automatically).

The other three domains forward (301) to `https://owwckc.org`:
- owwckc.com
- ozarkwildernesswaterwaysclub.org
- ozarkwildernesswaterwaysclub.com

### DNS for owwckc.org
| Type  | Host | Value |
|-------|------|-------|
| A     | @    | 185.199.108.153 |
| A     | @    | 185.199.109.153 |
| A     | @    | 185.199.110.153 |
| A     | @    | 185.199.111.153 |
| AAAA  | @    | 2606:50c0:8000::153 |
| AAAA  | @    | 2606:50c0:8001::153 |
| AAAA  | @    | 2606:50c0:8002::153 |
| AAAA  | @    | 2606:50c0:8003::153 |
| CNAME | www  | mcnairr.github.io |

Remove any old Google Sites records (A records / `ghs.googlehosted.com` CNAMEs / Google Sites "web forwarding") first.

### The other three domains
GitHub Pages serves only one custom domain per repository, so set up **domain forwarding** at the registrar
(permanent 301 redirect to `https://owwckc.org`, for both `@` and `www`).
