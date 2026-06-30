1. Accelerating Requirements Gathering
## Extract requirements from workshop notes:
**Persona:** Acting in the role of a Business Central Functional Consultant.
**Context:** Having just completed a customer requirements workshop and received rough notes (bullet points, partial sentences, and notes) that need turning into implementable requirements for the BC team.
**Scope:** Base your output only on the notes provided. Do not invent requirements. Where the notes are unclear, flag it as an open question. Keep requirements specific to Business Central behaviour (posting, dimensions, approvals, audit trail).
**Instructions:**
“Summarise the workshop notes in this file into structured Business Central functional requirements.
- Group them into: General Ledger, Dimensions, VAT, Approvals.
- For each requirement, write it in a testable format: *‘When… then…’* or *‘Given… when… then…’*.
- Add a short ‘Business Central interpretation’ line where needed (e.g., what posting event or document is impacted).
- Produce an Open Questions section for anything ambiguous or missing.”

## Clarify vague requirements:
**Persona:** Acting in the role of a Business Central Functional Consultant responsible for writing the functional spec.
**Context:** Having reviewed drafted requirements and noticing they’re full of terms like “should”, “as needed”, “handle correctly”, and “fast”, which will cause rework later.
**Scope:** Rewrite using standard Microsoft-documented Business Central concepts (documents, posting, approval workflows, dimensions, posting groups). Do not propose custom development unless the requirement explicitly demands it; instead, identify what would be standard vs. unclear.
**Instructions:**
“Rewrite the requirements in <this file> so they are:
- Clear
- Testable
- Specific to Business Central behaviour (posting, dimensions, approvals).
- Replace vague language with measurable outcomes.
- Highlight any requirement that still cannot be made testable (and explain why).
- For each rewritten requirement, add a ‘What to confirm in workshop’ question.”

## Detect gaps and assumptions:
**Persona:** Acting in the role of a BC Solution Architect running a requirements validation checkpoint with the team.
**Context:** The team is about to start solution design and you want to avoid later surprises (edge cases, exceptions, roles, controls).
**Scope:** Use only the requirement text given. Do not guess customer policy; instead, list assumptions explicitly.
**Instructions:**
“Based on the requirements in <this file>, produce a ‘Gaps & Assumptions Review’ with:
- Missing scenarios (exceptions, reversals, cancellations, partial receipts/invoices, credit memos).
- Missing actors/roles (who approves, who posts, who can override).
- Missing data needs (dimensions, VAT rates, posting groups, document capture inputs).
- Assumptions you think the team is implicitly making.
- A prioritised list of unanswered questions that could impact delivery.”

## Check for functional completeness in the context of BC:
**Persona:** Acting in the role of a Business Central Functional Solution Architect specialising in project-centric purchasing.
**Context:** You’ve drafted requirements for purchase orders linked to jobs/projects and subcontractors, and you need to sanity-check whether they fully describe the intended process.
**Scope:** Evaluate completeness only against standard Business Central behaviours for purchase order → receipt → invoice posting, and standard project/job linkage concepts. If something depends on add-ons or customisations, flag it as “out of standard scope”.
**Instructions:**
“Do these requirements fully describe how purchase orders should behave when used in the context of jobs/projects and subcontractor vendors in Business Central?
- Identify what’s missing across: setup prerequisites, document lifecycle, posting impacts, dimensions, VAT, approvals, and reporting outcomes.
- List the top 10 clarifying questions to ask the customer before design starts.”

2. Improving Analysis & Understanding
## Process simplification:
**Persona:** Acting in the role of a BC Functional Lead preparing a playback session for mixed business/IT stakeholders.
**Context:** You need to explain the end-to-end process simply, to confirm shared understanding before solution design.
**Scope:** Use plain business language. Don’t introduce extra steps that are not present in the described process; if gaps exist, label them as gaps.
**Instructions:**
“Summarise this end-to-end Procure to Pay process in Business Central in no more than 8 steps, using plain business language.
- For each step, include: key role, key document, and what ‘done’ means.
- Add a short section called ‘Where errors typically happen’ based on what is described.”

## Consistency analysis:
**Persona:** Acting in the role of a BC Solution Architect reviewing the requirements in <this file> before sign-off.
**Context:** Requirements were written by multiple people; you suspect contradictions that will cause build/test churn.
**Scope:** Only analyse the given text. Don’t “fix” by inventing new policy. Identify conflicts and the decision needed.
**Instructions:**
“Analyse these requirements and identify conflicts or inconsistencies, specifically in:
- Posting rules (when/where posting occurs, what triggers posting)
- Dimensions (which are mandatory, defaulting rules, overrides)
- Approval rules (who approves what, thresholds, delegation)
For each conflict, quote the conflicting statements and suggest the decision question to resolve it.”

## Risk-focused analysis:
**Persona:** Acting in the role of a BC Project Manager partnering with the Functional Lead.
**Context:** You’re preparing a delivery plan and want to analyse risk based on the requirement set.
**Scope:** Categorise risks only using what is implied by the requirements; don’t assume technical constraints beyond standard BC unless indicated.
**Instructions:**
“Based on these requirements, identify the main delivery risks for a Business Central project.
Group risks into: customisation, data quality, user adoption, performance, and testing complexity.
For each risk: explain why it’s a risk, early warning signs, and one mitigation action we can take during analysis/design.”

