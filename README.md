# Editorial Workflow

> A repeatable editorial system for people who want AI help without giving up authorship.

Editorial Workflow turns a rough idea into an evidence-backed, publication-ready article package. It separates research, voice, structure, drafting, review, and revision so the final piece is accurate, useful, and recognizably yours.

It works for articles, essays, technical guides, project stories, comparisons, case studies, opinions, and timely analysis.

## Why use it?

- **Evidence before prose:** Material claims are tracked in a source ledger before they reach the final copy.
- **Author voice as source material:** The workflow learns from approved author-written work, not generic generated drafts.
- **Real editorial stages:** Brief, angle, and outline approvals prevent expensive rewrites later.
- **Independent review:** Specialist reviewers check facts, technical accuracy, reader value, voice, reasoning, and search intent.
- **No automatic publishing:** The workflow stops at a publication-ready package unless the user separately authorizes an external action.

## How it works

```mermaid
flowchart LR
    A["Brief"] --> B["Research and voice"]
    B --> C["Angle"]
    C --> D["Outline"]
    D --> E["Draft"]
    E --> F["Independent reviews"]
    F --> G["Revision and package"]
```

The approval gates are intentional. Standard and cornerstone articles do not move from brief to research, angle to outline, or outline to draft until the direction is clear.

## Installation

Clone this repository and install all seven folders under `skills/`. Each folder is a separate Agent Skill, so do not copy only the coordinator.

### Where to put the skills

| Runtime and scope | Put the skill folders here |
|---|---|
| Codex, personal | `$CODEX_HOME/skills/` or `~/.codex/skills/` when `CODEX_HOME` is unset |
| Codex, one project | `<project>/.agents/skills/` |
| Claude Code, personal skills only | `~/.claude/skills/` |
| Claude Code, one project, skills only | `<project>/.claude/skills/` |
| Claude Code, full plugin | `~/.claude/skills/editorial-workflow/` |
| Other Agent Skills clients | The client-specific Agent Skills directory |

The destination directory should contain the seven member folders, such as `editorial-workflow/`, `editorial-fact-reviewer/`, and `editorial-voice-reviewer/`.

### Codex

Clone the repository anywhere, then copy all seven skills into your personal Codex skills directory:

```bash
git clone https://github.com/bradtraversy/editorial-workflow-skill.git
cd editorial-workflow-skill
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/. "${CODEX_HOME:-$HOME/.codex}/skills/"
```

For a project-only installation, copy them into that project's `.agents/skills/` directory instead:

```bash
mkdir -p /path/to/project/.agents/skills
cp -R skills/. /path/to/project/.agents/skills/
```

Restart Codex after installation so it discovers the skills.

### Claude Code with reviewer agents

Clone the full repository into Claude's personal skills directory. This preserves the plugin manifest, coordinator, reviewer skills, and six read-only reviewer agents:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/bradtraversy/editorial-workflow-skill.git ~/.claude/skills/editorial-workflow
```

Restart Claude Code or run `/reload-plugins` after installation.

To test a clone from any other location without installing it there, run:

```bash
claude --plugin-dir /path/to/editorial-workflow-skill
```

### Claude Code skills only

If you do not need the custom reviewer agents, copy the seven portable skills into Claude's personal or project skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R skills/. ~/.claude/skills/
```

Use `/path/to/project/.claude/skills/` instead for a project-only installation.

### Other Agent Skills clients

Clone the repository and copy every folder under `skills/` into the Agent Skills directory used by your client. The seven `SKILL.md` files and their bundled references and assets are the portable layer. The root `agents/` directory and `.claude-plugin/` manifest are Claude-specific and can be ignored by other clients.

## Quick start

After installing the skills and restarting your client, natural language works in any runtime that can discover Agent Skills:

```text
Use the editorial workflow to develop a practical article about debugging AI-generated code.
```

### Codex

```text
Use $editorial-workflow to develop a comparison of server-rendered and client-rendered authentication.
```

Run a specialist reviewer directly when needed:

```text
Use $editorial-technical-reviewer to review the code and instructions in draft.md.
```

### Claude Code plugin

```text
/editorial-workflow:editorial-workflow Develop a project story from my notes about rebuilding a production feature.
```

The Claude plugin also exposes read-only reviewer agents:

```text
@editorial-workflow:editorial-fact-reviewer Review the claims and source support in draft.md.
```

## What it creates

The coordinator creates only the artifacts required by the selected content mode and research depth:

```text
Editorial/Workspaces/YYYY-MM-DD-slug/
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

A standard run produces an approved brief, a source-backed research dossier, an author voice packet, an approved outline, a draft, independent review reports, a revised article, and the packaging needed by the intended destination.

## Included skills and reviewers

| Skill | Responsibility |
|---|---|
| `editorial-workflow` | Coordinates stages, artifacts, approvals, revision, and packaging |
| `editorial-fact-reviewer` | Verifies claims, quotations, sources, freshness, and evidence boundaries |
| `editorial-technical-reviewer` | Checks code, commands, terminology, completeness, security, privacy, and product behavior |
| `editorial-reader-reviewer` | Checks usefulness, structure, clarity, examples, unanswered questions, and reading flow |
| `editorial-voice-reviewer` | Protects the author's sourced voice, perspective, and lived experience |
| `editorial-argument-reviewer` | Checks thesis support, definitions, counterarguments, reasoning, limits, and conclusions |
| `editorial-seo-reviewer` | Checks search intent, titles, headings, metadata, links, originality, and refresh needs |

Claude Code plugin mode exposes the six reviewer roles as custom subagents. Each agent preloads its matching reviewer skill and is blocked from using the Write and Edit tools.

## Runtime support

| Runtime | Installation | Coordinator | Reviewers |
|---|---|---|---|
| Codex | Copy the seven skill folders | `$editorial-workflow` | Reviewer skills with native isolated-agent delegation when available |
| Claude Code | Clone as a plugin or copy the skill folders | `/editorial-workflow:editorial-workflow` in plugin mode | Six namespaced custom subagents plus reviewer skills |
| Other Agent Skills clients | Copy the `skills/` members | Client-specific invocation | Reviewer skills, with isolation determined by the client |

The portable core is each `SKILL.md` with its references and assets. Vendor-specific metadata is additive and can be ignored safely by clients that do not use it.

## Develop locally with Claude Code

Load the repository directly as a plugin:

```bash
claude --plugin-dir .
```

## Editorial principles

- Choose the content mode and evidence depth before research.
- Ground voice in author-owned material, not generated imitation.
- Track material claims in a source ledger.
- Approve the brief, angle, and outline before expensive downstream work.
- Keep drafting and independent review separate.
- Preserve visible input flags when truth depends on the author.
- Keep private evidence paths and editorial decisions out of public copy.

## Boundaries

Editorial Workflow does not invent personal experience, fabricate sources, contact people, deploy changes, publish articles, syndicate content, or edit a live destination automatically.

Missing human material remains visible as `[AUTHOR INPUT NEEDED]`. Unsupported factual material remains visible as `[SOURCE NEEDED]`.

## Validate the pack

Validate the portable Agent Skills and the Claude plugin before release:

```bash
claude plugin validate --strict .
```

## License

MIT
