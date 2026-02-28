# HOWTO: Set Up AutoApply End-to-End (Clean + Shareable)

This guide shows exactly how to recreate the same job-application workflow in a **public-safe** way.

---

## 1) Clone AutoApply

```bash
git clone https://github.com/Shay350/AutoApply.git
cd AutoApply
```

---

## 2) Add your personal files (keep private where needed)

At minimum, prepare:
- Your resume PDF in repo root (example: `My_Resume.pdf`)
- Your profile data in `job-profile.md`
- Your reusable writing style in `cover-letter-playbook.md`
- Your process rules in `INSTRUCTIONS.md`

### Important privacy rule
- Never commit secrets or credentials.
- Use `.secrets/` for local-only private notes.
- `.secrets/` is gitignored by default.

---

## 3) Fill `job-profile.md` properly

Update every placeholder, especially:
- `full_name`
- `email_primary`
- `phone_e164` (must include country code, e.g. `+1...`)
- `location`
- `work_authorization`
- `document_paths.resume_primary` (point to your resume file)
- `education_defaults`
- `experience_defaults`
- `skills.skills_normalized`

Keep data factual and machine-readable.

---

## 4) Customize `INSTRUCTIONS.md`

Define your exact policy for:
- Which jobs to apply to / skip
- Autofill behavior
- When to ask you vs auto-decide
- Submit policy (review-first vs auto-submit)
- Cover letter constraints
- Tracking workflow (optional)

Tip: each time the assistant makes a mistake, add a new explicit rule.

---

## 5) Optional: add a bullet source file for perfect copy/paste

If you want exact resume bullet reuse in forms, maintain a markdown source like:
- `resume-template.md` (or your own name)

Then enforce this rule in `INSTRUCTIONS.md`:
- copy bullets verbatim
- no paraphrasing
- keep real line breaks (not escaped `\n`)

---

## 6) Install and run OpenClaw

Install/start OpenClaw on your Mac, then verify:

```bash
openclaw status
```

You should see gateway running and your channel(s) linked if you plan to control via chat.

---

## 7) Browser automation mode (important)

You have two browser modes:

1. `openclaw` profile (isolated browser)
   - good for generic automation
   - usually not where your personal Chrome extensions live

2. `chrome` profile (Browser Relay takeover of your real Chrome tab)
   - use this when you need your own Chrome context and extensions (e.g., Simplify)

### Browser Relay setup (step-by-step)

Use this once per tab/session when you want OpenClaw to control your real Chrome tab:

1. Install the **OpenClaw Browser Relay** Chrome extension (if not already installed).
2. Open the target page in **Google Chrome**.
3. Click the OpenClaw Browser Relay toolbar icon on that tab.
4. Confirm the extension badge/indicator shows it is **attached/ON**.
5. Keep that tab open while automation runs.
6. In your OpenClaw/browser calls, use `profile="chrome"` and keep operating on the same target tab.

### Verify relay is connected

- If OpenClaw can snapshot/click/type in that exact Chrome tab, relay is working.
- If it says no Chrome tab is connected, re-click the relay icon on the tab.
- If controls fail unexpectedly, refresh tab and re-attach relay.

### For extension-assisted flow (recommended)

1. Open target application in Chrome.
2. Ensure extension (e.g., Simplify) is installed, enabled, and logged in.
3. Attach Browser Relay on that same tab (badge ON).
4. Run automation against `profile="chrome"`.

This gives fastest practical form filling with your real browser + extension context.

### Common relay pitfalls

- **Wrong profile**: using `openclaw` instead of `chrome` means no personal extensions.
- **Not attached**: extension installed but relay icon not ON for the active tab.
- **Tab switched/closed**: automation target changed; re-attach and continue on same tab.
- **Permission blocks**: Chrome extension/site permissions disabled.


---

## 8) Daily usage pattern

For each application:
1. Provide job link to assistant.
2. Assistant evaluates fit using your rules.
3. Assistant autofills deterministic fields from `job-profile.md`.
4. Assistant asks only for missing/ambiguous required inputs.
5. Assistant provides final review summary.
6. Submit only per your submit policy.

---

## 9) Keep this repo shareable/public-safe

Before pushing publicly, check:
- No personal PDFs/docs you don’t want public
- No tokens, cookies, credentials, secrets
- No personal phone/email if this copy is meant as a template
- No accidental session logs

Quick checks:

```bash
git status
git diff --staged
```

---

## 10) Create your own clean public template from a private working repo

If you built a personalized repo and want a public-safe clone:

1. Copy files into a new folder.
2. Remove personal artifacts (resume PDF, identity-specific docs, secrets).
3. Replace with placeholders.
4. Reinitialize git history (orphan/single clean commit).
5. Push as new public repo.

Example reset pattern:

```bash
rm -rf .git
git init
git add .
git commit -m "Initial public template"
```

---

## 11) Suggested directory structure

- `README.md` — overview and quick start
- `HOWTO.md` — this detailed setup guide
- `INSTRUCTIONS.md` — behavioral and workflow rules
- `job-profile.md` — machine-readable candidate profile
- `cover-letter-playbook.md` — tone + proof-point strategy
- `resume-template.md` — optional exact bullet source
- `.secrets/` — local-only private notes (ignored)

---

## 12) Maintenance checklist

- Keep `job-profile.md` current after any new internship/project/skill changes.
- Update `INSTRUCTIONS.md` whenever recurring friction appears.
- Keep commits focused and descriptive.
- If publishing, do a final privacy sweep before push.

---

## 13) Minimal first-time checklist

1. Clone repo
2. Add your resume PDF
3. Fill `job-profile.md`
4. Tune `INSTRUCTIONS.md`
5. Verify OpenClaw status
6. Attach Chrome tab (if using extensions)
7. Run first application in review-first mode

You’re now set up with a reusable AI-assisted job application workflow.