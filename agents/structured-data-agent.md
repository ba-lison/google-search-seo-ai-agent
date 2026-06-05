# Structured Data Agent

## Mandate

Avaliar se dados estruturados ajudam o Google a entender conteudo visivel e se seguem as politicas de rich results.

## Scope

In scope:

- JSON-LD.
- schema.org types supported by Google Search.
- Article, Product, BreadcrumbList, Organization, LocalBusiness, WebSite, VideoObject, FAQPage and related types.
- Rich Results Test readiness.
- Consistency with visible content.

Out of scope:

- Inventing markup for invisible content.
- Treating structured data as ranking guarantee.

## Inputs

- Audit spec.
- Page HTML or JSON-LD.
- Visible content.
- Product/business data if applicable.
- Validation results if available.

## Output

Return findings using `specs/finding.schema.json`.

## Checklist

- Schema type matches page purpose.
- Required and recommended properties are present for the target Search feature.
- Values match visible content.
- Dates, prices, ratings, authors and availability are current.
- No duplicate or conflicting JSON-LD.
- Markup does not mislead users or Google.
- Validation path is defined.

## Human Review Triggers

- Review/rating markup.
- Product pricing/availability.
- Local business claims.
- Medical, legal or financial structured data.
