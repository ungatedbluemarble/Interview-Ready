# Session Handoff: Calibrated Candidate

**Work session:** May 28, 2026
**Prepared by:** Claude Sonnet 4.6
**Repo:** github.com/ungatedbluemarble/calibrated-candidate

---

## Session Summary

This session covered repository audit, schema synchronization, feature scoping across three phases, GitHub issue authoring, and LinkedIn content production for the Calibrated Candidate open source project.

---

## Work Completed

### 1. Repository Audit and Schema Sync

Reviewed the full Calibrated Candidate ZIP: six skills, shared schema, web files, changelog, contributing docs, and PDF user guide.

Identified schema drift: five skills were on an older version of `user-profile-schema.md` missing the `company_research` object introduced in skill-04. Synced all six copies to the current version.

Delivered: `schema-sync.zip` containing the five updated `references/user-profile-schema.md` files with folder paths preserved for direct repo replacement.

### 2. Feature Scoping: Document Extraction Pipeline

Scoped a three-phase extraction pipeline feature. Verified all required libraries in the Claude Code Execution environment before writing a single requirement.

Libraries confirmed present: `markitdown`, `pdfplumber` 0.11.9, `python-docx` 1.2.0, `Pillow` 12.1.1, `pytesseract` with Tesseract 5.3.4 (eng only).

Key architecture decisions made during scoping:

- MarkItDown is the primary extraction path for PDF and DOCX, not raw pdfplumber or python-docx. It handles tables, columns, and form layouts internally.
- Scanned PDF detection required: MarkItDown returns empty output silently on scanned PDFs. Detection threshold set at 100 characters. Fallback routes to pdfplumber rasterization plus pytesseract OCR.
- `target_job_description_markdown` ownership resolved: skill-02 writes to `source_jd_skill02` only. Skills 03 and 04 write to a separate `job_descriptions` array. No ownership conflict.
- Per-document timestamps, not per-session: `extracted_at` is tracked independently per field so each document ages independently.
- Batched freshness checks: all stale field prompts fire once at session start as a single consolidated message, not mid-workflow.
- `id` field in `job_descriptions` uses a hash of company, role, and timestamp rather than an incrementing integer to prevent duplicate IDs across sessions.
- Known ceiling documented: Tesseract supports English only in the container environment. Mixed-language resumes will have non-English sections missed silently by OCR. Documented as a known limitation in affected skills.
- Claude Code local session handling: if required libraries are missing, the skill surfaces a plain-language message and routes to user paste. No tracebacks shown to the user.

### 3. GitHub Issues Authored

Four issues written and posted. All formatted as raw Markdown for direct GitHub paste. Standard going forward: all issues produced as `.md` files.

| Issue | Title | Status | Blocked By |
|---|---|---|---|
| #12 | Local Markdown Pre-Processing Integration | Open | Blocked by #13 |
| #13 | Skill 02: Normalize uploaded documents to Markdown before processing | Active | |
| #14 | Skill 03, 04, 05: Connect downstream skills to extracted document cache | Pending | Blocked by #13 |
| #15 | Skill 02, 03, 04, 05: Add extraction pipeline health checks and durability logging | Pending | Blocked by #14 |

Dependency chain: #13 unblocks #14 unblocks #15. #12 is superseded by #13 and should be closed when #13 merges.

### 4. LinkedIn Post and Roadmap Assets

LinkedIn post written and revised. Skill references updated from internal numbering to user-facing names (Resume Writer, Job Search Expert, Interview Prep, Mock Interviewer). Hashtag corrected from `#CalibatedCandidate` to `#CalibratedCandidate`.

Roadmap visual produced in two color themes (light and dark) at 900px width with content-hugging height. Delivered as standalone HTML files for browser screenshot at correct dimensions.

Files delivered this session:

- `schema-sync.zip`: five updated schema files
- `issue-local-preprocessing.md`: GitHub issue #12
- `issue-phase1-extraction-pipeline.md`: GitHub issue #13
- `issue-phase2-downstream-consumption.md`: GitHub issue #14
- `issue-phase3-durability.md`: GitHub issue #15
- `roadmap-900x600-dark.html`: dark theme roadmap for LinkedIn
- `roadmap-900-light.html`: light theme roadmap for LinkedIn
- `calibrated-candidate-session-handoff-2026-05-28.md`: this document

---

## Schema Changes Reference

All fields below are added to `calibrated_candidate_profile.json` across the three phases. All six `references/user-profile-schema.md` copies must be synced after each phase merges.

### Phase 1: extracted_documents

```json
"extracted_documents": {
  "source_resume": {
    "markdown": "",
    "extraction_method": "",
    "extracted_at": ""
  },
  "source_cover_letter": {
    "markdown": "",
    "extraction_method": "",
    "extracted_at": ""
  },
  "source_jd_skill02": {
    "markdown": "",
    "extraction_method": "",
    "extracted_at": ""
  }
}
```

### Phase 2: job_descriptions

```json
"job_descriptions": [
  {
    "id": "",            // hash of company+role+extracted_at
    "company": "",
    "role": "",
    "source": "",        // URL, filename, or user_paste
    "markdown": "",
    "extraction_method": "",
    "extracted_at": ""
  }
]
```

### Phase 3: extraction_health_cache

```json
"extraction_health_cache": {
  "last_checked": "",
  "next_check_due": "",
  "library_versions": {
    "markitdown": "",
    "pdfplumber": "",
    "pytesseract": "",
    "pillow": ""
  },
  "methods": [
    {
      "name": "",        // markitdown | ocr_rasterized | ocr_direct | user_paste
      "status": "",      // passing | degraded | failed
      "last_tested": "",
      "note": ""
    }
  ]
}
```

---

## Standing Rules Established This Session

- All GitHub issues must be produced as `.md` files for direct paste into GitHub.
- Every build session requires updating: all six `references/user-profile-schema.md`, `shared/user-profile-schema.md`, README, affected SKILL.md files, CHANGELOG.md, and web files (index.html, job-seeker.html, recruiter.html, market-comparison.html).
- All technical claims must be verified in the Code Execution environment before being written into an issue.
- LinkedIn posts must use user-facing skill names, not internal skill numbers.
- Roadmap visuals are delivered as standalone HTML files at fixed pixel dimensions for browser screenshot. Do not rely on Claude artifact rendering for final image capture.
- Schema syncs across all six skill reference copies are required after every merge that touches `user-profile-schema.md`.
- All Calibrated Candidate session handoff documents must be produced as `.md` files, not `.docx`. Markdown is the standard format for all future handoffs.

---

## Next Session Priorities

In order of dependency:

- Begin Phase 1 build: implement extraction pipeline in skill-02. Start with SKILL.md updates, then the Python extraction script, then schema write logic.
- Update all README files and web content to reflect the extraction pipeline feature once Phase 1 is merged.
- Review skill-01 (Interviewer) and skill-02 (Resume Writer) in full detail. These have not been audited this session.
- Decide whether to close #12 as superseded when #13 merges, or update it with a cross-reference.
- Consider adding a PR template checklist to the repo enforcing schema sync and README updates as hard gates on every merge.

---

*Calibrated Candidate is open source. github.com/ungatedbluemarble | Built for Claude Desktop, claude.ai, and Claude Mobile*
