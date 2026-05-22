# references/: Skill 03: Job Search Expert

This folder is reserved for reference documents that guide how Claude evaluates job descriptions, matches candidates to roles, and researches companies and market context.

---

## What Belongs Here

**JD evaluation examples**
Worked examples of job description evaluations: showing the full assessment framework applied to a realistic JD against a fictional candidate profile: give Claude a concrete model to follow. These are the Skill 03 equivalent of the resume and interview prep examples in Skills 02 and 04. Place them here as `jd_evaluation_example_[role_type].md`. Use John Doe or Jane Doe as the candidate. Use fictional company names.

**Industry transfer guides**
Some candidates have strong transferable skills but need help articulating how their background maps to a new industry. Reference guides for common transfer paths: military to corporate, academic to industry, nonprofit to private sector, technical IC to management: help the skill give more accurate fit assessments and positioning advice. Place them here as `transfer_[from]_to_[to].md`.

**Title variation reference**
Job titles vary significantly across companies and sectors for the same function and level. A reference document mapping common functional roles to their title variations helps the skill give more precise search targeting recommendations. For example, "Head of Customer Success" maps to VP of CS, Director of CS, Customer Success Lead, Client Success Manager, and Post-Sales Director depending on company size and stage. Place this as `title_variations.md`.

**Company research query templates**
Structured web search query patterns that reliably surface the information needed for company evaluation: funding data, headcount, recent news, Glassdoor signals, leadership profiles: help the skill conduct more consistent research. Place them here as `company_research_queries.md`.

**Red flag reference**
A curated list of signals to look for when researching a company or evaluating a job description that may indicate risk to the candidate: recent mass layoffs, pending litigation, unusual equity structures, high leadership turnover, or patterns associated with poor candidate experience. Place this as `red_flag_reference.md`. Include the date of last review at the top: red flag patterns shift over time.

---

## What Does Not Belong Here

- Market compensation data: that belongs in `assets/` where it can be clearly dated and updated
- Actual job descriptions from real companies
- Personal profile data of any kind

---

## Contributing

If you build a reference that meaningfully improves the accuracy or depth of job fit evaluation for a specific industry, candidate type, or role category, open a pull request with the file and a note on what it covers and when the skill should load it.
