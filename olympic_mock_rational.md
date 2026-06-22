# Olympic Mock Homepage — Design Rationale

**Artifact:** `olympic_mock_home.html`  
**Informed by:** `olympic_recommendations.md`, `comparison_report.md`  
**Purpose:** Document why each major design decision was made, and how it maps to research findings and club recommendations.

This is a **mockup**, not a production deployment. Rationale includes both user-experience intent and practical constraints for a volunteer-run club website.

---

## 1. Overall strategy

### Problem the mock addresses

`olympic_recommendations.md` identifies that Olympic Harriers’ primary online failure is **signposting**, not offering: recreational membership ($82), pack runs for all paces, and a try-before-you-join policy already exist, but a nervous newcomer landing on the live homepage sees news, results, and race calendars first.

The mock implements recommendation **L1** (homepage information architecture reorder) in visual form, prioritising:

1. *Can I join this club?*
2. *When and where do I show up?*
3. *Who do I talk to?*
4. *What does it cost if I stay?*

…before serving existing members with news, results, and calendar tables.

### Persona driving decisions

Every layout and copy choice is weighted toward the **social beginner** defined in the comparison analysis: new to running (slow 5 km), Wellington-based, anxious about turning up alone. The mock deliberately **does not** optimise for competitive members or race administrators — that audience is still served, but lower on the page under **“For members”**.

### Relationship to the live site

