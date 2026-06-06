# Academic Translation Skill — Philosophy & History of Ideas

A Claude Code skill for translating academic journal articles in humanities and philosophy, with built-in terminology management and style guidance.

## Supported Language Pairs

| Source | Target |
|--------|--------|
| English | Chinese |
| French | Chinese |
| German | Chinese |
| Chinese | English |
| Chinese | French |

## Features

- **Three-pass translation**: faithful draft → terminology audit → register polish
- **Philosophy-specific terminology tables**: Spinoza, Merleau-Ponty, French philosophy (in progress)
- **Footnote & citation preservation**: numbering, bibliographic entries, inline quotes
- **Style consistency**: terms rendered uniformly throughout the text; first-occurrence parenthetical originals
- **术语注记**: translation notes section documenting deliberate terminology choices

## Installation

```bash
git clone https://github.com/yzh1250363348-del/claude-academic-translation.git ~/.claude/skills/academic-translate
```

## Usage

In Claude Code, trigger with:
- `/translate` or `/翻译`
- Paste text and say "帮我翻译这段"
- Provide a PDF path: "translate this PDF → Chinese"

## Terminology Sources

Glossaries are compiled from published academic works and translations. Sources are noted in each glossary file.

- `glossaries/spinoza.md` — Spinoza terminology (EN/FR/DE ↔ ZH)
- `glossaries/merleau-ponty.md` — Merleau-Ponty terminology (in progress)
- `glossaries/french-philosophy.md` — General French philosophy terms (in progress)

## Sync Across Machines

```bash
# After updating glossaries or SKILL.md
git add . && git commit -m "update glossaries" && git push

# On the other machine
git pull
```

## Roadmap

- [ ] Merleau-Ponty glossary
- [ ] French philosophy general glossary
- [ ] Style profile (extracted from reference translations)
- [ ] German philosophy glossary expansion
