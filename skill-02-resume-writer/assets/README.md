# assets/: Skill 02: Resume Writer

This folder is reserved for assets that support document generation: templates, style definitions, fonts, and format variations that extend what the resume writer can produce.

---

## What Belongs Here

**Document style definitions**
The skill uses a defined color palette and font standard for Word output. If you want to extend or modify the visual style: for example, to create a cleaner single-column ATS format, a two-column executive layout, or a branded version for a specific industry: place the style definition file here. Name it descriptively: `style_ats_plain.md`, `style_executive_twocol.md`. Reference it from SKILL.md when the user requests that format.

**ATS-safe plain text template**
Many applicant tracking systems strip formatting entirely. An ATS-safe output template defines exactly how content should be ordered and delimited when Claude produces plain text output: section headers, spacing, and character rules that maximize parsability. Place that template here as `template_ats.txt`.

**Industry-specific resume variants**
Different industries have different resume conventions. A federal government resume (USAJobs format) is structured entirely differently from a creative industry portfolio resume or a technical engineering resume. If you build a variant for a specific industry, place the format specification here: `format_federal.md`, `format_creative.md`, `format_engineering.md`. Update SKILL.md to offer these when the user's target industry matches.

**Cover letter format variants**
The default cover letter format works for most professional roles. For academic positions, research roles, or creative fields, the format and conventions differ significantly. Place variant specifications here if you build them.

**Font and color reference**
If you want contributors to match the visual standard without reading through the SKILL.md, place a one-page `style_reference.md` here summarizing the font, color palette, margin, and spacing standards used across all documents this skill produces.

---

## Current Style Standard (for reference)

| Element | Value |
|---|---|
| Font | Arial |
| Page size | US Letter (8.5 x 11 in) |
| Margins | 1 inch all sides |
| Primary color | #1A3C6E |
| Accent color | #1D9E75 |
| Warning color | #92400E |
| Background light | #F2F4F6 |

---

## What Does Not Belong Here

- Reference documents that guide Claude's writing style: those go in `references/`
- Executable scripts for document generation: those go in a `scripts/` folder if you add one
- Actual resume or cover letter files belonging to real people

---

## Contributing

If you build a format variant that serves a meaningful audience: veterans applying to federal positions, academics transitioning to industry, international candidates adapting to US resume conventions: open a pull request with the format file and a clear description of when the skill should use it.
