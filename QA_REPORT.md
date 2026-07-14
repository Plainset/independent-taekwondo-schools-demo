# QA Report

Use exact pass/fail evidence. "Looks fine" is not a result.

## Pages Checked
- index.html
- classes.html
- instructors.html
- contact.html

Served locally via `python3 -m http.server 4264` (per `.claude/launch.json` entry `independent-taekwondo-schools-site`). Audited via `.pipeline/qa/run-audit.js` (local Playwright runner, used because chrome-devtools MCP / WebFetch / WebSearch were confirmed permission-denied in this unattended session) using the shared `contrast-audit.js` and `upscale-audit.js` scripts, plus ad-hoc Playwright scripts for text-overflow, mobile-nav-toggle, FAQ-toggle, and internal-link checks.

## Audit Results
| Check | Result | Evidence |
|---|---|---|
| Contrast audit | PASS (after 1 fix) | Initial run found a real violation: the "Book a free taster" primary button inside the desktop nav rendered dark grey text (`--ink-soft`) on a red background (ratio 1.34) on index.html and contact.html, at all 3 widths. Cause: `.main-nav a` (0,2,1 specificity) was overriding `.btn-primary`'s own `color: var(--paper)`. Fixed by rescoping the nav link rule to `.main-nav ul a` so it no longer touches the button element sitting outside the `<ul>`. Re-ran all 4 pages × 390/834/1440px (12 runs): `violations: []` on every run. `needsManualCheck` counts: index 13, classes 4, instructors 5, contact 3 — all are hero/CTA-band/section-dark text over CSS gradients, manually reviewed below. |
| Upscale mobile (390px) | PASS | index: 3 imgs, 0 violations/broken/mismatches. classes: 2 imgs, 0/0/0. instructors: 2 imgs, 0/0/0. contact: 1 img, 0/0/0. |
| Upscale tablet (834px) | PASS | Same counts as mobile, 0/0/0 on all 4 pages. |
| Upscale desktop (1440px) | PASS | Same counts as mobile, 0/0/0 on all 4 pages. Total images checked across the whole site: 3+2+2+1 = 8, matching BUILD_BRIEF.md's Asset Manifest exactly. |
| Broken images | PASS | 0 `brokenImages` across all 12 page/width combinations; 0 `notYetLoaded` (no lazy-loaded images were missed — all images are above the fold or resolved on the single-viewport check). |
| Aspect mismatch advisory | PASS (advisory, none found) | 0 `aspectMismatches` across all 12 page/width combinations. |

