# Survey Results → Infographic Prompt (Olympic Harriers)

Use this prompt to analyse a member survey CSV and produce one or more infographics that summarise responses fairly, with charts for common interests and common challenges. Output should use Olympic Harriers **black, white, and red** branding.

---

## Prompt (copy from here)

**Role:** You are a neutral data analyst and information designer working for a volunteer-run athletics club. You present survey findings accurately — neither cheerleading nor catastrophising. Your audience includes committee members, coaches, and members who did not complete the survey.

**Task:** Analyse the survey results in the CSV file provided. Produce a written analysis plus specifications (or deliverables) for **one or more infographics** that summarise what members said about interests, barriers, and priorities. Charts must reflect the **data as given**, not what the club might wish were true.

**Input file:**
- Path: `[survey_responses-20260823.csv]` *(update filename if different)*
- Context: Olympic Harriers and Athletic Club (OHAC) member experience survey, Wellington region.

**Output file(s):**
- Analysis report: `[survey_infographic_report.md]`
- Infographic deliverable(s): HTML canvas and/or SVG/PDF specs as `[survey_infographic.html]` *(or separate files if multiple infographics)*

---

### Brand & visual theme

Apply Olympic Harriers colours consistently across all infographics:

| Token | Hex | Use |
| --- | --- | --- |
| **Black** | `#0d0d0d` | Headings, body text, chart axes, footer |
| **Red** | `#c8102e` | Primary data series, highlights, key callouts |
| **Red dark** | `#9e0c24` | Hover states, secondary emphasis |
| **White** | `#ffffff` | Backgrounds, chart plot areas, reversed text on black |
| **Grey light** | `#f5f5f5` | Alternate rows, subtle chart bands |
| **Grey mid** | `#888888` | Secondary labels, low-emphasis data |

**Typography:** Clean sans-serif (e.g. Segoe UI, system-ui). Avoid decorative fonts.

**Tone:** Professional, club-owned, accessible. No stock-photo clutter unless real member photos are supplied separately.

**Singlet reference (optional):** Club uniform is black, red, white, and silver/grey — secondary charts may use grey for tertiary categories only; do not introduce unrelated palette colours.

---

### Before you chart: data preparation

1. **Load and inspect the CSV**
   - Row count, response rate context if known (note if unknown).
   - Column names and types: rating scales, single-select, multi-select (“Tick all that apply”), free text, matrix questions (e.g. communication channels).
   - Missing values, `#ERROR!`, empty cells, duplicate timestamps — document how handled.

2. **Clean multi-select fields**
   - Split comma-separated tick-box answers into countable items.
   - Normalise obvious variants (trim whitespace, consistent casing; do **not** merge distinct options unless duplicates are clearly typos — list assumptions).

3. **Segment where useful**
   - By membership type (e.g. social vs full competitive vs parent/supporter) **only when sample size allows** — suppress or merge segments with n &lt; 5 and say so.
   - Do not over-segment; prefer club-wide totals for headline infographics.

4. **Free-text fields**
   - Do not force into charts unless thematically coded.
   - Use for **qualitative appendix** or word-frequency / theme summary with clear “interpreted themes” labelling — not presented as exact counts unless coded systematically.

---

### Non-bias rules (mandatory)

- **Report response counts** on every chart (`n = …`). Percentages must state whether they are of all respondents or of those who answered that question.
- **Do not cherry-pick** quotes or metrics that support a single narrative; show strongest consensus **and** notable disagreement.
- **Label uncertainty:** small samples, optional questions with low completion, and leading/question-order effects where relevant.
- **Distinguish facts from interpretation:** “42% selected Weekday evening” vs “Members want more evening runs” (the second requires explicit inference language).
- **Free text is illustrative**, not statistically representative unless coded.
- **Experience ratings:** show full distribution (1–5), not only mean — means hide polarisation.
- **Avoid advocacy language** in titles (“Members desperately need…”) — use neutral titles (“Barriers to attendance (selected)”).

---

### What to analyse

#### A. Interests & engagement (common positives)

Questions to prioritise (map to actual CSV column names on load):

| Theme | Typical columns / content |
| --- | --- |
| What works well | Open text — theme summary |
| What attracted you | Multi-select — bar chart top attractions |
| What keeps you involved | Multi-select — bar chart |
| Activities currently taken part in | Multi-select — participation chart |
| Desired activity types | Multi-select — “what would add value” |
| Preferred run times / locations | Multi-select — heatmap or grouped bars |
| Skills willing to share | Open / list — tag cloud or top themes |

**Chart suggestions:** Horizontal bar charts (top 8–10 items), stacked bars by membership type (if n sufficient), dot plot for experience rating distribution.

#### B. Challenges & friction (common barriers)

| Theme | Typical columns / content |
| --- | --- |
| What could be improved | Open text — themed summary |
| Barriers to attendance | Multi-select — ranked bar chart |
| What would make attendance easier | Multi-select — compare to barriers |
| Communication usefulness | Matrix — grouped bar or heatmap (channel × useful / not useful) |
| Information hard to find | Multi-select |
| Website / comms suggestions | Open text — themes only |

**Chart suggestions:** Diverging bar (facilitators vs barriers if comparable), heatmap for channel usefulness, “top 5 barriers” single infographic panel.

#### C. Cross-cutting

- Overall experience rating (1–5): histogram + median/mean footnote.
- Membership type breakdown: donut or simple bar (sample composition).
- Informal groups: yes / no / would like to be — pie or bar.
- Preferred communication channels: bar chart.

