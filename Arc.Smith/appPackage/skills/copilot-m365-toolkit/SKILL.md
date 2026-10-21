---
name: copilot-m365-toolkit
description: "Orienta a criação de agentes declarativos com o Microsoft 365 Agents Toolkit (público técnico): declarativeAgent.json, manifest.json, capabilities, conversation starters, behavior overrides, custom skills, plugins MCP e de API, ambientes, provision, deploy e publish. Use quando a plataforma de destino for o Agents Toolkit ou quando o usuário pedir arquivos de manifesto, capabilities, MCP ou comandos do atk."
---

# Microsoft 365 Agents Toolkit (agentes declarativos)

## Objetivo
Orientar a construção de agentes declarativos em código com o Agents Toolkit, garantindo manifesto válido, capabilities corretas e ciclo de vida seguro (provision, deploy, publish).

## Quando usar
- A plataforma de destino é o Agents Toolkit (público técnico, projeto versionado em repositório).
- O usuário pede declarativeAgent.json, manifest.json, ai-plugin.json, capabilities, conversation starters, skills ou MCP.
- O usuário pede comandos do atk ou ajuda com erros de provision e validação.

## Regra absoluta
Antes de afirmar uma propriedade, um valor válido ou um limite do manifesto, consulte o Microsoft Learn MCP. Propriedade não reconhecida invalida o manifesto inteiro: nunca invente campos.

## Fluxo
1. Confirme a versão de schema do projeto (campo version e $schema) e o público do agente (licença).
2. Monte ou revise o declarativeAgent.json (references/manifest-declarativeagent.md).
3. Escolha as capabilities pelo caso e pela licença (references/capabilities.md).
4. Se houver integração, defina skills, MCP ou API plugin (references/skills-mcp-actions.md).
5. Oriente o ciclo de vida: versão, ambiente e comandos (references/provision-deploy.md).
6. As instruções seguem o Prompt-Base da skill smith-prompt, no arquivo instruction.txt (até 8.000 caracteres).

## Regras
- Entregue arquivos JSON completos em bloco de código, prontos para colar, e valide a sintaxe antes de entregar.
- Use somente valores documentados (exemplo: default_response_mode aceita só Auto, Quick response e Think deeper).
- Suba o version do manifest.json antes de cada provision.
- Skills exigem schema v1.9 e não combinam com EmbeddedKnowledge (preview).
- Para fatos que mudam rápido, use references/fatos-volateis.md como ponto de partida e confirme no Learn.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/manifest-declarativeagent.md | Para propriedades e limites do declarativeAgent.json e do manifest.json |
| references/capabilities.md | Para escolher e configurar capabilities |
| references/skills-mcp-actions.md | Para custom skills, plugins MCP e plugins de API |
| references/provision-deploy.md | Para ambientes, versões e comandos do atk |
| references/capacidades-limites.md | Para visão geral, licença e restrições do agente declarativo |
| references/fatos-volateis.md | Ponto de partida para limites e status; confirmar no Learn |
