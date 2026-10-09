# Skill Wizard

Single-file browser tool that walks you through building a **model-portable `SKILL.md`**: plain Markdown with YAML frontmatter, no platform hooks, readable by any LLM.

## Use it

Open `skill-wizard.html` in a browser. No build step, no dependencies, no server.

1. **Identify**: name, one-sentence overview, description
2. **Triggers**: phrases that should activate the skill
3. **Steps**: imperative execution steps
4. **Guardrails**: checks and failure modes
5. **Assemble**: live preview, portability lint, copy or download

Exports: `SKILL.md` (copy or download) or a plain system prompt with no frontmatter.

## Model assist

Each step has an optional button that drafts or refines content with a model. Pick the engine under **Engine** at the top:

| Engine | Where it works |
| --- | --- |
| Claude, built in | Only while the page is open inside Claude |
| OpenAI-compatible endpoint | OpenAI, OpenRouter, DeepSeek, or local Ollama / LM Studio / llama.cpp |
| Anthropic API with your key | Opened from disk |
| Off | Everywhere, fully offline |

Local servers need CORS enabled and work when the file is opened from disk. API keys live in page memory only; nothing is stored, and a refresh clears the form.

## Portability lint

Heuristic checks, no model needed: 500-line cap, slug-clean name, description and trigger phrases present, vendor or tool names flagged (`claude`, `bash_tool`, `/mnt/`, and similar), imperative voice in steps. Treat results as hints, not proof.

## Layout

```
skill-wizard.html                 the tool
examples/model-portable-skill/    reference template the output follows
```
