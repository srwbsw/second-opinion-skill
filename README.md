# opencode-skill

**A Claude Code plugin that brings opencode into your AI coding workflow as a second-opinion reviewer — with your choice of model.**

opencode gives you access to GPT, Gemini, Llama, Mistral, and 50+ other models in a single CLI. This plugin lets you tap any of them for an independent code review without leaving your Claude Code session. Different models have different training, different blind spots, and different strengths — using one to review another's work is the same instinct as a second engineer reading your PR.

## What it does

Adds an `opencode-review` skill to Claude Code. When invoked, it asks you to pick a model from the opencode registry, then pipes your code, diff, or question to that model and shows the structured review inline.

opencode always runs with `--agent plan` — the plan agent enforces `"edit": "deny"` at the permission level, making file writes structurally impossible. This is a review-only tool.

## Use cases

- **Code review** — pipe a `git diff` or file to GPT, Gemini, or any opencode model for a senior-engineer-style critique
- **Second opinion** — get an independent take on an architectural or design decision from a differently-trained model
- **Security review** — scan for injection, auth flaws, data exposure, and input validation issues
- **General consultation** — ask any technical question and get a structured answer

## Requirements

- [opencode](https://opencode.ai) installed (`opencode -h` should work)
- [Claude Code](https://claude.ai/code) (CLI, desktop app, or IDE extension)

## Installation

```bash
/plugin marketplace add srwbsw/opencode-skill
/plugin install opencode-skill@opencode-skill
```

## Usage

> "Use opencode to review this"
> "Ask opencode what it thinks about this approach"
> "Get opencode's opinion on this diff"
> "Review with GPT"

When invoked, the skill shows a model picker defaulting to free `opencode/*` models (purpose-built, no API key needed). You can also choose any model from the full opencode registry — GPT-4o, Gemini 2.5 Pro, Llama 4, and more.

Results appear under a `## Opencode's Take (<model>)` heading with structured sections: Summary, Issues (with HIGH/MED/LOW severity), Concerns, and Positives.

## Why cross-model review?

No single AI model catches everything. Claude reasons well through complex logic but has its own blind spots. Running your changes through GPT or Llama before declaring done is the same instinct as a second engineer reading your PR — except it takes seconds, not hours.

This plugin automates that second read with zero friction, and lets you pick which model does the reviewing based on what you're trying to catch.

## Related

- [gemini-cli-skill](https://github.com/srwbsw/gemini-cli-skill) — same concept but dedicated to Gemini CLI, with tighter Gemini-specific integration

## License

MIT