The mock **retains** the live site’s three-column news / results / calendar pattern rather than inventing a new content model. That reduces implementation risk for volunteers: the reorder is structural and copy-led, not a full CMS rethink. Tables use the same row format and real entries from [olympicharriers.nz](https://www.olympicharriers.nz/) (June 2026) so stakeholders can compare like-for-like.

---

## 2. Information architecture

| Decision | Rationale |
| --- | --- |
| **Hero + priority cards above the fold** | Implements Q1 (homepage “New to Olympic?” banner) and Q2 (pinned next Club Run/Walk). Research shows newcomers need answers within ~30 seconds; the live homepage fails this test. |
| **Three priority cards in one row** | Maps to the three unanswered questions from the executive summary: *when/where* (next run), *how to try* (trial policy), *what it costs* ($82 recreational). One card per question reduces cognitive load. |
| **Featured card (wider column) for next run** | Q2 is the highest-anxiety item — wrong day or venue is the main reason a beginner would not return. Visual prominence (1.2fr grid column + red top border) signals “start here.” |
| **“For members” section label** | Explicitly reframes news/results/calendar as secondary content. Matches recommendation to deprioritise without deleting material members rely on. |
| **FAQ before member tables** | Recommendation M1 includes FAQ (*“I’m slow and nervous — will I fit in?”*). Placing it above member tables catches prospects who scroll past the hero but bounce before reaching the footer. |
| **Facts bar between cards and FAQ** | Scannable **When / Where / Who / Bring** answers the New Members page outline (§5) in a format readable on mobile without opening accordions. |
| **Sticky header with “New members” first in nav** | Recommendation Q1 links to joining content; putting **New members** first (and highlighted) mirrors Wellington Scottish’s front-page membership visibility and HVH’s homepage welcome copy. |
| **In-page anchor `#next-run`** | Secondary hero button jumps to the next-run card — supports users who want logistics immediately without reading marketing copy. |

---

## 3. Content decisions

| Element | Source | Why it appears |
| --- | --- | --- |
| **Headline:** *“New to running? New to Olympic?”* | Sample content §1, `olympic_recommendations.md` | Directly addresses the persona; mirrors Scottish’s *“beginners to elite”* openness in a question form that invites self-identification. |
| **“No signup, no singlet, no pressure”** | Joining page policy + recommendation strengths | Removes perceived barriers (cost, kit, commitment) before the user reads membership fees. |
| **$82/year in hero** | Subscriptions page (Mar 2026); Q5 | Scottish puts non-racing price on homepage; Olympic’s recreational tier is a competitive advantage ($115 Scottish, $90 Trentham) and should not be buried. |
| **Saturday 27 June 2026, 1:30 pm** | Club calendar (Jun 2026); Q2 | Real Club Run/Walk date from analysis — demonstrates weekly update workflow rather than static placeholder. |
| **Rob McCrudden & Graeme Moss** | Contact page; Q3 | Names a human contact; reduces fear of walking into an anonymous crowd. Benchmark: HVH *“contact the club captain.”* |
| **Suggested script:** *“Hi, I’m new — which pack suits a slow 5 km jog?”* | New Members page outline §7 | Gives socially anxious users literal words to use — low effort, high reassurance. |
| **Race-week disclaimer on next-run card** | Q2, M4 | Honest about harrier season complexity; builds trust vs overpromising “every Saturday at clubrooms.” |
| **Pills:** walkers, try before join, pack runs, families | About page + strengths to preserve | Surfaces pack-run model and inclusivity without a long paragraph; supports skimming. |
| **FAQ copy** | Sample content §3 | Verbatim from recommendations — ready for club approval. |
| **Club Run/Walk bold in calendar table** | Q2 | Links member-facing calendar back to newcomer entry point; consistent messaging at bottom of page. |

---

## 4. Visual identity — black and red

### Colour palette

| Token | Value | Rationale |
| --- | --- | --- |
| `--black` | `#0d0d0d` | User brief: Olympic colour scheme of **black and red**. Near-black avoids harsh pure `#000` on large areas while reading as club black on screens. |
| `--red` | `#c8102e` | Classic athletic red — strong contrast on black and white, accessible for links and CTAs. Chosen as a generic “club red” common in NZ athletics kit; **not** sampled from live site CSS (live site styling was not extracted). Production should match official singlet/brand assets if available. |
| `--red-dark` | `#9e0c24` | Hover state for buttons — affordance without changing hue family. |
| `--red-light` | `#fce8ec` | Mock banner background only — distinguishes prototype from live site without clashing with club colours. |
| Greys | `#f5f5f5` … `#555` | Neutral UI chrome; keeps **black + red for brand**, grey for secondary text and borders. Avoids introducing a third brand colour. |

### Where black and red are applied

- **Black:** header, hero background, facts bar, footer, member table headers — anchors the page in club identity and frames white content cards.
- **Red:** logo mark, eyebrow label, primary buttons, card accent borders, section heading underlines, fact labels, FAQ left border, links — draws the eye to **actions and newcomer paths**.
- **White cards on grey page background:** separates “information you need to act on” from “site chrome”; common pattern for community org sites with limited design resource.

### Hero gradient (`#2d0a10` tint)

Subtle red shift in the black gradient plus a radial red glow (`::before`) adds depth without photography — appropriate for a mock that may not have licensed images. **Production note:** real photos of mixed-pace pack runs (recommendation M5) would strengthen social proof; gradient is a placeholder strategy.

### Logo mark (red circle, “O”)

No official vector logo was available in the repo. A simple monogram:

- Reads at small sizes (mobile header).
- Uses club colours immediately.
- Avoids implying a final brand mark — easily replaced with official artwork.

**“Johnsonville · Wellington”** under the wordmark supports local discovery (persona is Wellington-based; club serves northern suburbs).

---

## 5. Typography and readability

| Decision | Rationale |
| --- | --- |
| **System font stack** (`Segoe UI`, `system-ui`) | Volunteer-maintained site unlikely to host custom webfonts. System fonts load instantly, render well on Windows (user environment) and mobile. |
| **Base size 1rem, line-height 1.6** | Comfortable for longer FAQ prose; WCAG-friendly body text without shrinking to fit tables. |
| **Hero `clamp(1.75rem, 4vw, 2.5rem)`** | Responsive headline without breakpoint-specific font rules — one less thing for maintainers to tune. |
| **Uppercase eyebrow / card labels** | Small caps-style labels create hierarchy without extra font weights; red labels tie sections to brand colour. |
| **Large price (`2rem`, weight 800`)** | Implements Q5 visually — recreational fee readable at a glance, matching Scottish’s homepage price prominence. |
| **Grey body text on white cards (`--grey-600`)** | Softens secondary copy; keeps headings and prices in `--black` for contrast hierarchy. |

---

## 6. Component-level UX

### Header (sticky)

- **Sticky positioning:** Newcomers who scroll to FAQ or member tables can return to **New members** without scrolling to top — useful on long mobile pages.
- **“New members” as filled red button:** Only nav item with filled treatment — unmissable primary audience entry (Q1).
- **Other links unchanged in label:** About, Membership, Calendar, Contact align with live site nav expectations — lowers migration friction for existing users.

### Hero

- **Two CTAs:** Primary → joining path; secondary → next run card. Dual intent: “learn more” vs “I’m ready to show up.” Recommendation sample content specified both buttons.
- **Pills not buttons:** Non-clickable tags communicate inclusivity without four competing actions — reduces choice paralysis.
- **Dark hero, light page:** Maximum contrast for first impression; signals “this section is different from the rest of the site” (newcomer zone).

### Priority cards (overlap layout)

- **Negative margin (`margin-top: -2rem`)** pulls cards into the hero — visually connects welcome message to actionable details; common landing-page pattern.
- **Red top border on featured card only:** Signals primary action without red overload on all three cards.
- **Full-width buttons inside cards:** Large touch targets for mobile users checking details en route to the clubrooms.
- **Emoji meta icons (⏱ 📍 👋):** Lightweight icon substitute without icon font dependency; `aria-hidden="true"` because text carries meaning (accessibility).

### Facts bar

- **Four columns, red labels:** Answers “what do I need to know before I travel?” in one horizontal scan — especially **Bring: layers, grippy shoes** from About page hill/w weather guidance.
- **Black background:** Visual break between white card block and FAQ; repeats brand colours in mid-page rhythm.

### FAQ

- **Single question shown** (not accordion of many): Mock focuses on the highest-anxiety question from recommendations; production could expand.
- **Red left border:** Associates FAQ with “help / reassurance” same as featured card accent.

### Member tables

- **Lighter shadow than priority cards** (`0 2px 12px` vs `0 4px 24px`): Subordinate visual weight — implements deprioritisation.
- **`black-muted` headers not red:** Avoids competing with newcomer CTAs; tables are utility, not conversion.
- **Smaller type (`0.8125rem`)** | Dense tables acceptable for returning members who scan dates habitually.

### Footer

- **Clubrooms address prominent** | Live site only had address in footer; mock elevates practical need for first visit (L3 map recommendation partially addressed via text).
- **Social + iCal links** | Preserves strengths from recommendations (newsletter, Facebook, calendar feed) for post-visit retention.

### Mock banner

- **Red-light bar at top** | Clearly labels file as prototype — prevents confusion if shared with committee; would be removed in production.

---

## 7. Accessibility

| Feature | Intent |
| --- | --- |
| `lang="en-NZ"` | Correct locale for Wellington club. |
| `aria-labelledby` on sections | Screen readers can navigate by landmark + heading. |
| `aria-label` on nav and priority section | Clarifies purpose where visual layout implies context. |
| Semantic HTML (`header`, `nav`, `section`, `article`, `footer`) | Baseline structure for assistive tech without ARIA overuse. |
| Sufficient contrast (white on black, white on red buttons) | Red `#c8102e` on white for links meets common contrast needs for body-weight text; production should verify all states with a checker. |
| Focus not styled in mock | **Gap:** production CSS should add visible `:focus-visible` outlines on links and buttons. |

---

## 8. Responsive behaviour

| Breakpoint | Behaviour | Rationale |
| --- | --- | --- |
| **≤900px** | Priority grid → single column; tables stack; facts 2×2; nav wraps | Prospects often look up run details on phone **while travelling** to Johnsonville (comparison report: mobile usability criterion). |
| **≤480px** | Full-width stacked buttons; facts single column | Thumb-friendly CTAs; avoids horizontal scroll on narrow devices. |
| **No hamburger menu** | Nav wraps to second row | Volunteer sites often omit JS menu toggles; wrapped links stay visible without interaction — acceptable for ~5 items. |

---

## 9. Mapping to specific recommendations

| Rec ID | Mock implementation |
| --- | --- |
| **Q1** | Hero + “New members” nav + primary CTA |
| **Q2** | Featured next-run card; calendar row link; secondary hero button |
| **Q3** | Captain and deputy named on next-run card |
| **Q5** | $82 in hero + dedicated recreational card with large price |
| **M1** | FAQ + facts bar + three-card block ≈ condensed New Members page |
| **M4** | Race-week italic note on next-run card |
| **L1** | Full homepage reorder: newcomer block → FAQ → For members |
| **L3** | Address in footer (map not embedded — out of scope for static mock) |

**Not implemented in mock** (documented gaps):

- **M2** — Activities page redirect (content/navigation change, not homepage layout).
- **M3** — Tuesday training time/place (awaiting coach confirmation per recommendations).
- **M5 / L2** — Social posts and greeter rota (operational, not HTML).
- **Q4** — Contact page season header (different page).

---

## 10. Deliberate trade-offs

### Single HTML file, embedded CSS

**Why:** Easy to open locally, email to committee, or hand to a webmaster as a reference implementation. No build step, no dependencies — aligned with volunteer capacity noted in `recommendation_prompt.md`.

**Cost:** No shared stylesheet with rest of live site; production would extract tokens and components.

### No photography

**Why:** Avoids stock-image inauthenticity and licensing issues in a mock.

**Cost:** Less emotional warmth than Scottish-style café/group photos (comparison report social signal). Recommendations M5 suggest real member photos when available.

### Placeholder `href="#"` links

**Why:** Mock is structural, not wired to CMS routes.

**Production:** Map to `/membership/joining/`, `/membership/subscriptions/`, `/contact/`, `/listcalendar/`, etc.

### Emoji icons

**Why:** Zero-dependency visual scanning aids.

**Cost:** Less polished than an icon set; some users dislike emoji in institutional contexts. Replace if club prefers SVG icons.

### English-only

**Why:** All source material and club communications reviewed were English.

**Note:** Te reo Māori welcome could be added if club wishes to reflect local identity — not present in source recommendations.

---

## 11. Success criteria (how to judge if the design works)

Aligned with `olympic_recommendations.md` §How to measure success:

1. **Time-to-answer test:** Show the mock to someone matching the persona; they should state date, time, place, and contact name within 30 seconds without scrolling past the priority cards.
2. **First impression:** User describes club as “welcoming / for beginners” not “race results club” — addresses comparison report ⚠️ on social vibe.
3. **Committee feasibility:** Web volunteer can update next-run date and time in one card without touching hero copy — supports Q2 weekly workflow.
4. **Member regression:** Existing members still find news, results, calendar without extra clicks — tables preserved under **For members**.

---

## 12. Summary

The mock homepage is not a visual rebrand for its own sake. It is an **information-design response** to research showing Olympic Harriers loses nervous beginners online despite strong in-club offerings. Black and red express club identity; white cards and clear hierarchy express **approachability**; the top-of-page structure implements the highest-impact recommendations (Q1, Q2, Q3, Q5, L1) without abandoning the live site’s content model. Trade-offs favour volunteer maintainability, mobile lookup on run day, and honest messaging about harrier-season complexity over polish features (photography, maps, focus states) that production can add in a later pass.

---

*References: `olympic_mock_home.html`, `olympic_recommendations.md`, `comparison_report.md`.*
