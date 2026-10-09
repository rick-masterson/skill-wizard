---
name: model-portable-skill
description: Universal, model-agnostic instructions and structured frameworks that work reliably across different LLMs (such as Claude, GPT, and open-weight models). Use when creating portable workflows, prompts, or agents.
---

# Portable Skill Framework

A portable skillset is designed to run consistently across any capable language model (such as Anthropic Claude, OpenAI GPT, or local open-source models like DeepSeek or Llama).

## Core Design Principles for Portability

1. Explicit YAML Frontmatter: Always start with clear `name` and `description` fields. This acts as the universal router for all agent runtimes.
2. Standard Markdown Structure: Avoid proprietary syntax features. Use standard Markdown headings (`#`, `##`), lists, and clear text blocks.
3. Structured Constraints (Low/Medium/High Freedom):
   * Define exact steps for rigid processes.
   * Use high-level heuristics or goals for creative tasks.
4. Resilient Prompts: Provide a concise template or checklist that any model can parse without relying on platform-specific tool definitions.

## Universal Skill Template

Copy and adapt this structure for any new portable skill:

```markdown
---
name: your-skill-name
description: Clear summary of what this skill does and when the model should activate it. Include specific trigger phrases.
---

# [Skill Title]

## Overview
A single sentence describing the core objective.

## Trigger Scenarios
- Situation A
- User phrase B

## Execution Steps
1. **Analyze input:** Inspect the request against constraints.
2. **Execute workflow:** Follow the deterministic steps or heuristic guidelines.
3. **Format output:** Deliver the results in the requested format.

## Guardrails & Gotchas
- Avoid assumption errors by validating required fields.
- Keep output concise and actionable.
```

## Best Practices

* Keep instructions under 500 lines to fit comfortably into any model's attention window.
* Use imperative language ("Extract data", "Calculate totals") rather than passive voice.
* Include zero platform dependencies so the file can be dropped directly into any markdown-reading agent architecture.
