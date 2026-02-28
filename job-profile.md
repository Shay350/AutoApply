schema_version: "1.0"
profile_id: your_name_master_profile
last_updated: 2026-02-28
intended_use:
  - agent_autofill
  - ats_forms
  - llm_context

profile_metadata:
  identity:
    full_name: YOUR FULL NAME
    birth_date_iso: YYYY-MM-DD
    gender: optional
    veteran_status: optional
    disability_status: optional
    lgbtq_disclosed: false
  contact:
    email_primary: your@email.com
    phone_e164: "+1XXXXXXXXXX"
    country_code: CA
    location:
      city: Your City
      province_state: Your Province/State
      country: Your Country
  links:
    linkedin: https://linkedin.com/in/your-profile
    github: https://github.com/your-handle
    portfolio: https://your-site.com

work_authorization:
  canada:
    authorized_to_work: true
    requires_sponsorship_now: false
    requires_sponsorship_future: false
  united_states:
    authorized_to_work: false
    requires_sponsorship_now: true
    requires_sponsorship_future: true

document_paths:
  resume_basename: My_Resume
  resume_primary: ./My_Resume.pdf
  cover_letter_master: ./cover-letter-playbook.md
  additional_documents: []
  path_convention: relative_to_repo_root

application_defaults:
  notice_period: immediate
  willing_to_relocate: true
  willing_background_check: true
  autofill_policy: maximize_autofill_with_pre_submit_review

education_defaults:
  highest_level_currently_pursuing: bachelors_degree
  major: YOUR MAJOR
  graduation_year: 202X
  enrolled_in_official_coop_program: false

experience_defaults:
  previous_internships_completed: 0

skills:
  skills_normalized:
    - JavaScript
    - TypeScript
    - React
    - Node.js
  skills_format_version: normalized_list_v1

agent_instructions:
  behavioral_rules:
    - Do not fabricate experience, titles, dates, or metrics.
    - Ask when required fields are missing.
  validation_constraints:
    phone_format: E.164
    birth_date_format: ISO-8601
    boolean_values: true_or_false_only
    paths: relative_only