## Implicit requirement discovery:
**Persona:** Acting in the role of a BC Functional Consultant who’s been burned by ‘that’s what we assumed!’ moments.
**Context:** The requirements read “complete” but feel like they’re missing unwritten expectations around controls, reporting, and responsibilities.
**Scope:** Only infer implicit requirements that are strongly suggested by the text; label each as “implicit” and explain what triggered it.
**Instructions:**
“What implicit requirements or expectations are suggested here but not explicitly stated?
For each implicit item:
- What wording suggests it
- Why it matters in Business Central terms (posting, audit trail, approvals, reporting)
- The exact question we should ask the customer to confirm it.”
3. Faster & Better Solution Design
## Challenging the design:
**Persona:** Acting in the role of a BC Functional Solution Architect doing a design review.
**Context:** A consultant has proposed a design and you want to stress-test it before it becomes “the plan”.
**Scope:** Evaluate against standard Business Central behaviour first. If the design relies on non-standard behaviour, explicitly call that out as an assumption.
**Instructions:**
“Challenge this proposed solution design.
- List the assumptions it makes about standard Business Central behaviour (posting, approvals, dimensions, VAT, job/project integration).
- For each assumption, explain where it might fail (edge cases, permissions, partial processes, volume).
- Provide a ‘Questions to validate with customer’ list.”

## Alternative approaches:
**Persona:** Acting in the role of a BC Solution Architect responsible for balancing fit-to-standard with business value.
**Context:** Stakeholders are pushing for customisation; you want structured options for a design decision meeting.
**Scope:** Base the options on standard BC capabilities first; keep “light extension” conceptual (no code).
**Instructions:**
“Suggest three alternative ways to handle this requirement in Business Central:
1. Standard configuration
2. Light extension
3. Process change.
For each option, list the following aspects: pros, cons, delivery risk, user impact, and likely supportability impact.
Finish with a recommendation framework: what facts would make us choose each option?”

## Customisation pressure test:
**Persona:** Acting in the role of a BC Functional Lead accountable for keeping the solution maintainable.
**Context:** A requirement is being labelled “customisation required” without enough evidence.
**Scope:** Only use standard BC features/configuration as your baseline. If unsure, output “needs confirmation” rather than guessing.
**Instructions:**
“Does this solution truly require custom development, or could it be achieved using standard Business Central features or configuration?
- List which parts appear achievable in standard BC and how (feature/category level).
- List what would force customisation (and what requirement wording indicates that).
- Provide the minimum evidence needed to justify development.”

## Scenario simulation:
**Persona:** Acting in the role of a BC Solution Architect preparing for a steering committee design checkpoint.
**Context:** You want to anticipate future constraints before go-live decisions lock in.
**Scope:** Keep simulation at a functional/operational level; don’t invent technical limits.
**Instructions:**
“How would this design behave if:
- Transaction volumes doubled
- Approval hierarchies became more complex
- Multiple companies were added later
For each scenario: describe the likely functional impact, where processes could break down, and what design adjustment could improve resilience.”
4. Improving Breadth & Speed of Testing
## Test case generation:
**Persona:** Acting in the role of a BC Test Lead supporting UAT readiness.
**Context:** Requirements are approved and you need a first draft of test coverage quickly.
**Scope:** Use only the requirement text in this file. Produce tests that reflect standard BC document lifecycles and posting outcomes.
**Instructions:**
“Generate functional test cases for these Business Central requirements. For each test case include:
- Preconditions / setup
- Test data
- Steps
- Expected results (including posting outcomes, ledger impacts, dimensions, approvals)
- Variations (at least 2)
Also add a ‘Coverage Map’ that shows which requirements are covered by which test cases.”

## Negative testing:
**Persona:** Acting in the role of a BC Functional Consultant who wants to test beyond happy paths.
**Context:** Posting routines often fail under partial receipts, mismatched amounts, missing dimensions, or approval constraints.
**Scope:** Suggest edge cases that are plausible in standard BC; don’t assume custom validations unless stated.
**Instructions:**
“Suggest negative and edge-case test scenarios for this posting process in Business Central.
Group them into: data issues, setup issues, permission issues, workflow/approval issues, and process timing issues.
For each scenario: expected error/behaviour, and what a ‘correct resolution’ looks like.”

## Role-based testing:
**Persona:** Acting in the role of a BC UAT coordinator preparing scripts for different business roles.
**Context:** UAT participants need role-specific scripts that reflect what they actually do day-to-day.
**Scope:** Keep steps aligned to standard BC responsibilities; don’t assume people have elevated permissions unless stated.
**Instructions:**
“Create UAT scenarios from these requirements for the following roles: Warehouse Manager, Accounts Payable, Project Accountant.
For each role: provide 5–8 scenarios, written in business language, including what success looks like and what evidence/screenshots to capture.”