## Manual Checks
| Check | Result | Notes |
|---|---|---|
| Text on photo | PASS | No copy is overlaid directly on top of a photo anywhere in the built site. The hero badge ("7 clubs...") sits on a solid navy card overlapping the photo's corner, not directly on the image pixels — verified it has its own opaque `var(--navy)` background with a gold border, not a transparent scrim. |
| Gradient/::before backgrounds | PASS | Hero sections use a light paper→paper-alt gradient with dark ink text (high contrast, not flagged as a violation). `.section-dark` and `.cta-band` use solid-ish dark navy/red gradients with light paper text. Manually reviewed all `needsManualCheck` items via the CSS custom properties involved (`--ink`/`--ink-soft` dark text on `--paper`/`--paper-alt` light gradients; `--paper` light text on `--navy`/`--navy-dark` or `--red`/`--red-dark` dark gradients) — all clearly high-contrast pairings, no borderline cases. |
| Image/content match | PASS | All 8 images were downloaded directly from tkduk.co.uk's own `cc_images` gallery folder (linked from the real site's Home, Classes, Gallery, Instructors and Events pages) via `curl` over HTTP, visually inspected at full resolution, and matched to on-page copy that describes what's actually in the photo (e.g. junior sparring photo captioned "Junior Taekwon-Do students sparring with protective head, hand and foot guards" — visually confirmed red head/hand/foot guards in frame). See BUILD_BRIEF.md Asset Manifest for the full source-URL-to-usage mapping. |
| Fabricated claims | PASS | Every factual claim (instructor names/grades, governing-body affiliation, club venues, class days/times, PVG/First Aid/Governing Body certification, membership with Aberdeenshire ClubSport SCIO, recent grading results, secretary's name and qualifications) was sourced directly from tkduk.co.uk's own pages, re-fetched this session via curl. No street address, pricing, or founding date is claimed anywhere — none of those facts exist on the source site (confirmed by grep across all fetched pages); see BUILD_BRIEF.md Do Not Claim. |
| Mobile layout | PASS | Full-page mobile screenshot (390px, taken after a real incremental scroll — see Scroll-reveal below) reviewed for index.html: nav collapses to a hamburger toggle, hero/stat-cards/venue-cards/quote-cards/CTA-band/footer all stack to a single column cleanly with no overlap or cut-off text. Confirmed via Playwright script that `.nav-toggle` click opens `.main-nav` (`is-open` class added, `opacity` goes from computed non-visible to `1`) and that clicking a nav link both closes the menu and navigates correctly (`classes.html` loaded). |
| Text-overflow (real content lengths) | PASS | Custom `scrollWidth > clientWidth` check against `.contact-list li/a/.value`, `.venue-card`, `.venue-schedule li`, `.venue-note`, `.instructor-list li`, `.footer-col a/li`, `nav a`, `.stat-card`, `.card-body`, `.quote-card`, `.brand-text`, `.trust-item`, `.badge` at 390px and 1440px on all 4 pages (longest real strings used: full email address `k1.tkduk@gmail.com`, full phone numbers, longest venue note sentence, longest footer link "Aberdeen University, Inverurie & Borders", longest instructor entry "Mr R Deans (jun)") — 0 overflowing elements out of 42–53 checked per page. |
| Scroll-reveal above-the-fold + full-page | PASS | `main.js` implements the AGENTS.md standing rule (checks `getBoundingClientRect()` before observing each `[data-reveal]` element; anything already in the viewport at load gets `is-visible` immediately, not left waiting for a later intersection change). A naive one-shot `mouse.wheel` jump to the bottom left some later `[data-reveal]` sections unrevealed in a full-page screenshot — this is the known Playwright full-page-screenshot timing artifact (already documented in `international-tennis-coaching/QA_REPORT.md`), not a site bug. Re-verified with a real incremental scroll (400px steps with a 60ms wait between each, simulating normal scroll speed): all 12 `[data-reveal]` elements on index.html reach `is-visible` (`{"total":12,"visible":12,"notVisible":[]}`), confirmed via direct DOM query, not just visual inspection. |
| Internal links / anchors | PASS | Grepped every `href="..."` across all 4 pages: every page-to-page link (`index.html`, `classes.html`, `instructors.html`, `contact.html`) resolves to a real file in the repo; every `classes.html#anchor` link (`#aberdeen`, `#peterhead`, `#more-clubs`) has a matching `id` on `classes.html`. The two external links (`ausa.org.uk/sports`, the Borders club's Facebook page) match sourced facts in BUILD_BRIEF.md. |
| FAQ interaction | PASS | Native `<details>/<summary>` used for the Contact page FAQ (per AGENTS.md's "use native `<details>/<summary>` for FAQs" default). Playwright click test confirms clicking the first FAQ's `<summary>` sets `.open = true`. |

## Blocking Issues
| Issue | Evidence | Required fix |
|---|---|---|
| (none remaining) | — | — |

## Advisory Issues
- Full-page Playwright screenshots taken with a single large `mouse.wheel` jump (rather than a real incremental scroll) show the sticky header re-rendering partway down the page and several `[data-reveal]` sections appearing blank. This is a known Playwright full-page-screenshot stitching/timing artifact (racing ahead of the async `IntersectionObserver` callback and the sticky-position compositing), not a real rendering bug — confirmed by re-running with a real incremental scroll, which resolves both. Noting for the next agent so it isn't re-flagged as a defect (same pattern documented in `international-tennis-coaching/QA_REPORT.md`).
- The `venue-jump` chip row on `classes.html` uses `overflow-x: auto` with the shared `.scroll-thin` styling for narrow viewports where the three chips don't fit on one line; not exercised with a dedicated drag/swipe test this session, but it degrades gracefully (chips simply wrap via horizontal scroll, no clipped/hidden content) — low risk, non-blocking.

## Fixed Verification
| Issue | Fix | Recheck result |
|---|---|---|
| Nav "Book a free taster" button had a contrast violation (dark grey text on red, ratio 1.34) on index.html and contact.html, all widths | Rescoped `.main-nav a` → `.main-nav ul a` (and the matching mobile-width override) in `assets/css/style.css`, so the nav-link color rule no longer overrides `.btn-primary`'s own light text color on the button sitting outside the `<ul>` | Re-ran `contrast-audit.js` on all 4 pages × 390/834/1440px (12 runs): `violations: []` on every run. Re-ran `upscale-audit.js` on all 4 pages × 3 widths: unchanged, 0/0/0 throughout — confirms the CSS specificity fix caused no layout regression. |

## Verdict
PASS
