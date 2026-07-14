# Build Brief

Keep this compact. Add only sourced facts and assets actually used or deliberately rejected.

## Contact
- Email: k1.tkduk@gmail.com
- Email source URL: http://www.tkduk.co.uk/contact-us/ (also appears identically on http://www.tkduk.co.uk/ home, /classes/, /holiday-venue-changes/, /instructors/, /gallery/ — re-verified live via curl 2026-07-14)
- Rechecked date: 2026-07-14 (this session, via `curl -A "Mozilla/5.0" http://www.tkduk.co.uk/contact-us/`)
- Phone: 07526 081316 or 01779 821866 — both explicitly noted on site as "unmanned phone — please leave a message"
- Address: No street address published anywhere on the site. The association operates across multiple hired venues (school halls / community centres) in Aberdeenshire rather than one fixed premises — see Page Plan / locations below. Do not fabricate a street address.

## Business State Check
- Status: still operating, multi-venue, no fixed single address (this is normal/expected for a hall-hire martial arts club, not a red flag)
- Checked sources: http://www.tkduk.co.uk/ (home page has a "March 2026 Training Course and Grading Test" news item — most recent post is contemporaneous with today's date, 2026-07-14), http://www.tkduk.co.uk/events-seminar-gradings/ (2026 Calendar of Events PDF present, ongoing monthly grading write-ups through 2024–2026), http://www.tkduk.co.uk/classes/ (current 2026 class schedule), home page banner text: "The club has updated its membership with Aberdeenshire ClubSport SCIO for 2024/25" and "NEW STUDENT INTAKE — Our clubs are taking on new students at this time."
- Notes: Site content is current and active — most recent grading news item is from March 2026, four months before this build (2026-07-14). No closure, relocation, or "online only" signal anywhere. Matches LEADS.md note that "site content confirms ongoing/current operation."
- Build decision: proceed

## Page Plan
- Scope: extra page approved (4 pages instead of the 3-page default)
- Pages: index.html (Home), classes.html (Classes & Locations), instructors.html (Instructors), contact.html (Contact / Booking)
- Reason for any extra page: This is a genuine multi-venue association (7 listed club venues across Aberdeenshire and one linked Borders club), not a single studio. AGENTS.md's standing rule requires covering every location honestly for a genuinely multi-location business rather than silently narrowing scope. A dedicated Classes & Locations page lets each venue, day, and time be listed accurately without cramming it into the homepage or forcing readers to guess which club is "the" club. Also split out Instructors as its own page because the source site has a long, credentialed instructor roster (8th Dan down to junior 1st Dan) that is a real trust signal and deserves full visibility rather than a cut-down teaser.

## Pitch Hook
- Verified observation: The business's own domain (tkduk.co.uk) fails to load over HTTPS on both bare and www domains — TLS handshake "internal error" alert (reproduced this session via `curl -v https://www.tkduk.co.uk/` and `curl -v https://tkduk.co.uk/`, both fail at TLS handshake). Only the plain HTTP version loads, so any visitor whose browser tries HTTPS first (the default in every modern browser) or who is on a network that enforces HTTPS gets a hard security warning before they ever see the club's content — for a martial arts club whose entire growth channel is a "free taster class" email/phone enquiry, that is a real lost-enquiry risk, not a cosmetic issue.
- Source URL: https://www.tkduk.co.uk/ and https://tkduk.co.uk/ (both fail); http://www.tkduk.co.uk/ (loads)

