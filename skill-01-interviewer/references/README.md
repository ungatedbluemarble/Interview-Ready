# references/: Skill 01: Interviewer

This folder is reserved for reference documents that guide how Claude conducts the intake conversation and builds the user profile.

---

## What Belongs Here

**Intake question extensions**
The default onboarding sequence in SKILL.md covers the core profile fields. If you develop supplemental question sets for specific candidate populations: veterans transitioning to civilian roles, candidates returning after a career gap, new graduates with limited work history, or candidates making an industry pivot: place those question guides here. Name them clearly: `intake_veterans.md`, `intake_career_gap.md`, `intake_new_graduate.md`, `intake_career_changer.md`. Reference them from SKILL.md when the user's situation matches.

**Profile validation rules**
As the profile schema evolves, you may want to define validation logic: required fields before handoff, field format standards, or rules for flagging incomplete profiles before a downstream skill runs. Place a `profile_validation_rules.md` here that documents what constitutes a complete and usable profile for each downstream skill. This helps contributors understand the minimum bar before routing a user to Skills 02, 03, or 04.

**Sensitivity handling guidance**
Some intake questions touch sensitive territory: reasons for leaving a current employer, compensation history, employment gaps, health-related career interruptions, or personal circumstances. A reference document here can guide Claude on how to ask these questions with appropriate care, how to handle disclosures that require sensitivity, and when to offer the user the option to skip. Place this as `sensitivity_handling.md`.

**Localization guides**
If the onboarding conversation is extended to support languages other than English, place localized versions of the intake prompts and confirmation language here alongside notes on cultural context that may affect how questions should be framed. Name them: `intake_localization_es.md`, `intake_localization_fr.md`, and so on.

---

## What Does Not Belong Here

- Assets used in document generation: those go in `assets/`
- The profile schema itself: that lives in `shared/user-profile-schema.md` and is the single source of truth
- Personal profile data from real users

---

## Contributing

If you develop intake extensions for a candidate population that is meaningfully underserved by the default onboarding sequence, open a pull request with the reference file and a note on which population it serves and how SKILL.md should route to it.
