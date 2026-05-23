# AGENTS.md

## Purpose
This repository supports tailored resume generation per job application.

## Standard Workflow For Each Job Application
1. Invoke the `humanizer` skill from `/Users/mutahharbm/.codex/skills/humanizer/SKILL.md` before writing, revising, or finalizing any resume or application text.
2. Create a folder under `job-applications/` at repository root.
3. Folder name format:
   - `<job-title> - <company-name>`
   - Use readable title case.
   - Replace `/` with `-` to keep paths valid.
4. Inside that folder, create a metadata text file named `job-details.txt`.
5. `job-details.txt` must include:
   - Current date
   - Company website
   - Job title
   - Full job description
6. Save the tailored LaTeX resume (`.tex`) in the same folder.
7. Compile the generated PDF in the same folder.
8. Rename the generated PDF to:
   - `Mutahhar BM - {Job Title}.pdf`
9. Keep only one PDF file after compile: do not keep `resume.pdf` or any duplicate copy once renamed.
10. Before final tailoring edits, run a keyword-gap check against the job description.
11. If required or repeated keywords are missing from the current resume (for example: GraphQL, AWS, GCP), pause and ask the user whether relevant real experience exists that should be added.
12. Before asking, review `resume-tailoring-items.txt` at repository root for reusable points that may close the gap.
13. If a relevant point exists in `resume-tailoring-items.txt`, ask the user whether to include it for this specific job.
14. Never invent experience to fill keyword gaps; only add points confirmed by the user.
15. If a job description emphasizes testing (for example: unit testing, integration testing, React Testing Library, Jest, coverage, quality gates), explicitly check testing-related points in `resume-tailoring-items.txt` and ask the user whether to include them in this job-specific version.

## `job-details.txt` Template
Use this structure:

```txt
Date: YYYY-MM-DD
Company: <Company Name>
Company Website: <https://...>
Job Title: <Job Title>

Job Description:
<Paste full job description here>
```

## Notes
- Always invoke the `humanizer` skill from `/Users/mutahharbm/.codex/skills/humanizer/SKILL.md` before any text drafting or text polishing step.
- Keep each job application self-contained in its own folder.
- Do not overwrite previous job application folders.
- Use the latest approved resume baseline as the source for tailoring.
- Always use the exact PDF naming format: `Mutahhar BM - {Job Title}.pdf`.
- PDF handling rule is rename-only: never keep both `resume.pdf` and `Mutahhar BM - {Job Title}.pdf` in the same folder.
- Resume writing style must stay professional, neutral, and human.
- Avoid repetitive AI-like phrasing patterns (for example, starting many bullets with the same word such as "Accomplished").
- Vary sentence openings and keep bullet language natural, specific, and believable.
- Do not write monotone sentence patterns that read like AI output. Avoid repeating the same opening verb across multiple bullets (for example, "Increased..." on several consecutive lines), and vary rhythm and structure naturally.
- Treat missing-skill escalation as mandatory: ask the user before inserting any new skill/experience that is not already explicit in the selected baseline resume.
- Confirmed testing context available for tailoring: during Devsinc tenure on the Kudo project, unit testing was implemented using Jest and React Testing Library (RTL).
