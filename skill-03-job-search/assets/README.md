# assets/: Skill 03: Job Search Expert

This folder is reserved for assets that support job search evaluation: industry mappings, evaluation frameworks, role taxonomy files, and market data references that make the skill's analysis more precise and useful.

---

## What Belongs Here

**Industry-to-role taxonomy**
A structured mapping of industries to common job titles, title variations, and seniority levels helps the skill give more precise targeting recommendations. If you build this: for example, a file that maps "enterprise software" to the 15 most common CS/sales/ops titles at each level: place it here as `taxonomy_industry_roles.md`. The skill can load it when generating role targeting recommendations.

**Compensation benchmarks**
Market compensation data by role, level, and geography ages quickly but is useful when it exists. If you maintain a periodically updated benchmark file: sourced from Levels.fyi, Glassdoor, or similar: place it here as `compensation_benchmarks.md` with the date it was last updated clearly marked. The skill should always flag to the user that compensation data has a shelf life and they should verify against current sources.

**JD evaluation rubric**
The skill's fit scoring (Strong / Moderate / Stretch) is based on logic defined in SKILL.md. If you want to make that rubric explicit and adjustable: for example, to weight technical requirements differently from leadership requirements: place a structured rubric file here as `jd_evaluation_rubric.md`. Contributors can then modify the rubric without editing the core SKILL.md.

**Red flag signal library**
A curated list of warning signals to look for in job descriptions and company research: unusual equity structures, patterns associated with high churn, compliance red flags, and similar: gives the skill more to work with when advising a user whether to pursue a role. Place it here as `red_flag_signals.md`.

**Search query templates**
The skill generates web search queries for company research and role market analysis. If you want to standardize and improve those queries: for example, structured query patterns that reliably surface funding data, Glassdoor signals, or recent news: place a query template file here as `research_query_templates.md`.

---

## What Does Not Belong Here

- Actual job descriptions: those are provided by the user at runtime, not stored here
- Personal profile data of any kind
- Reference documents that guide Claude's writing style: those go in `references/`

---

## A Note on Data Currency

Any asset in this folder that contains market data: compensation ranges, industry hiring trends, role demand signals: should include a clearly marked date of last update at the top of the file. The skill should surface that date to the user when drawing on time-sensitive data so they can judge its relevance.

---

## Contributing

If you build an asset that meaningfully improves the skill's ability to evaluate fit or guide job targeting for a specific industry, level, or candidate type, open a pull request with the file and a note on the data source, currency, and intended use.
