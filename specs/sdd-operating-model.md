# SDD Operating Model

This project uses lightweight Spec-Driven Development for agent orchestration.

## Levels

1. Constitution: non-negotiable principles.
2. Audit Spec: the current job contract.
3. Agent Specs: specialist mandates and boundaries.
4. Handoff Contracts: input/output schemas between agents.
5. Findings: evidence-backed observations.
6. Report: final prioritized plan.

## Workflow

```text
request
  -> audit spec
  -> clarification if needed
  -> delegation plan
  -> specialist findings
  -> synthesis
  -> validation plan
```

## Pragmatic Rule

Use enough specification to remove ambiguity, but not so much that the process becomes markdown theater.

For small questions, use the skill directly.

For complex audits, use the full orchestrator flow.

## Audit Spec Fields

- `objective`: what the user wants to know or improve.
- `site`: domain or product.
- `site_type`: ecommerce, SaaS, marketplace, content site, institutional, local business, app docs or other.
- `scope`: full site, template, single URL, traffic drop, AI readiness or structured data.
- `urls`: priority URLs.
- `data_available`: Search Console, Analytics, crawl, logs, source code, screenshots.
- `constraints`: access, time, platform, legal, brand or deployment constraints.
- `success_criteria`: what a good answer must include.
- `subagents`: selected specialists.
- `output_format`: executive report, technical backlog, marketing plan or mixed.

## Clarification Rules

Ask only when the missing detail changes the result.

Examples:

- Ask for URL if none is available.
- Ask for date range when diagnosing traffic drop.
- Ask for site type if recommendations differ by ecommerce/content/SaaS.
- Ask for Search Console access/export when the user asks for data-backed diagnosis.

Do not ask if a reasonable assumption is safe. State the assumption instead.

## Validation

The final report must be checked against:

- constitution;
- audit spec;
- Google Search SEO skill;
- finding schema;
- no guaranteed ranking language;
- clear validation path.
