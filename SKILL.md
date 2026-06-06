# Academic Translation — Philosophy & History of Ideas

## Trigger

Use this skill when the user asks to translate an academic text, journal article, or passage. Activate on:
- `/translate` or `/翻译`
- Phrases like "translate this", "帮我翻译", "translate into Chinese/English/French"
- User pastes a foreign-language text and asks for translation
- User provides a PDF path and asks for translation

## Supported Language Pairs

- English → Chinese (中文)
- French → Chinese (中文)
- German → Chinese (中文)
- Chinese → English
- Chinese → French

Auto-detect the source language unless the user specifies otherwise. If the target language is ambiguous, ask. If the user writes `/translate en→zh`, respect that explicitly.

## Input Handling

**Pasted text**: Translate directly.

**PDF file path**: Use the Read tool to extract the text from the PDF, then translate. Preserve the document's section structure (abstract, body, footnotes, bibliography).

## Translation Workflow

Execute three passes internally. Only show the user the final output unless they ask to see intermediate steps.

### Pass 1 — Faithful Draft
Translate closely and literally. Preserve sentence structure where possible. The goal is accuracy, not fluency.

### Pass 2 — Terminology Audit
Review the draft for:
- Philosophical proper nouns and technical terms (see glossary guidance below)
- Latin phrases (render with Chinese gloss + keep Latin in parentheses)
- Author-specific coined terms (keep original in parentheses on first occurrence)
- Proper names of philosophers, scholars, institutions (transliterate consistently)
- Citations, footnote markers, and bibliographic references (preserve numbering exactly)

### Pass 3 — Register Polish
Rewrite the draft in the appropriate academic register:
- **→ Chinese**: Use standard Mainland scholarly Chinese (规范学术汉语). Avoid colloquialisms. Mirror the source text's sentence weight — a dense Hegelian paragraph should remain dense, not be simplified.
- **→ English**: Use formal academic English appropriate for anglophone philosophy journals (e.g., *Mind*, *Philosophical Review*, *Journal of the History of Philosophy*). Avoid contractions.
- **→ French**: Use formal academic French appropriate for francophone philosophy journals (e.g., *Revue de métaphysique et de morale*, *Philosophie*). Use appropriate subjunctive and stylistic register.

## Philosophical Terminology Guidance

### General rules
- **Preserve ambiguity in the source**: do not resolve a term that the author leaves deliberately vague.
- **Consistency**: use the same Chinese/French/English rendering for each term throughout the entire translated text. If you change a rendering mid-text, note it.
- **First occurrence**: for any key technical term, include the original in parentheses: 实体（substance）.

### Common philosophy terms (EN→ZH defaults — adjust per author's tradition)
| Original | Default ZH rendering | Notes |
|---|---|---|
| substance | 实体 | Spinoza context |
| attribute | 属性 | Spinoza context |
| mode | 样式 | Spinoza context |
| conatus | 努力/冲力（conatus） | keep Latin |
| affect / affection | 情动 / 情感 | distinguish carefully |
| essence | 本质 |  |
| existence | 存在 |  |
| being | 存在 / 在者 | distinguish Sein/Seiendes if Heidegger |
| representation | 表象 |  |
| consciousness | 意识 |  |
| subject / subjectivity | 主体 / 主体性 |  |
| object | 客体 / 对象 | context-dependent |
| dialectic | 辩证法 |  |
| immanence | 内在性 |  |
| transcendence | 超越性 |  |
| immanent cause | 内在因 |  |
| adequate idea | 充分观念 |  |
| intellect | 理智 | vs. understanding → 知性 |
| will | 意志 |  |
| power / potentia / puissance | 力量 / 潜能 | flag FR puissance vs. pouvoir |
| expression | 表达 |  |
| univocity | 单义性 |  |

### FR↔ZH specific
- *être* → 存在（as verb）/ 存在者（as noun, context-dependent）
- *étant* → 存在者
- *raison* → 理性 / 理由（distinguish）
- *connaissance* → 认识 / 知识
- *puissance* vs. *pouvoir* → 潜能 vs. 权力（flag when ambiguous）
- *sujet* → 主体 / 主语（distinguish grammatical vs. philosophical use）

### DE→ZH specific
- *Geist* → 精神（not "鬼"）
- *Aufhebung* → 扬弃（keep German on first use）
- *Dasein* → 此在（Heidegger) / 定在（Hegel）— always specify which
- *Vorstellung* → 表象
- *Begriff* → 概念
- *Sittlichkeit* → 伦理生活
- *Weltanschauung* → 世界观

## Footnotes and Citations

- Preserve all footnote numbers exactly. Translate footnote content fully.
- For bibliographic entries in footnotes: translate titles into the target language, but keep the original title in brackets: *Éthique* [Ethics].
- Do not add or remove citations.
- If the source text cites a passage in a language other than the main text language (e.g., a French text quoting Spinoza in Latin), translate the quoted passage into Chinese and keep the original in parentheses.

## Output Format

```
【译文】

[Full translated text, preserving section headers, paragraph breaks, and footnote markers]

---
【术语注记】
[List any terms where you made a deliberate rendering choice that differs from convention, or where the source was ambiguous. One line each: 原词 → 译词 — 理由]
```

If the text is short (under 200 words in the source), omit the 术语注记 section unless there are genuinely notable choices.

## What NOT to do

- Do not summarize or paraphrase — this is translation, not synthesis.
- Do not add explanatory glosses inside the main text (use footnotes marked [译注] if truly necessary, and keep them minimal).
- Do not normalize the author's style. If Spinoza is geometrical, stay geometrical. If Derrida is recursive and dense, stay recursive and dense.
- Do not silently change a term mid-text for stylistic variety.
