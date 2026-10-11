# Ozark Wilderness Waterways Club website

Static site for the Ozark Wilderness Waterways Club (OWWC), Kansas City — hosted on GitHub Pages.

- `index.html` — Home: what we do, mission, Second Saturday meetings, Stream Team #41
- `history.html` — Founders & history (Oscar "Oz" Hawksley)
- `trips.html` — Recent trips, club photos, resources
- `css/style.css` — shared styles (colors from the club pin)
- `images/` — club pin and photos
- `CNAME` — primary custom domain (`owwckc.org`)

## Editing
Plain HTML — edit a file on GitHub and commit; the site updates within a minute or two.
To add a trip, copy the template in the comment at the top of the trip list in `trips.html`.

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
