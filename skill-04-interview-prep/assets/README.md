# assets/: Skill 04: Interview Prep

This folder is reserved for assets that support interview preparation document generation: stage-specific templates, question banks, negotiation frameworks, and format variants that extend what the skill can produce across the full hiring pipeline.

---

## What Belongs Here

**Stage-specific document templates**
The skill produces a different prep document for each pipeline stage. If you want to define a precise template for any stage: fixed section order, callout box placement, table layouts: place it here as a named template file. Use clear names: `template_recruiter_screen.md`, `template_hiring_manager.md`, `template_panel.md`, `template_final_round.md`, `template_offer_negotiation.md`. The skill loads the appropriate template based on the stage the user is preparing for.

**Question bank by function and level**
Anticipated interview questions vary significantly by functional domain (sales, engineering, finance, operations) and seniority level (IC, manager, director, VP). A structured question bank gives the skill more to draw from when building the Q&A section of a prep document. Place it here as `question_bank.md`, organized by function and level. The skill selects relevant questions based on the user's profile and the role they are preparing for.

**Offer negotiation frameworks**
The offer negotiation stage is where most candidates are least prepared. A structured negotiation framework: covering total compensation components, anchoring strategy, counteroffer language, and walk-away analysis: makes the skill's negotiation guide significantly more useful. Place it here as `negotiation_framework.md`.

**Panel interview preparation matrix**
Panel interviews require the candidate to manage multiple evaluators with different lenses simultaneously. A matrix that maps common panelist types (hiring manager, peer, technical evaluator, HR, skip-level executive) to their typical priorities and likely question styles helps the skill build panelist-specific guidance. Place it here as `panel_prep_matrix.md`.

**Industry-specific interview conventions**
Interview norms vary by industry. A finance or consulting interview may include case components. A technical role may include a take-home assessment. A healthcare or regulated industry role may include compliance-specific questions. If you build an industry-specific prep extension, place it here: `conventions_finance.md`, `conventions_technical.md`, `conventions_regulated.md`. The skill loads the relevant file when the user's target industry matches.

**Mock interview question sets**
The skill supports a mock interview mode at the end of prep document generation. Curated question sets by role type, function, and seniority level: beyond what is generated dynamically: can be stored here and loaded during mock sessions. Name them: `mock_questions_cs_director.md`, `mock_questions_ic_engineer.md`, and so on.

---

## What Does Not Belong Here

- Reference documents that guide Claude's writing style and document structure: those go in `references/`
- Actual prep documents generated for real users: those are session outputs, not stored here
- Personal data of any kind

---

## A Note on the Pipeline

The skill covers five stages: recruiter screen, hiring manager, panel, final round, and offer negotiation. Assets that extend a specific stage should be clearly labeled with that stage in the filename so contributors and the skill can identify them without reading the full file. Assets that apply across all stages should say so at the top of the file.

---

## Contributing

Interview norms, question conventions, and negotiation dynamics shift over time and vary significantly across industries and geographies. If you have domain expertise that would make prep documents meaningfully more accurate for a specific context: regulated industries, executive-level hiring, international roles, technical assessments: open a pull request with the asset and a clear description of what it covers and when the skill should use it.