## Allowed Facts
| Fact | Source URL | Used where |
|---|---|---|
| Business name "Independent Taekwondo Schools" (site also uses "Independent Taekwon-Do Schools") | http://www.tkduk.co.uk/ (title tag), /contact-us/ (page heading "Independent Taekwon-Do Schools Secretary") | All pages |
| Meta description: "association teaching the martial art Taekwon-Do in Aberdeenshire" | http://www.tkduk.co.uk/ (meta description tag) | Home, meta tags |
| Email k1.tkduk@gmail.com | /contact-us/, /classes/, /holiday-venue-changes/ | All pages (footer, contact) |
| Phone 07526 081316 / 01779 821866, "unmanned phone – please leave a message" | /contact-us/, /classes/ | Contact page |
| Secretary: Mrs J Murdoch, M.A., Dip. Lib., A.L.A. | /instructors/, /contact-us/ | Instructors, Contact |
| Head instructor: Senior Master Murdoch, 8th Dan Black Belt | /instructors/ | Home, Instructors |
| International Instructors: Mr J Aitchison 5th Dan, Miss E Thoms 5th Dan, Mr R Deans 4th Dan, Mr M Watt 4th Dan | /instructors/ | Instructors |
| Assistant Instructors: Mr M Murdoch 3rd Dan, Miss I Krammer 3rd Dan, Mr C Grieve 3rd Dan, Miss C Welch 3rd Dan, Mrs J Murdoch 2nd Dan, Miss M Murray 2nd Dan, Mr A Stewart 2nd Dan, Mr A-B Murphy 1st Dan | /instructors/ | Instructors |
| Junior Black Belt Assistant Instructors: Miss A Lawal 1st Dan, Mr R Deans (jun) 1st Dan, Mr Z Sarbantovica 1st Dan, Mr P Olejniczak 1st Dan | /instructors/ | Instructors |
| Affiliated to UKGT, which is affiliated to World Body International Taekwon-do Federation (ITF) | /instructors/ | Instructors, Home trust strip |
| Members of Aberdeen Sports Council and Aberdeenshire Sports Council | /instructors/ | Instructors |
| Instructors PVG checked, First Aid qualified, Governing Body certified | /instructors/ | Instructors, Home trust strip |
| Club membership updated with Aberdeenshire ClubSport SCIO for 2024/25 | http://www.tkduk.co.uk/ (home news banner) | Home |
| Club venues (7 listed): Aberdeen Central, Bridge of Don, Aberdeen, Peterhead, Aberdeen University, Inverurie, Borders (by Edinburgh) | /contact-us/ (footer "Club venues" list, identical on every page) | Home, Classes & Locations |
| Aberdeen class: Monday evenings, Seaton Primary School, Aberdeen, 7–8pm | /classes/ | Classes & Locations |
| Bridge of Don class: Wednesday evenings, Oldmachar Academy, Bridge of Don, 7–8pm, mixed class | /classes/ | Classes & Locations |
| Bridge of Don class: Friday evenings, Braehead Primary School, Bridge of Don, 7–8pm, mixed class | /classes/ | Classes & Locations |
| Saturday mornings: Gradings / Seminars / Black Belt and Instructors' Training | /classes/ | Classes & Locations |
| Peterhead class: Tuesday & Thursday evenings, Peterhead Community Centre, 7–8pm, mixed class | /classes/ | Classes & Locations |
| Aberdeen University club — separate student-run sports club; check https://www.ausa.org.uk/sports/ for current details | /classes/ | Classes & Locations |
| Borders (by Edinburgh) — separate/affiliated club "Taekwon-do Borders", own Facebook page https://www.facebook.com/profile.php?id=61573146817849 | /classes/ | Classes & Locations |
| New starters: free taster class, book by email/phone or Facebook message ("INDEPENDENT TAEKWON-DO SCHOOLS") | http://www.tkduk.co.uk/ (home news banner) | Home, Contact |
| New starters told to "wear something loose and comfy to train in" | http://www.tkduk.co.uk/ (home news banner) | Contact FAQ |
| 2026 Calendar of Events available as a downloadable PDF ("CALENDAR OF EVENTS 2026.pdf") | /events-seminar-gradings/ | Home (mentioned as a fact only, PDF itself not carried over — see Do Not Claim) |
| Regular monthly training seminars and grading tests, colour-belt and black-belt gradings, with Grading Trophy/Grading Shield awards for top students | /events-seminar-gradings/, home page news items | Home, Instructors |

## Do Not Claim
| Claim or uncertainty | Reason |
|---|---|
| Any specific street address / postcode for any venue | Never published on the source site — only venue names (e.g. "Seaton Primary School, Aberdeen"; "Peterhead Community Centre"). Fabricating a postcode would fail the no-fabrication rule. |
| Pricing / membership fees | No pricing figure appears anywhere on the source site. Not shown on the demo; "free taster class" is the only cost-related fact that is actually stated. |
| A founding/established year for the association | Not stated anywhere on the source site (checked all fetched pages for "since", "founded", "established" — no match). Not claimed on the demo. |
| Specific schedule (day/time) for Aberdeen Central, Aberdeen University, Inverurie, or Borders clubs | The source site lists these as venues but only gives day/time detail for Aberdeen (Seaton Primary), Bridge of Don (x2), and Peterhead. For the other three, the demo says "contact the club" / links to the venue's own listed source (AUSA sports page, Borders Facebook page) rather than inventing a schedule. |
| Linking directly to the live CALENDAR OF EVENTS 2026.pdf or reproducing its contents | The PDF itself was not fetched/reviewed this session; only its existence and title are referenced as a fact, not its contents. |
| Live embedded downloadable PDF or shop functionality | Source site has a "Shop" nav item; not reviewed this session and not load-bearing to the pitch, so it is omitted from the demo entirely rather than guessed at. |

