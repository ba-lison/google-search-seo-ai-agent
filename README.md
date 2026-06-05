# Google Search SEO AI Agent

Um modelo aberto de agent orquestrador + subagents para auditoria, planejamento e melhoria continua de SEO com foco em Google Search, recursos de IA na Pesquisa e conteudo gerado com IA.

Este repositorio complementa a skill [google-search-seo-ai](https://github.com/balison13/google-search-seo-ai). A skill e a base de conhecimento. Este repo e a camada operacional: define como um agent deve receber um objetivo, criar uma especificacao, delegar para subagents, consolidar achados e entregar um plano validavel.

## Por Que Isso Existe

SEO esta deixando de ser apenas uma lista de tags e checklists. Com AI Overviews, AI Mode, query fan-out, conteudo gerado com IA e experiencias cada vez mais dinamicas, equipes precisam de um processo que conecte:

- tecnica: rastreamento, renderizacao, indexacao, dados estruturados e performance;
- conteudo: utilidade, confiabilidade, originalidade, atualizacao e intencao de busca;
- IA: elegibilidade para recursos de IA, snippets, controles de exibicao e uso responsavel de generative AI;
- negocio: prioridade, impacto, esforco, donos, prazos e medicao.

Um agent unico tentando fazer tudo tende a virar uma consultoria generica. Este projeto propoe outro caminho: um orquestrador cria uma spec da auditoria, subagents especialistas executam partes bem delimitadas e um sintetizador transforma os achados em plano.

## A Tese SDD

Este agent usa uma abordagem inspirada em Spec-Driven Development:

1. Primeiro especificar o objetivo, escopo, criterios e formato de saida.
2. Depois delegar tarefas com contratos claros de input e output.
3. Por fim validar se o resultado responde a spec original.

SDD faz sentido aqui porque SEO e IA na Pesquisa tem muita ambiguidade. Sem especificacao, o agent precisa adivinhar se a tarefa e tecnica, editorial, estrategica, ecommerce, recuperacao de queda, readiness para IA ou tudo ao mesmo tempo.

Este repo nao tenta aplicar SDD de forma pesada. A regra e pragmatica: usar o minimo de spec necessario para remover ambiguidade e tornar o trabalho repetivel.

Veja tambem [`docs/sdd-notes.md`](docs/sdd-notes.md) para a sintese do raciocinio de SDD aplicado ao agent.

## Arquitetura

```text
User Request
    |
    v
Orchestrator Agent
    |
    +-- creates Audit Spec
    +-- selects subagents
    +-- validates handoffs
    |
    +--> Technical SEO Agent
    +--> Content Quality Agent
    +--> AI Search Readiness Agent
    +--> Structured Data Agent
    +--> Measurement Agent
    |
    v
Synthesis / Action Plan Agent
    |
    v
Executive Report + Dev Backlog + Marketing Backlog + Validation Plan
```

## Estrutura

```text
google-search-seo-ai-agent/
|-- AGENTS.md
|-- constitution.md
|-- agents/
|   |-- orchestrator.md
|   |-- technical-seo-agent.md
|   |-- content-quality-agent.md
|   |-- ai-search-readiness-agent.md
|   |-- structured-data-agent.md
|   |-- measurement-agent.md
|   `-- synthesis-action-plan-agent.md
|-- specs/
|   |-- audit-spec.schema.json
|   |-- agent-handoff.schema.json
|   |-- finding.schema.json
|   `-- sdd-operating-model.md
|-- docs/
|   `-- sdd-notes.md
|-- examples/
|   |-- sample-audit-spec.json
|   `-- sample-finding.json
|-- playbooks/
|   |-- full-site-audit.md
|   |-- single-url-audit.md
|   |-- traffic-drop-debug.md
|   `-- ai-search-readiness.md
`-- reports/
    `-- templates/
        `-- executive-report.md
```

## Como Usar

Use o orquestrador como ponto de entrada:

```text
Use o Google Search SEO AI Agent para auditar este site:

Site:
Objetivo:
Tipo de negocio:
URLs prioritarias:
Acesso ao Search Console: sim/nao
Stack:
Principais duvidas:
Prazo/urgencia:
```

O orquestrador deve:

1. Criar uma `Audit Spec`.
2. Identificar ambiguidades e pedir clarificacao quando necessario.
3. Escolher subagents conforme o objetivo.
4. Delegar com contratos de handoff.
5. Consolidar achados sem duplicar ou inventar evidencia.
6. Entregar plano priorizado com validacao.

## Quando Usar

Use este agent para:

- auditoria tecnica de SEO;
- revisao de sites JavaScript;
- preparacao para AI Overviews e AI Mode;
- avaliacao de conteudo gerado por IA;
- auditoria de dados estruturados;
- diagnostico de queda de trafego;
- criacao de backlog para dev, marketing e produto;
- traducao de documentacao Google Search em plano de execucao.

Nao use quando:

- a tarefa e uma pergunta simples que a skill resolve sozinha;
- o site ainda e um prototipo descartavel;
- nao ha URL, objetivo ou contexto minimo;
- o usuario espera garantia de ranking ou inclusao em recurso de IA.

## Relacao Com A Skill

Instale tambem a skill:

```bash
git clone https://github.com/balison13/google-search-seo-ai.git ~/.codex/skills/google-search-seo-ai
```

Este agent deve consultar a skill para regras de Google Search, IA, generative AI content, Search Console, structured data e playbooks de auditoria.

## Exemplos

- [`examples/sample-audit-spec.json`](examples/sample-audit-spec.json): exemplo de spec de auditoria.
- [`examples/sample-finding.json`](examples/sample-finding.json): exemplo de finding retornado por um subagent.

## Licenca

MIT. Use, adapte e compartilhe.
