---
name: copilot-m365-agent-builder
description: "Orienta a criação de agentes no Agent Builder do Microsoft 365 Copilot para Copilot Basic e Copilot Premium, nos dois modos: Assistente (entrevista ponto a ponto e briefing único para a conversa de criação) e Detalhado (configuração manual na aba Configurar, com pacote .zip de skills quando o nível suportar). Cobre campos, limites, fontes de conhecimento, capacidades, skills e teste. Use quando a plataforma de destino for o Agent Builder."
---

# Agent Builder do Microsoft 365 Copilot

## Objetivo
Garantir que o agente criado no Agent Builder respeite os campos, limites e recursos da plataforma e do nível do cliente (Copilot Basic ou Copilot Premium), em qualquer um dos dois modos.

## Quando usar
- A plataforma de destino é o Agent Builder.
- O usuário escolheu o modo Assistente.
- O usuário pede o passo a passo de criação, teste ou ajuste de um agente no Agent Builder.

Para Copilot Basic, carregue também a skill copilot-chat, que define o que não está disponível.

## Regra absoluta
Antes de afirmar um limite, um campo ou um recurso, consulte o Microsoft Learn MCP. Em conflito, o Learn prevalece. Se não houver documentação para um ponto, diga que não está documentado e não invente.

## Modos de criação
- **Assistente:** entreviste o usuário ponto a ponto e entregue uma única caixa copiável com o briefing completo para a conversa de criação, seguida do checklist pós-criação. Siga references/criacao-assistida.md.
- **Detalhado:** o usuário preenche a aba Configurar com as caixas geradas pela skill smith-prompt, camada por camada. Quando a verificação de recursos confirmar suporte a skills, elas vão como pacote .zip (arquivo skills-agente.md da skill smith-prompt). Siga references/passo-a-passo.md.

## Regras
- Nome com até 30 caracteres, descrição com até 1.000 e instruções com até 8.000.
- Só proponha fontes de conhecimento e capacidades disponíveis para o nível do cliente (references/capacidades-limites.md).
- Skills só quando a verificação de recursos (arquivo verificacao-recursos.md da skill smith-prompt) confirmar suporte para o nível do cliente.
- Configurações que só existem na aba Configurar (ícone, modo de resposta, priorizar fontes especificadas, pesquisar todos os sites, referenciar pessoas) vão no checklist pós-criação, nunca no briefing como se fossem automáticas.
- Integrações e ações não são criadas no Agent Builder: se o caso exigir, recomende o modo Detalhado no Copilot Studio ou no Agents Toolkit.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/criacao-assistida.md | No modo Assistente (entrevista, briefing e checklist) |
| references/passo-a-passo.md | No modo Detalhado e para orientar teste e criação |
| references/capacidades-limites.md | Para campos, limites, fontes de conhecimento, capacidades, skills e níveis |
| references/instrucoes-modelo.md | Para adaptar o Prompt-Base ao campo Instruções do Agent Builder |
| references/fatos-volateis.md | Ponto de partida para limites; confirmar no Learn |
