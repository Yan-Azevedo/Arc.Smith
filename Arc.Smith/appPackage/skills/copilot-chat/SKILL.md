---
name: copilot-chat
description: "Orienta a criação de agentes para o Copilot Basic (Copilot Chat sem licença do Microsoft 365 Copilot): recursos disponíveis no nível, que mudam rápido e são confirmados no Learn a cada criação, e quando o cliente passa a ter a estrutura do Copilot Premium. Use quando o nível do cliente for Copilot Basic."
---

# Agentes para Copilot Basic

## Objetivo
Garantir que o agente proposto funcione no Copilot Basic, usando somente os recursos disponíveis nesse nível.

## Quando usar
- O nível do cliente é Copilot Basic: Copilot Chat sem licença do Microsoft 365 Copilot e sem cobrança por consumo.
- O usuário pergunta o que é possível fazer no Copilot Basic.

Se o tenant tiver cobrança por consumo ativa, o cliente tem a estrutura do Copilot Premium: use a skill copilot-m365-agent-builder sem as restrições desta skill.

A criação acontece no Agent Builder: carregue também a skill copilot-m365-agent-builder para campos, limites e os dois modos de criação (Assistente e Detalhado).

## Regra absoluta
Consulte o Microsoft Learn MCP antes de afirmar disponibilidade. Em conflito, o Learn prevalece. Não prometa recursos que o Copilot Basic não tem.

## Fluxo
1. Confirme o nível do cliente. Se não souber, pergunte.
2. Faça a verificação de recursos (arquivo verificacao-recursos.md da skill smith-prompt) e classifique cada fonte, capacidade e skill pedida: disponível no Basic hoje ou só no Premium. Use references/capacidades-limites.md como ponto de partida.
3. Se o caso depende de algo só do Premium, informe e proponha alternativa: o usuário anexar ou colar o conteúdo na conversa, usar sites públicos ou passar para o Copilot Premium.
4. Gere o agente com a skill smith-prompt, no modo escolhido.

## Regras
- Skills no Copilot Basic estão em mudança (implantação no Copilot Chat entre outubro e novembro de 2026): inclua a seção Skills no briefing só se a verificação de recursos confirmar.
- Dados do tenant (SharePoint, OneDrive, arquivos enviados, conectores, Dataverse, e-mail, pessoas e Teams) não estavam disponíveis no Basic na última verificação: confirme antes de propor.
- A documentação diverge sobre a criação de agentes por usuários sem licença (references/fatos-volateis.md, CC-05): confirme no tenant antes de prometer.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/capacidades-limites.md | Para saber o que está disponível em cada nível |
| references/instrucoes-e-prompts.md | Para escrever instruções de agentes sem dados do tenant |
| references/fatos-volateis.md | Ponto de partida para disponibilidade; confirmar no Learn |
