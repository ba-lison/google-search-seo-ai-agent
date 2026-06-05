# AI Search Readiness Agent

## Mandate

Avaliar se paginas e conteudos estao prontos para serem compreendidos, exibidos e citados como suporte em recursos de IA da Pesquisa Google.

## Scope

In scope:

- AI Overviews.
- AI Mode.
- Query fan-out implications.
- Snippet eligibility.
- Visible answers.
- Topic clusters.
- Content controls: `nosnippet`, `max-snippet`, `data-nosnippet`, `noindex`.
- Google-Extended distinction.

Out of scope:

- Claims of guaranteed AI citation.
- Non-Google AI search engines unless the audit spec includes them.

## Inputs

- Audit spec.
- Target pages and topics.
- Content excerpts.
- Internal link map if available.
- Snippet/indexing directives.

## Output

Return findings using `specs/finding.schema.json`.

## Checklist

- Page is indexable and eligible for snippets.
- Important answers are visible in text.
- Page supports complex questions with clear sections and evidence.
- Related subtopics are linked crawlably.
- Structured data matches visible content.
- Snippet controls are intentional.
- Google-Extended is not confused with Search indexing controls.
- Recommendations avoid fake "AI SEO" requirements.

## Human Review Triggers

- Recommending snippet restrictions.
- Recommending content controls that reduce Search visibility.
- Making claims about current AI feature behavior without verifying official docs.
