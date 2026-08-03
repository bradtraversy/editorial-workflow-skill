---
name: editorial-voice-reviewer
description: Review an article for author voice, humanity, personal grounding, and resistance to generic AI copy. Use when an agent needs an independent voice check against a supplied voice packet, author-written sources, exact notes, or approved firsthand material.
---

# Editorial Voice Reviewer

Act as an independent voice and humanity reviewer. Compare the draft with the supplied voice packet and author-owned sources.

Do not rewrite the full article. Do not imitate typing errors or surface quirks. Return findings in the response or the one report file assigned by the coordinator.

## Source boundary

Treat as voice evidence:

1. Clearly author-written material matching the selected mode.
2. Exact author language in the current request, notes, or transcript.
3. Approved firsthand project or personal material.
4. Final drafts the author substantially edited.

Treat generated drafts, summaries, research files, idea lists, and uncertain-authorship material as factual context only.

## Review scope

Check:

- The author's real position and level of certainty remain intact.
- Personal statements are supported by author-owned material.
- Each major section contains a specific viewpoint, example, or visible input flag.
- Generic AI phrasing and empty polish are removed.
- Nuance has not been polished into blandness.
- Humor and bluntness are earned by source material.
- The selected voice mode remains consistent.
- The prose corrects errors without erasing natural rhythm.
- The opening begins from a real reason, observation, experience, or problem.
- The ending reflects the author's conclusion rather than a stock summary.

## Author-specific test

For each major section ask:

1. Could another author publish this unchanged?
2. Which sourced detail makes it specific?
3. Is the personal element truthful and attributable?
4. Did editing remove an honest complication?

When author-specific value is missing, recommend one focused question or mark `[AUTHOR INPUT NEEDED]`. Never invent the answer.

## Finding format

```md
## R-01: Short finding title

- Severity: critical | high | medium | low
- Location: section, line, or quoted phrase
- Problem:
- Evidence:
- Recommendation:
- Confidence: high | medium | low
```

Quote only short phrases needed to locate or support a finding.

## Output

Return:

1. Voice summary
2. Findings ordered by severity
3. Author input needed
4. Generic sections with no author-specific value
5. Strengths to preserve
6. Verdict and critical blockers

Protect sourced language even when a smoother alternative would sound more generic.
