# Artifact Contracts

Use these rules to create, resume, and validate an editorial workspace.

## Workspace path

Use:

```text
Editorial/Workspaces/YYYY-MM-DD-slug/
```

Add a numeric suffix when the path already exists. Never overwrite or silently reuse a workspace for another piece.

## Structure

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

Only create required artifacts. Quick work may use one combined review file. Standard and cornerstone work should keep independent reviews separate.

## Artifact ownership

| Artifact | Role | Required input |
|---|---|---|
| `status.md` | Managing editor | Current workspace state |
| `brief.md` | Content strategist | User request and approved assumptions |
| `research/dossier.md` | Research synthesizer | Completed research tracks |
| `research/sources.md` | Research team | Claim and source records |
| `research/voice-packet.md` | Voice researcher | Approved author-owned sources |
| `angle.md` | Research synthesizer and user | Dossier and angle decision |
| `outline.md` | Outline architect | Approved angle and evidence |
| `draft.md` | Writer | Approved outline |
| `reviews/*.md` | Named independent reviewer | Draft and relevant evidence |
| `revision.md` | Revision editor | Draft and reviews |
| `package.md` | Packaging role | Approved revision and destination |
| `performance.md` | Performance role | Published URL and observed data |

One role must not modify another role's artifact. Add new conclusions to the current role's artifact or a clearly marked amendment.

## File rules

- Use Markdown.
- Use workspace-relative paths for local evidence.
- Use direct URLs for web sources.
- Use stable IDs for claims and findings.
- Include dates for current facts and approvals.
- Never overwrite earlier draft or revision evidence.
- Keep private decision logs outside public copy.
- Do not include hidden reasoning or chain of thought.
- Do not store credentials, secrets, private account data, or unrelated sensitive context.
- Delete unused template sections rather than leaving empty headings in a completed artifact.

## Completion rules

A piece is ready for a publication decision when:

- Brief and angle are documented.
- Required research is complete.
- Material claims are supported or visibly flagged.
- Draft and required reviews are complete.
- Critical and high findings are resolved or explicitly accepted.
- Public-safety review is complete.
- Recommended final copy is clearly identified.
- Packaging is complete when requested.
- No publication action has occurred without authorization.
