---
name: editorial-workflow
description: Develop articles, essays, guides, comparisons, case studies, and timely analysis from intake through research, angle selection, outline, draft, independent review, revision, and publication-ready packaging. Use when an agent needs a rigorous writing workflow that preserves the author's real voice, tracks sources, supports multi-agent reviews, and stops before publication.
---

# Editorial Workflow

Coordinate writing as a staged editorial project. Keep strategy, evidence, voice, drafting, review, revision, and approval visible in durable artifacts.

## Load the contracts

Read these files before substantive work:

- `references/content-modes.md`
- `references/artifact-contracts.md`
- `references/research-contract.md`
- `references/voice-and-quality.md`
- `references/production-contracts.md`
- `references/orchestration.md`

Use the templates under `assets/templates/` when creating a workspace.

## Establish the workspace

Use the workspace supplied by the user. If none exists, create:

```text
Editorial/Workspaces/YYYY-MM-DD-slug/
```

Add a numeric suffix when the path already belongs to a different piece. Never overwrite or silently repurpose another workspace.

Use this standard layout:

```text
status.md
brief.md
research/
  dossier.md
  sources.md
  voice-packet.md
angle.md
outline.md
draft.md
reviews/
  facts.md
  technical.md
  reader.md
  voice.md
  argument.md
  seo.md
revision.md
package.md
performance.md
```

Create only required artifacts. Quick work may combine reviews. Standard and cornerstone work should preserve independent review files.

## Protect truth and privacy

- Treat exact author language, approved notes, and clearly author-written work as voice evidence.
- Treat generated drafts, summaries, and idea lists as factual leads, not voice evidence.
- Never invent experience, motivation, emotion, results, quotations, or a change of mind.
- Mark missing human material as `[AUTHOR INPUT NEEDED]`.
- Mark unsupported factual material as `[SOURCE NEEDED]`.
- Keep private source paths and editorial decisions out of public copy.
- Do not store credentials, private account data, or unrelated sensitive material.
- Do not publish, deploy, send, syndicate, or modify a live destination without separate authorization.

## Select the mode and depth

Choose one primary content mode:

- Search guide
- Project story
- Opinion
- Personal essay
- Comparison
- Timely analysis
- Case study

Use one secondary mode only when it contributes essential evidence or voice. The primary mode controls structure.

Choose quick, standard, or cornerstone research using `references/content-modes.md`. Increase depth for technical, competitive, consequential, commercially important, or long-lived pieces.

## Run the workflow

### 1. Intake and brief

Create `status.md` and `brief.md`.

Capture:

- Intended reader and reader problem
- Desired reader outcome and action
- Goal and publishing destination
- Author's connection and available firsthand material
- Unique value
- Search importance
- Freshness and factual risk
- Scope, boundaries, and known sources
- Open questions

Ask only questions that change truth, angle, audience, or destination. Record reasonable assumptions explicitly.

For standard or cornerstone work, stop for brief approval before broad research.

### 2. Voice and research

Create `research/voice-packet.md` from two to four relevant author-owned sources. Record observations and short phrases, not large copied passages.

Run only the tracks required by the brief:

- Search and intent
- Primary and authoritative sources
- Audience and community
- Firsthand experience
- Technical investigation
- Counterarguments

Parallelize independent tracks when isolated agents are available. Give each track a narrow question and one output contract. Otherwise, run clearly separated role passes.

Synthesize the work into `research/dossier.md` and `research/sources.md`. Assign stable claim IDs such as `C-01` to every material fact, quotation, firsthand account, test observation, inference, or recommendation.

### 3. Angle gate

Create `angle.md` with three to five evidence-supported directions when the angle is not already explicit.

For each option record:

- Thesis or central angle
- Reader value
- Author-specific advantage
- Evidence strength
- Strongest counterargument
- Risks and unsupported claims

Recommend one direction without pretending the choice is automatic. Stop for angle approval before outlining when the direction materially changes the piece.

### 4. Outline gate

Create `outline.md`. Give every section:

- Heading concept
- Reader question
- Purpose
- Required claim IDs
- Firsthand material
- Example or demonstration
- Visual opportunity
- Link or call-to-action opportunity
- Transition logic

Lead with useful substance, preserve the approved angle, and remove sections that do not earn their place.

Stop for outline approval before drafting unless the user explicitly requested a lightweight pass.

### 5. Draft

Write `draft.md` as one coherent piece.

- Keep claims within the evidence.
- Preserve uncertainty and meaningful complications.
- Use concrete examples before broad lessons.
- Do not introduce a new thesis silently.
- Keep author input and source flags visible.
- Apply destination constraints without exposing private source paths.
- Keep calls to action useful and proportional.

Do not include the private claim ledger or editorial decision log in public copy.

### 6. Independent reviews

For standard work, select the relevant isolated reviewer skills:

- `$editorial-fact-reviewer`
- `$editorial-technical-reviewer` when code, commands, security, or product behavior matters
- `$editorial-reader-reviewer`
- `$editorial-voice-reviewer`
- `$editorial-argument-reviewer` for opinion, analysis, comparison, and recommendation
- `$editorial-seo-reviewer` when search discovery matters

In Claude Code plugin mode, delegate each review to the matching custom agent bundled in the plugin. Each agent preloads its reviewer skill and is blocked from using the Write and Edit tools. In other runtimes, use a native isolated agent with the matching reviewer skill when available.

Reviewers receive the draft and only the evidence needed for their role. They report findings in separate files and do not rewrite the draft. Do not reveal the desired review conclusion.

If isolated agents are unavailable, complete the draft, clear drafting assumptions from the active summary, then run separate role passes. State that reviewer independence was limited.

### 7. Revision

Group duplicate findings and resolve critical and high findings first. Compare conflicting recommendations with the brief, approved angle, evidence, and voice packet.

Write `revision.md` without overwriting `draft.md`. For additional material revisions, use numbered filenames.

Keep a private decision log after the revised copy or in a separate note:

- Accepted findings
- Rejected findings and reasons
- Deferred findings
- Remaining questions
- Claims still requiring verification

The decision log is not public copy.

### 8. Packaging

Create `package.md` only after the recommended revision is clear. Include only assets requested by the brief and destination:

- Recommended title and alternatives
- Slug
- Meta title and description
- Visual brief
- Screenshots, diagrams, or code assets
- Internal and external links
- Calls to action
- Social copy
- Canonical destination
- Syndication notes
- Refresh plan

Set the status to `ready-for-publication-decision`. Do not publish or transmit anything.

### 9. Performance planning

Create `performance.md` only when a published URL and real analytics are available. Evaluate the piece against the stated reader and business goal. Recommend changes, but do not modify live content automatically.

## Status lifecycle

Use one state in `status.md`:

- `intake`
- `awaiting-brief-approval`
- `researching`
- `awaiting-angle-approval`
- `outlining`
- `awaiting-outline-approval`
- `drafting`
- `reviewing`
- `revising`
- `awaiting-final-approval`
- `packaging`
- `ready-for-publication-decision`
- `published`
- `monitoring`
- `paused`
- `blocked`

Record the current owner, last completed stage, next action, approvals, blockers, and artifact inventory whenever the state changes.

## Completion standard

A piece is ready for a final publication decision when:

- The brief and angle are documented.
- Required research is complete.
- Material claims are supported or visibly flagged.
- The draft and required reviews are complete at the selected depth.
- Critical and high findings are resolved or explicitly accepted.
- The author's real viewpoint and firsthand value remain intact.
- The recommended final copy is clearly identified.
- Packaging is complete when requested.
- No external action has been taken without authorization.
