# Agente declarativo com Agents Toolkit: visão geral e limites

Verificado em 2026-10-20. Confirme no Microsoft Learn MCP.

## O que é
Um agente declarativo é um pacote (app package) com manifest.json, declarativeAgent.json, instruções, ícones e, opcionalmente, plugins e skills. Ele roda no Microsoft 365 Copilot, com o orquestrador e os modelos do Copilot.

## Pré-requisitos
- Visual Studio Code com a extensão Microsoft 365 Agents Toolkit, ou o CLI (atk).
- Tenant que permita carregar aplicativos personalizados (sideload). Sem isso, o provision falha. O administrador habilita em Teams admin center, Teams apps, Setup policies, "Upload custom apps".
- Sem licença do Microsoft 365 Copilot é possível construir, mas agentes com dados da organização exigem licença ou cobrança por consumo.

## Disponibilidade das capabilities por licença
- Usuários sem licença só acessam agentes com capabilities além de WebSearch se o tenant tiver cobrança por consumo ou se tiverem licença.
- E-mail, pessoas, mensagens e reuniões do Teams exigem licença do Microsoft 365 Copilot.
- Detalhes por cenário: skill copilot-chat (references/capacidades-limites.md).

## Limites principais
| Item | Limite |
|---|---|
| name | 100 caracteres |
| description | 1.000 caracteres |
| instructions | 8.000 caracteres |
| conversation_starters | 12 itens (schema 1.8) |
| actions | 1 a 10 plugins |
| Strings sem limite próprio | 4.000 caracteres |
| disclaimer | 500 caracteres |
| editorial_answers | 300 pares pergunta e resposta |
| Pacote com skills | 10 MB; até 8 skills; 350 arquivos; profundidade 3 |

## Quando não usar o Toolkit
- Usuário de negócio sem repositório e sem acesso a sideload: prefira o Agent Builder.
- Fluxos com tópicos, conectores do Power Platform ou canais externos: prefira o Copilot Studio.

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/prerequisites ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills
