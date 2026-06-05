# SDD Notes

Estas notas resumem como a pesquisa sobre Spec-Driven Development foi aplicada neste agent.

## O Que Faz Sentido

SDD combina com este projeto porque um agent de SEO + IA precisa operar com ambiguidade controlada:

- o usuario pode querer auditoria tecnica, plano de marketing, diagnostico de queda, readiness para IA ou tudo junto;
- subagents diferentes precisam receber o mesmo objetivo sem reinterpretar a tarefa;
- findings precisam voltar em formato comparavel;
- o relatorio final precisa ser rastreavel ate evidencia, nao apenas opiniao.

Por isso o repo adota:

- `constitution.md` como principios permanentes;
- `specs/audit-spec.schema.json` como contrato de entrada;
- `specs/agent-handoff.schema.json` como contrato entre orquestrador e subagents;
- `specs/finding.schema.json` como formato comum de achados;
- `agents/*.md` como specs de agentes;
- `playbooks/*.md` como fluxos reutilizaveis.

## O Que Foi Evitado

O repo evita aplicar SDD de forma pesada demais.

Nao foram criados muitos arquivos por feature, comandos slash, tarefas atomizadas ou um processo rigido de implementacao. Para este momento, isso seria excesso.

A regra usada:

```text
Use o minimo de especificacao que remove ambiguidade e melhora a coordenacao.
```

## Modelo De Maturidade

### Fase 1: Spec-First Leve

Usar constitution, agent specs, handoffs e findings. Ideal para o estado atual do repo.

### Fase 2: Spec-Anchored

Adicionar validadores, exemplos reais de auditoria, fixtures e testes de consistencia entre specs e reports.

### Fase 3: Operacional

Integrar crawlers, Search Console, Lighthouse, GitHub Issues e pipelines de relatorio.

### Fase 4: Produto

Transformar em aplicacao ou MCP/agent service com UI, historico, memoria, rotinas de monitoramento e revisoes recorrentes.

## Principio Final

A skill responde "o que o Google diz".

O agent responde "como coordenar trabalho real usando isso".
