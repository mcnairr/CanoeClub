# Ozark Wilderness Waterways Club website

Static site for the Ozark Wilderness Waterways Club (OWWC), Kansas City, hosted on GitHub Pages at **owwckc.org**.

## Pages
- `index.html` — Home: what the club does, a year on the calendar, Second Saturday meetings, membership
- `history.html` — Founding in 1956, Oz Hawksley, river-protection milestones, timeline
- `trips.html` — The club calendar (Ozark and Close-to-Home trips), how a trip works, upcoming trips, photos, resources
- `conservation.html` — The annual river clean-up (since 1960) and Missouri Stream Team #41 on the Blue River
- `newsletter.html` — The latest monthly newsletter only (calendar, trip recaps, "OWWC Past"); back issues stay in the members-only Google Drive
- `404.html` — Friendly not-found page for old links
- `css/style.css` — shared styles (colors from the club pin, Fraunces + Source Sans 3 from Google Fonts)
- `images/` — club pin, group photo, 2026 trip photos from the newsletter, favicon, contour-line background
- `CNAME` — primary custom domain (`owwckc.org`)

## Things a human should confirm or fill in
Search the HTML for `class="edit"` (dotted underline on the site: a detail to confirm) and `class="tba"` (a visible "to be announced" chip: a detail to fill in).

| Where | What |
|-------|------|
| `index.html` → Join | **Dues** (currently $25/year per family or individual, from the old site) and the **club email address** |
| `newsletter.html` | Replace with each new issue (see the editing notes at the top of the file) |
| `trips.html` → Coming up | Upcoming trips. Copy a table row; a template row is in an HTML comment. Delete rows once they've happened. |
| `trips.html` → Photos | Links to online photo albums |
| `conservation.html` → Clean-up box, Stream Team | Next clean-up river and dates; next Blue River testing date |

Meeting time (potluck 6:30 p.m., meeting 7:30 p.m.) and place (Camp Lake of the Woods dining hall, 5700 Oakwood Rd.) were confirmed from the October 2026 newsletter.

**Privacy:** keep member names, phone numbers, and personal email addresses off the public site. Refer to "the trip coordinator"; members get contact details in the emailed newsletter.

Once a detail is confirmed, delete the `class="edit"` so the dotted underline goes away.

## Editing
Plain HTML. Edit a file on GitHub and commit to `main`; the site updates within a minute or two.

## Sources for the history
- Club's former website (sites.google.com/site/owwckc): founding by families in 1956, annual clean-up since 1960, Stream Team #41, meetings, schedules, dues
- *Missouri Conservationist*, June 2007, "Clean Water": Stream Team #41 formed June 13, 1989; 19 tons of trash from eight rivers; 7,749 volunteer hours; Judith Guyn quote
- Associated Press photo, July 24, 1970: club clean-up on the Current River
- American Whitewater and Terrain Magazine on Oz Hawksley and the founding of American Whitewater
- OWWC newsletter, October 2026 (Vol. 76 No. 10): meeting times and place, 2026–27 calendar, 67th annual clean-up, "OWWC Past" items (1971, 1976, 1986, 2016)

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