## Asset Manifest
| File | Source URL | Native size | License/credit | Watermark checked | Intended section | Copy match |
|---|---|---|---|---|---|---|
| hero-beach-kick.jpg | http://www.tkduk.co.uk/s/cc_images/cache_66078840.jpg (home page gallery) | 1024×768 | Business's own site gallery photo | yes/no — no watermark found | Home hero | Dramatic outdoor turning/axe kick on a beach at dusk by a club member in dobok — used as an aspirational hero image, not tied to a specific claim |
| hall-pattern-practice.jpg | http://www.tkduk.co.uk/s/cc_images/cache_68216806.jpg (gallery) | 1024×391 | Business's own site gallery photo | yes/no — no watermark found | Home "About the association" section | Wide shot of instructors and students performing a pattern in a training hall — matches "regular training, all grades" copy |
| junior-sparring-headgear.jpg | http://www.tkduk.co.uk/s/cc_images/teaserbox_63622351.JPG (events/seminar page) | 900×475 | Business's own site gallery photo | yes/no — no watermark found | Home classes teaser card | Junior students sparring with red head/hand/foot guards — matches "classes for children and adults" copy |
| training-hall-group.jpg | http://www.tkduk.co.uk/s/cc_images/cache_68216804.jpg (gallery) | 1024×639 | Business's own site gallery photo | yes/no — no watermark found | Classes & Locations page hero | Wide shot of a full class of adults and children training together — matches "mixed classes, all ages and grades" copy |
| sparring-pair.jpg | http://www.tkduk.co.uk/s/cc_images/teaserbox_67173788.JPG (events/seminar page) | 885×1080 | Business's own site gallery photo | yes/no — no watermark found | Classes & Locations page secondary image | Two students (green belt and red belt) sparring — matches "structured belt-grade sparring practice" copy |
| blackbelt-team-photo.jpg | http://www.tkduk.co.uk/s/cc_images/teaserbox_45872908.jpg (events/seminar page) | 900×495 | Business's own site gallery photo | yes/no — no watermark found | Instructors page hero | Line-up of black-belt instructors and senior grade students with Senior Master Murdoch (in blazer) — matches "instructor team" copy |
| grading-trophy-winners.jpg | http://www.tkduk.co.uk/s/cc_images/teaserbox_69107406.jpg (home page news) | 733×801 | Business's own site gallery photo | yes/no — no watermark found | Instructors page achievements panel | Two students holding grading trophy/shield awards with an instructor | matches "grading trophy and shield" copy |
| group-welcome-photo.jpg | http://www.tkduk.co.uk/s/cc_images/teaserbox_69443282.jpg (home page news) | 900×397 | Business's own site gallery photo | yes/no — no watermark found | Contact page | Mixed group of instructors, teens and children posed together in a hall — matches "friendly, family classes, new starters welcome" copy |

All eight images were downloaded directly from tkduk.co.uk's own `cc_images` gallery folder (linked from the site's own Home, Classes, Gallery, Instructors and Events pages) via `curl` over HTTP (the only protocol that loads on this domain — see Business State Check / Pitch Hook). Each was visually inspected at full resolution for third-party photographer watermarks, stock-photo marks, or review-site logos before use — none found on any of the eight.

## Design Notes
- Palette: ITF/dobok-inspired — deep navy ink (`#101a30`), a warm off-white "dobok" paper background, a strong red accent (taken from the red belt/red sparring-gear seen repeatedly in the club's own photos) and a gold/amber accent for Dan-grade/achievement callouts (black-belt embroidery gold). Distinct from every other build in this pipeline (no other business uses this navy/red/gold combination).
- Image layout pattern: wrapper with `aspect-ratio` + `object-fit: cover` for hero/card images (pattern 2 from AGENTS.md), so native photo crops stay controlled across breakpoints without blanket `height:auto`.
- Risk notes: No fixed street address exists to put in a map/footer — footer and contact page instead list venues by name/area, matching what the real site does. Multi-location scope is handled with an explicit Classes & Locations page rather than picking one club and silently dropping the others.

## Builder QA
- Contrast: PASS after 1 fix (nav "Book a free taster" button had a specificity bug causing dark-on-red text; fixed by rescoping `.main-nav a` to `.main-nav ul a`). 0 violations on all 4 pages × 3 widths after fix. See QA_REPORT.md.
- Upscale mobile: PASS — 0 violations/broken/mismatches, all 4 pages. See QA_REPORT.md.
- Upscale tablet: PASS — 0 violations/broken/mismatches, all 4 pages. See QA_REPORT.md.
- Upscale desktop: PASS — 0 violations/broken/mismatches, all 4 pages. See QA_REPORT.md.
- Broken images: PASS — 0 across all 12 page/width combinations. See QA_REPORT.md.
- Manual checks: PASS — text-overflow (0/42-53 elements per page overflowing), mobile nav toggle, FAQ details/summary toggle, internal link/anchor integrity, scroll-reveal (12/12 elements reach is-visible on a real scroll), image/copy match. Full detail in QA_REPORT.md.