## Regression awareness:
**Persona:** Acting in the role of a BC Functional Lead planning regression coverage for a change set.
**Context:** You’re adding changes and want to anticipate which adjacent processes must be retested.
**Scope:** Use standard BC process adjacency (posting routines, approvals, dimensions, VAT, reporting).
**Instructions:**
“Which existing Business Central processes are most at risk of regression based on these changes?
List the top impacted process areas and explain the linkage (why the change could affect it).
Then propose a minimal regression test pack with priorities.”
5. AI-Supported Documentation
## User Guide creation:
**Persona:** Acting in the role of a Technical Writer tasked with delivering end-user documentation for the customer solutions our company implements.
**Context:** Requirements are agreed, to-be process is fully defined, and a functional specification is agreed.
**Scope:** Use only the following files provided: <Requirements List>, <Functional Spec>.
**Instructions:**
“Create a Business Central User Guide for the solution described in the spec, which meets the listed requirements. You can derive the target user audience roles from the functional spec. Sections required in the document are:
- Introduction (subject, purpose, scope, how the doc is organised)
- Prerequisites
- Process overview (end-to-end, high-level)
- Work instructions (clearly stating which user role each instruction is relevant for).

## Audience-specific rewriting:
**Persona:** Acting in the role of a BC consultant handing over from implementation to support/training.
**Context:** The same design must be reused for training and for internal handover, but those audiences need different language.
**Scope:** Keep facts identical; only change phrasing, structure, and emphasis.
**Instructions:**
“Rewrite this functional design as:
a) End-user training material (simple language, step-by-step tasks, ‘what to do’)
b) Consultant handover documentation (setup notes, dependencies, risks, things to watch)
Ensure both versions remain consistent with the same underlying process and rules.”

## Standardisation:
**Persona:** Acting in the role of a BC Functional Lead responsible for consistent deliverables.
**Context:** Multiple consultants contributed content; terminology is inconsistent and confusing.
**Scope:** Standardise to common Business Central naming conventions; don’t change meaning.
**Instructions:**
“Rewrite this document so it follows a consistent structure and terminology aligned with standard Business Central language.
- Replace inconsistent terms with consistent ones (create a mini glossary of replacements).
- Keep meaning unchanged.
- Flag any term where you cannot confidently standardise without confirmation.”

## Living documentation:
**Persona:** Acting in the role of a BC consultant preparing aftercare/support transition.
**Context:** Support teams need a concise reference to resolve common issues and understand intended behaviour quickly.
**Scope:** Summarise only what is present. Emphasise “how it should work” and “how to troubleshoot” at a functional level.
**Instructions:**
“Summarise this document into a one-page ‘Quick Reference’ for future support teams including:
- What the process is meant to achieve
- Key rules (approvals, posting, dimensions, VAT)
- Common failure points
- What to check first (setup/data/permissions)
- Escalation criteria (when it’s likely a defect vs data/setup)”
6. Assisting with Issue Triage and RCA
## Summarise an issue:
**Persona:** Acting in the role of a BC escalation consultant joining an issue mid-stream.
**Context:** You’ve been forwarded a long Teams thread and need a clean, factual snapshot fast.
**Scope:** Use only the content provided; distinguish confirmed facts vs speculation.
**Instructions:**
“Summarise this Teams thread into:
- Problem statement (one paragraph)
- Business impact
- Timeline of key events/decisions
- Current status
- What’s been tried (and outcomes)
Label any unverified hypotheses clearly as ‘unconfirmed’.”

## Root cause hypothesis:
**Persona:** Acting in the role of a BC Functional Lead running a structured RCA.
**Context:** Symptoms are known but cause is unclear; you need a disciplined hypothesis list to guide investigation.
**Scope:** Propose causes only within these categories: data, setup, customisation/extensions, process, permissions. Don’t assume code defects without evidence.
**Instructions:**
“Based on this issue description, list the most likely root causes in a Business Central context, grouped into:
- Data
- Setup
- Customisation/extensions
- Process
- Permissions
For each hypothesis: evidence that would support it, evidence that would disprove it, and the first check to perform.”

## Change correlation:
**Persona:** Acting in the role of a BC consultant preparing an incident timeline for stakeholders.
**Context:** The issue “suddenly started” and you suspect a recent change triggered it.
**Scope:** Only use described changes; don’t invent changes. Output a checklist of what change history to review.
**Instructions:**
“What recent changes (configuration, extensions, data migration, permissions) could plausibly explain this issue?
- Provide a ranked list of change types to investigate first, and why.
- Suggest the key questions to ask the team (what changed, when, who approved, what environment).
- Produce a simple timeline template we can fill in.”

## Preventative actions:
**Persona:** Acting in the role of a BC Delivery Lead focused on continuous improvement.
**Context:** The incident is resolved (or nearly), and you want to prevent repeats across customers/projects.
**Scope:** Suggest preventative actions across process, training, testing, monitoring, and governance.
**Instructions:**
“Suggest preventative actions to reduce the likelihood of this issue recurring in future Business Central projects.
Group suggestions into:
- Requirements/design
- Configuration governance
- Testing/regression
- Training/adoption
- Operational monitoring.
For each: expected effort, expected impact, and who should own it.”