---

### Infographic structure

Produce **at least one** of the following (choose based on data richness):

#### Option 1 — Single-page summary (`survey_infographic.html`)

Sections top to bottom:

1. **Header** — “OHAC Member Survey — Summary” + date range of responses + `n`
2. **Snapshot** — experience rating distribution + membership mix (2 small charts)
3. **What members value** — top interests / activities / retention drivers (1 chart)
4. **What gets in the way** — top barriers + communication pain points (1 chart)
5. **What members want more of** — desired activities & run times (1 chart)
6. **Footer** — methodology note, limitations, “full report” link

#### Option 2 — Multi-panel set (2–3 files or pages)

- **Infographic A:** Interests & participation  
- **Infographic B:** Barriers & communication  
- **Infographic C:** Open-text themes (word-style summary, not a chart of fake precision)

Each panel must stand alone if shared on Facebook or printed A4.

---

### Output format: analysis report

Structure `survey_infographic_report.md` as:

#### Executive summary (5–7 sentences)
Neutral overview: response count, overall satisfaction shape, top 3 interests, top 3 challenges, largest data gaps.

#### Data quality & methodology
Rows, date range, exclusions, multi-select handling, segments used.

#### Findings — interests
Bullet points with numbers; reference chart IDs.

#### Findings — challenges
Same; call out where barriers and “hard to find info” overlap.

#### Findings — communications
Channel usefulness summary; preferred channels vs actual usefulness gaps.

#### Free-text themes (optional questions)
Themed bullets with example quotes (anonymised); max 2–3 quotes per theme.

#### Infographic specifications
For each chart: title, chart type, data source columns, exact labels, colours (hex), footnotes.

#### Limitations & caveats
Sample bias, self-selection, volunteer survey, questions not answered by all.

#### Recommended actions (optional, clearly labelled “inference”)
2–4 evidence-based suggestions — not a committee agenda.

---

### Output format: infographic HTML/CSS

If generating HTML:

- Self-contained file(s) with embedded CSS.
- Use SVG or CSS for charts (or Chart.js / similar if specified — prefer no external deps for portability).
- **Accessible:** sufficient colour contrast; don’t rely on colour alone — patterns or labels on bars.
- **Print-friendly:** `@media print` with white background option.
- Include `n` and question wording in small print under each chart.
- Mock banner if prototype: *“Survey summary — draft for committee review”*

---

### Chart catalogue (use where data supports)

| Chart | Best for |
| --- | --- |
| Horizontal bar | Top tick-box choices (attractions, barriers, activities) |
| Histogram / bar (1–5) | Experience rating |
| Stacked bar | Channel usefulness (useful → not useful) |
| Heatmap | Time × location preferences (if both multi-select linked) |
| Donut (sparingly) | Membership type mix — max 5 slices |
| Side-by-side bars | Social vs competitive segment (if n ≥ 5 each) |

**Avoid:** 3D charts, pie charts with &gt;6 slices, truncated y-axes that exaggerate differences.

---

### Rules

- **Evidence-based:** Every percentage traceable to CSV counts; show working in report appendix if helpful.
- **Non-biased presentation** per section above — no spin.
- **OHAC branding** — black, white, red only (+ greys for UI).
- **Privacy:** Do not include names, emails, or identifiable contact details in infographics; anonymise quotes.
- **One survey file** — do not merge with external datasets unless provided.
- **Note limitations** — if a question has &lt; 10 responses, say “low n” on the chart or omit segment breakdown.

---

### Optional add-on

- Compare **desired activities** vs **current participation** — gap chart (only where both columns exist).
- Export static PNG/PDF instructions for committee slides.
- Te reo Māori headings for public-facing version (optional second pass).

---

## Usage notes

1. Attach or place the CSV in the workspace; update the filename placeholder above.
2. Run the prompt in Agent mode with the CSV readable.
3. Review `survey_infographic_report.md` for neutrality before publishing infographics to members.
4. Align website/communications recommendations with `olympic_recommendations.md` only where survey data independently supports them — do not conflate projects without evidence.

---

## Survey column reference (from `survey_responses-20260823.csv`)

*Verify against actual file header on load.*

| # | Column (abbreviated) | Type |
| --- | --- | --- |
| 1 | Timestamp | Date |
| 2 | Membership type | Single-select |
| 3 | Overall experience (1–5) | Rating |
| 4 | What works well | Free text |
| 5 | What could be improved | Free text |
| 6 | What first attracted you | Multi-select |
| 7 | What keeps you involved | Multi-select |
| 8 | Activities currently take part in | Multi-select |
| 9 | Informal groups (Y/N/would like) | Single-select |
| 10 | Informal group description | Free text |
| 11 | Activities more members should know about | Free text |
| 12 | Activity types that would add value | Multi-select |
| 13 | When would attend more group runs | Multi-select |
| 14 | Best locations | Multi-select |
| 15 | What would make you attend | Multi-select |
| 16 | Barriers to attendance | Multi-select |
| 17–23 | Communication channel usefulness | Matrix |
| 24 | Information should be easier to find | Multi-select |
| 25 | More of in communications | Multi-select |
| 26 | Website/newsletter/Facebook suggestions | Free text |
| 27 | Preferred communication channel(s) | Free text / multi |
| 28 | Skills willing to share | Free text |
| 29 | Contact permission | Y/N |
| 30 | Name and contact (if yes) | PII — **exclude from infographics** |
| 31 | Anything else | Free text |
