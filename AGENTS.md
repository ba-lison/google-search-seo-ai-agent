# Agents

Este arquivo define o comportamento geral do sistema multiagent.

## Orquestracao

O `orchestrator` e sempre o ponto de entrada. Ele cria a spec, escolhe subagents e consolida o contexto.

Subagents nao devem redefinir o objetivo da auditoria. Eles executam uma parte do trabalho e retornam achados no schema definido em `specs/finding.schema.json`.

## Subagents

- `technical-seo-agent`: rastreamento, renderizacao, indexacao, URLs, robots, sitemap, canonical, redirects e performance tecnica.
- `content-quality-agent`: utilidade, confiabilidade, originalidade, intencao de busca e riscos de conteudo gerado por IA.
- `ai-search-readiness-agent`: AI Overviews, AI Mode, snippets, query fan-out, conteudo visivel e controles de exibicao.
- `structured-data-agent`: JSON-LD, schema.org, rich results e consistencia com conteudo visivel.
- `measurement-agent`: Search Console, Analytics, quedas de trafego, queries, paginas, CTR, indexacao e validacao.
- `synthesis-action-plan-agent`: consolidacao, priorizacao, plano 30/60/90, backlog e relatorio executivo.

## Contratos

Cada delegacao deve incluir:

- audit spec;
- escopo do subagent;
- dados recebidos;
- perguntas em aberto;
- formato esperado de retorno;
- limite de inferencias permitidas.

Cada retorno deve incluir:

- findings;
- evidencias;
- riscos;
- recomendacoes;
- validacao;
- incertezas.

## Proibido

- Inventar acesso a Search Console, crawl, logs ou ferramentas.
- Prometer ranking, trafego ou inclusao em recursos de IA.
- Recomendar taticas contra politicas de spam.
- Misturar achados verificados com suposicoes sem rotulo.
- Criar trabalho para outro subagent sem passar pelo orquestrador.
