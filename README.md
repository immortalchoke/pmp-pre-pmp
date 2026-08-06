# PMP — Pre-PMP Dashboard

Live demo: **https://immortalchoke.github.io/pmp-pre-pmp/**

> Design study by Billy Hong for Facebook for Business. Not an official Meta site, and not
> a shipped product. All account data shown is placeholder — "Tea Leaf Salad Company",
> "E-Bike Company", and invented ad account IDs.

Layout concepts for **PMP (Personalized Marketing Plan)**, a guided marketing-plan
experience for small businesses on Facebook. This repo covers the *pre-PMP* state — what a
business sees before their plan is built — plus two agency-facing variants.

Companion demo: [PMP Self-Serve onboarding](https://immortalchoke.github.io/pmp-self-serve/),
the questionnaire flow that feeds this dashboard.

## Pages

| Page | Path |
|---|---|
| Pre-PMP dashboard | [`index.html`](index.html) |
| Agency PMP | [`agency-pmp.html`](agency-pmp.html) |
| Agency PMP — updated content | [`agency-pmp-updated-content.html`](agency-pmp-updated-content.html) |

The dashboard covers a campaign checklist, notification tray, ad-account switcher,
Marketing Expert call scheduling, and an onboarding modal linking out to Blueprint
eLearning and the Ads Guide.

## Running locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. No build step — it is a static site.

## Notes on this build

Webflow export, with four changes needed to make it work outside Webflow's hosting:

- **Fonts substituted.** The export bundled Meta's proprietary Optimistic and
  FacebookReader plus two commercially licensed families, as raw `.otf`/`.ttf`. Those are
  removed and replaced with open equivalents — see [`fonts/NOTICE.md`](fonts/NOTICE.md).
  Typography is an approximation; layout is unchanged.
- **Two broken image references repaired.** The export asked for
  `White-Check_1White-Check.png` and `blue-check_1blue-check.png`, but wrote both files
  with a space instead of a hyphen — six references across two pages resolved to nothing.
- **Two remote SVGs localised** from Webflow's asset CDN into [`images/`](images/).
- **Cross-link repointed** from the old Webflow staging URL to the companion demo above.

### Known dead link

Thirteen "download the guide" links point at a Google Drive file that returns **401** — it
is an access-controlled internal asset. Those links are left intact rather than removed,
since they are part of the original design; they will prompt a Google sign-in for anyone
without access.

The original export is untouched at
`~/Dropbox/Design/Webflow/Work/FB - PMP/new-pmp-layout-v2-pre-pmp-feb1130bfff49.webflow`.

## Credits

Design by Billy Hong. Built in Webflow. Facebook, the Facebook wordmark, PMP and all
product branding belong to Meta Platforms, Inc.
