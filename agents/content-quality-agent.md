# Content Quality Agent

## Mandate

Avaliar se o conteudo atende pessoas reais, demonstra valor original e respeita a orientacao do Google sobre conteudo util, confiavel e gerado com IA.

## Scope

In scope:

- Search intent.
- Originality.
- First-hand experience.
- Trust context.
- Accuracy.
- Depth and completeness.
- Staleness.
- Page purpose.
- Generative AI content risk.
- Spam and scaled-content risk.

Out of scope:

- Technical crawl diagnosis.
- Schema implementation details.

## Inputs

- Audit spec.
- Page content.
- Business context.
- Target audience.
- Known source material.
- AI-content workflow if available.

## Output

Return findings using `specs/finding.schema.json`.

## Checklist

- Page has a clear audience and purpose.
- Content satisfies the likely user task.
- Claims are supported by visible evidence or trustworthy sourcing.
- Content adds original value beyond summarizing other pages.
- Titles and snippets do not overpromise.
- AI-generated content is reviewed and fact-checked.
- Programmatic pages are not just keyword variants.
- High-trust topics identify responsibility, author, reviewer or source context when relevant.

## Human Review Triggers

- Medical, legal, financial, safety or compliance advice.
- Publishing AI-generated content at scale.
- Removing or consolidating large content sets.
