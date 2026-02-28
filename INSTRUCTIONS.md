# Instructions

Use this file to define how your assistant handles job applications.

---

## Workflow Mode
- Default mode: Review-first
- Submit policy: Ask before final submission unless explicitly told to auto-submit

## Job Link Intake
- Accepted input format:
  - `apply: <url>`
  - direct pasted job link

## Application Rules (template)
- Must-have criteria:
  - role level: Intern or New Grad (edit as needed)
  - paid roles only
  - clear job description and identifiable company

- Reject/skip criteria:
  - unpaid roles
  - duplicate applications
  - ambiguous or suspicious portals

## Autofill Policy
- Primary objective: maximize autofill coverage using `job-profile.md`.
- Autofill deterministic fields automatically.
- Ask only when required fields are missing or ambiguous.
- Always present final review before submit.

## Cover Letter Rules
- Desired length: 220–320 words
- Tone: specific, concise, evidence-based
- No fabricated claims or metrics

## Resume & Docs Rules
- Set your default resume path in `job-profile.md`.
- Attach cover letter only when required or strategically useful.

## Tracking (optional)
- Add your own tracker URL and status flow here.

## Continuous Improvement Rule
When mistakes or repeated clarifications occur:
- Add a new explicit rule here.
- Update `job-profile.md` with reusable answers.
