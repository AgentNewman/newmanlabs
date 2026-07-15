## [2026-04-29 22:37] Added GA4 tracking
- Property: Newman Labs
- Measurement ID: G-9LTV8JBT7C
- Pattern: shared js/analytics.js + gtag loader in <head>
- Files modified:
  - index.html
  - crawulator/index.html
  - Newman_Library/index.html

## [2026-07-14] UI overhaul phase 1 — "Lab chassis"
- New css/chassis.css: shared sticky nav (.nl-nav — wordmark, // tool crumb, status
  dot) and shared footer (.nl-footer) with the landing page's amber/mono identity.
- All four pages now include the chassis; per-page nav/footer CSS + markup removed:
  - index.html: fixed nav → chassis sticky nav; hero height now 100vh − nav.
  - vintool.html: custom nav/footer → chassis (kept "5 data sources live" status
    and the data-attribution line as .nl-note).
  - crawulator: back-bar → full chassis nav; chassis footer added below the
    "mud bugs" content footer. Page keeps its newspaper skin.
  - Newman_Library: first-ever site nav (page previously had no way back home);
    full-bleed negative margins compensate for the body clamp() padding.
- Design rule going forward: chassis owns nav/footer/identity; each tool page
  keeps its own body styling ("one shell, many skins").

## [2026-07-14] Full-repo audit + fixes
- KEY FINDING: VinTool 2.0 (854 lines) was never committed — HEAD:vintool.html was a
  17-line redirect stub, so the live /vintool bounced users back to the homepage
  while the landing page marked it "Live". Fixed by committing the real file.
- vintool.html: added GA4 (was the only page without it); added esc() HTML-escaping to
  all API-fed innerHTML (NHTSA complaint narratives are free-text consumer submissions
  — stored-XSS vector); NCAP/EPA now match the decoded trim/drive variant instead of
  blindly taking Results[0]; removed dead EPA fallback + unused constants; favicon.
- crawulator: fixed duplicate season-num/season-unit IDs (Liquid Seasoning card was
  frozen showing dry-seasoning values — now static "1 bottle"); cost-tab seasoning qty
  now scales with heat like the shopping list; tip strip no longer re-randomizes on
  every input; IBM Plex Mono actually loaded for the back bar.
- Newman_Library: fetch failure no longer leaves permanent loading shimmer
  (finally block); 30s polling only starts if reading-data.json exists; renderStats/
  renderInsights use null-safe setters (referenced ~10 deleted element IDs and would
  crash on data load); removed stray </div> from commented-out chart-grid; Inter font
  loaded; favicon. NOTE: reading-data.json still needs to be produced by the pipeline
  and committed — dashboard falls back to static content until then.
- index.html: charset first, analytics deferred, rel=noopener on _blank links,
  fonts.gstatic.com preconnect, favicon now references /favicon.svg (data-URI removed).
- Added .gitattributes (LF normalization) — every file showed as modified from CRLF
  churn, which is likely how the uncommitted vintool went unnoticed.
- Updated _SKILLS/SKILL.md tool table + structure (was stale: VinTool listed as
  FastAPI/SQLite coming-soon, Library path listed as /library).
- Known leftover: local `master` branch and remote `origin/Crawulator` branch are
  stale — deliberately not deleted without review.

## [2026-04-29 23:15] GA4 push + merge resolution
- Confirmed GA4 tracking present in all three pages after session recovery check
- Remote (origin/main) had 6 uncommitted updates not in local working tree:
  - Library of Kellie Newman promoted from "Coming soon" to Live
  - Crawulator description rewritten
  - Hero headline changed: "ship" → "get it done"
  - About blurb wording updated
  - Tool count bumped to "2 live"
  - Library renamed (Lib_Dashboard.html → index.html)
- Resolved merge conflicts by taking remote content as base, then re-stamping GA4 into <head> on all three files
- js/analytics.js content confirmed correct (gtag config only, no inline HTML)
- Pushed clean merge commit: 574f38d..2bfffc2 → origin/main
- Repo state: local main == origin/main, all GA4 tracking live
