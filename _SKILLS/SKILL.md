# Newman Labs Infrastructure — SKILL.md

**Last updated:** 2026-03-24 (end of session)
**Status:** LIVE at https://newmanlabs.dev ✅

---

## What exists — FULLY DEPLOYED ✅

### Domain
- **`newmanlabs.dev`** — registered Namecheap, 2026-03-24
- Order: 197947519 | 2 years | Privacy: ON | Parking: OFF
- Email verified ✅ | Cost: $29.36

### DNS
- Nameservers: `grant.ns.cloudflare.com` + `vita.ns.cloudflare.com`
- Cloudflare account: `Sjn013@gmail.com` | Free plan
- CNAME record: `@` → `agentNewman.github.io` | DNS only (gray cloud)
- AI crawlers: Allow (public tools = want indexed)

### GitHub
- Repo: `https://github.com/AgentNewman/newmanlabs`
- GitHub Pages: `main` branch, `/root`, custom domain `newmanlabs.dev`
- HTTPS enforced ✅

### Local workspace
- Path: `C:\Users\Sjn01\ON_DEVICE_WORKBENCH\NewmanLabs\`
- Git remote: `https://github.com/AgentNewman/newmanlabs.git`
- Branch: `main`

---

## Git workflow (going forward)

```powershell
cd C:\Users\Sjn01\ON_DEVICE_WORKBENCH\NewmanLabs
git add .
git commit -m "describe what changed"
git push origin main
```

GitHub Pages redeploys automatically within ~60 seconds of push.

### Known git issue — 55 pending changes in VS Code
VS Code opens ON_DEVICE_WORKBENCH (parent repo) and sees all projects.
Fix: Add `NewmanLabs/` to `ON_DEVICE_WORKBENCH\.gitignore` so the parent
repo ignores it entirely. NewmanLabs has its own git repo — they shouldn't overlap.

Add this to `C:\Users\Sjn01\ON_DEVICE_WORKBENCH\.gitignore`:
```
# Newman Labs has its own repo
NewmanLabs/
```

Then open VS Code scoped to `NewmanLabs\` only (File → Open Folder → NewmanLabs)
and the Source Control panel will only show NewmanLabs files.

---

## Site structure (live)

```
newmanlabs.dev/               ← Newman Labs landing page ✅
newmanlabs.dev/crawulator/    ← Crawfish Boil Calculator ✅
```

### Repo file structure
```
NewmanLabs/
  index.html          ← Landing page (dark industrial, IBM Plex Mono, amber)
  favicon.svg         ← NL monogram, black + amber border
  crawulator/
    index.html        ← Crawfish Boil Calculator (3-tab: calc/cost/timeline)
  _SKILLS/
    SKILL.md          ← This file
```

---

## Landing page design decisions
- Font: IBM Plex Mono (headings/labels) + IBM Plex Sans (body)
- Colors: #080A0C black bg, #F0A500 amber accent, #F0EDE8 white text
- Features: scanline overlay, grid texture, staggered fadeUp animations
- Sections: hero → stat bar (8+ apps, 3 yrs, 0 degrees, ∞ problems) → about → tools grid → footer
- Hero label: `// Albany, Louisiana — Est. 2023`
- Footer: `© 2026 Newman Labs — newmanlabs.dev` | `Albany, Louisiana`

---

## Tool cards on landing page

| Tool | Status | Path | Stack |
|---|---|---|---|
| Crawulator | ✅ Live | `/crawulator` | HTML, Vanilla JS |
| VinTool | Coming soon | `/vintool` | FastAPI, SQLite, Python |
| DeepDrive | Coming soon | `/deepdrive` | Electron, Node.js |
| Library | Coming soon | `/library` | Dashboard, CSV pipeline |

---

## Stack — locked in

| Layer | Choice | Cost |
|---|---|---|
| Domain | Namecheap — `newmanlabs.dev` | $29.36/2yr |
| DNS/CDN | Cloudflare free | $0 |
| Hosting | GitHub Pages | $0 |
| SSL | Auto (GitHub Pages + .dev enforced) | $0 |
| **Total** | | **~$15/yr** |

---

## Accounts
- GitHub: `AgentNewman`
- Namecheap: `Newman424` / `Sjn013@gmail.com`
- Cloudflare: `Sjn013@gmail.com`
- Local workbench: `C:\Users\Sjn01\ON_DEVICE_WORKBENCH\`
