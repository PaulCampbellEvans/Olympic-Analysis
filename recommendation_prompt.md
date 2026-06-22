# Single-Club Recommendation Prompt — Image & New-Member Accessibility

Use this prompt to generate actionable recommendations for **one** running club on how to improve its public image and accessibility to potential new members. Ground the advice in the comparative analysis already completed for Wellington harrier clubs.

---

## Prompt (copy from here)

**Role:** You are a club communications and member-experience adviser with expertise in community sports organisations. You understand that most harrier clubs are volunteer-run with limited time and budget. Your recommendations must be practical, prioritised, and respectful of that reality.

**Task:** Using the comparative analysis in `comparison_report.md`, produce a focused improvement plan for **one club only** on how it can better attract and reassure a nervous prospective member — especially a social runner who is new to running.

**Target club:**
- Name: [Olympic Harriers]
- Website: [https://www.olympicharriers.nz/]
- Replace the placeholders above if advising a different club.

**Target audience (prospect persona):**
- Location: Wellington region
- Experience: New to running — can complete a slow 5 km
- Goals: Social runs, build confidence, feel supported
- Anxiety: Turning up alone to an unknown group; fear of being too slow; unclear on cost, schedule, and “what happens on day one”

**Benchmark context (from `comparison_report.md`):**
Use the full comparison report as evidence. Pay particular attention to clubs rated **Strong fit** for this persona (**Wellington Scottish**, **Hutt Valley Harriers**) and what they do well that the target club does not. Also note gaps flagged for the target club in its club-by-club section (ratings, watch-outs, and unanswered questions).

**Clubs in the comparison (for reference only — do not recommend changes to all of them):**
1. Hutt Valley Harriers — hvh.org.nz
2. Olympic Harriers — olympicharriers.nz
3. Trentham United — trenthamunited.com
4. Wellington Harrier Athletic Club (WHAC) — whac.org.nz/wp
5. Wellington Scottish — scottishathletics.org.nz

---

### What to analyse for the target club

Review the target club’s **website**, **join/membership pages**, and **public social channels** linked from the site (or referenced in `comparison_report.md`). Evaluate through the prospect’s eyes:

#### 1. First impressions & positioning
- Within 30 seconds, can a newcomer answer: *What is this club? Who is it for? Can I try before I join?*
- Does the tone feel welcoming to beginners, or mainly race- and results-focused?
- Is social/recreational membership clearly explained and distinct from competitive membership?
- How does the club’s image compare to the best-performing clubs in the comparison report?

#### 2. Website & information architecture
- Is there a dedicated **“New to the club”** or **“First run”** path (or equivalent)?
- Are **fees**, **schedules**, **meeting points**, and **contact for newcomers** easy to find on mobile?
- Is any content stale, broken, or empty (e.g. blank Join page, pages not updated in years)?
- What should be promoted to the homepage vs buried in news/archives?

#### 3. Schedule clarity & “turn up alone” confidence
- Can a prospect find **when**, **where**, and **which session** suits a slow 5 km runner this week?
- Is it clear what happens on **race weekends** vs **social pack-run weekends**?
- Are walkers and slow joggers explicitly welcome?
- Is there a named contact, pack leader, or “newcomer greeter” mentioned online?

#### 4. Social media & outward-facing content
- Balance of community/social posts vs race results and performance content
- Frequency and consistency of posting
- Beginner-friendly content: “come try us”, first-timer FAQs, photos of mixed abilities
- Red flags: ghost accounts, cliquey tone, no response to comments, insider-only language

#### 5. Practical joinability
- Trial/guest policy — stated clearly or only implied?
- Membership tiers, costs, and what each tier includes
- How newcomers get looped in after the first visit (newsletter, WhatsApp, Facebook group, app)
- Safety and logistics for first visit (parking, kit, weather, hills, dark runs)

#### 6. Gap analysis vs best-in-class peers
For each dimension where the target club scored ⚠️ or ❌ in `comparison_report.md`, identify:
- What **HVH** or **Wellington Scottish** (or another stronger peer) does instead
- Whether the target club already does this in person but fails to communicate it online
- The smallest change that would close the gap

---

### Output format

Save the result as **`[club-slug]_recommendations.md`** (e.g. `olympic-harriers_recommendations.md`) structured as follows:

#### Executive summary (3–5 sentences)
What is the single biggest barrier preventing a nervous social beginner from choosing this club? What is the highest-leverage fix?

#### Current state snapshot
Brief summary of how the target club currently presents itself to newcomers, citing specific evidence from `comparison_report.md` and the live site (page names, quotes, dates). Distinguish **facts** from **inferences**.

#### Strengths to preserve
2–4 things the club already does well that should not be diluted (e.g. family focus, recreational tier, pack structure, volunteer culture).

#### Recommendations (prioritised)

Group into **Quick wins** (≤1 volunteer hour each), **Medium effort** (half-day or small project), and **Larger projects** (seasonal or committee-level).

For each recommendation include:

| Field | Detail |
| --- | --- |
| **Issue** | What problem this solves for a new member |
| **Evidence** | Quote or reference from comparison report or site |
| **Recommendation** | Specific, actionable change |
| **Example** | Optional: draft copy, page heading, social post, or FAQ answer |
| **Benchmark** | Which peer club does this well (if applicable) |
| **Effort** | Low / Medium / High |
| **Impact** | Low / Medium / High |

Aim for **8–12 recommendations** total, with at least 3 quick wins.

#### Suggested “New member” page outline
A wireframe or bullet list for a single webpage (or prominent homepage section) that would answer everything a nervous beginner needs before their first visit:
- Who we are (one paragraph)
- Is this for me? (beginners, walkers, social runners)
- Try before you join
- This week’s best session for newcomers (with caveat if schedule varies)
- What to bring / expect
- Membership options and costs
- Who to contact / what to say when you arrive
- Map or address

#### Sample content (optional but valuable)
Provide **ready-to-use draft text** for:
1. Homepage hero or banner (2–3 sentences)
2. One Facebook/Instagram post inviting newcomers
3. One FAQ entry: *“I’m slow and nervous — will I fit in?”*

#### 90-day action plan
A simple phased checklist:
- **Week 1–2:** Quick wins
- **Month 1:** Medium items
- **Month 2–3:** Larger items and measurement

#### How to measure success
3–5 simple, volunteer-trackable indicators (e.g. “Join page bounce rate”, “number of ‘first visit’ emails to captain”, “new social members vs competitive”, social post engagement on newcomer content).

---

### Rules

- **One club only** — all recommendations must be for the target club named above.
- **Evidence-based** — cite `comparison_report.md` and specific site pages; do not invent fees, schedules, or policies.
- **Persona-centred** — weight recommendations for a **social, beginner, nervous** prospect, not an elite racer.
- **Be constructive** — acknowledge volunteer constraints; prefer copy changes and information reordering over expensive redesigns.
- **Be fair** — the club may be welcoming in person but poor online; say so and recommend closing that gap.
- **Do not recommend** changes to other clubs except as brief benchmarks.
- **Note limitations** — if social feeds could not be fully reviewed, say what was inferred and what should be verified.
- **NZ context** — Athletics NZ / Athletics Wellington affiliation, harrier season (Apr–Oct), social vs competitive membership tiers where relevant.

---

### Optional add-on (if you can browse live)

Re-fetch the target club’s website and any linked social pages. Compare current live content to `comparison_report.md` (analysis date: 23 June 2026). Flag anything that has changed since the report. Update recommendations if the club has already fixed an issue.

---

## Usage notes

1. Attach or paste `comparison_report.md` when running this prompt.
2. Set the **Target club** name and website at the top.
3. For Olympic Harriers, the report’s club section (§2) and “Maybe” rating are the starting baseline; benchmark against HVH and Wellington Scottish.
4. Expected deliverable: a single markdown file of prioritised, copy-ready recommendations — not a repeat of the full five-club comparison.
