---
name: copilot-studio
description: "Orienta a criação de agentes no Microsoft Copilot Studio: escolha do harness, instruções, fontes de conhecimento, tópicos, ferramentas (conectores, fluxos de agente, prompts, MCP), pipelines de captura de dados, publicação e consumo de Copilot Credits. Use quando a plataforma de destino for o Copilot Studio ou quando o caso exigir integrações, fluxos, tópicos ou canais além do Microsoft 365 Copilot."
---

# Microsoft Copilot Studio

## Objetivo
Orientar a construção de agentes no Copilot Studio com a arquitetura certa para o caso (harness, conhecimento, ferramentas e tópicos), dentro dos limites e com o custo previsível.

## Quando usar
- A plataforma de destino é o Copilot Studio.
- O caso exige integrações com sistemas, fluxos, tópicos estruturados, captura e gravação de dados ou canais externos.
- O usuário pergunta sobre consumo de Copilot Credits ou licenciamento do Copilot Studio.

## Regra absoluta
Antes de afirmar um limite, um recurso ou um valor de cobrança, consulte o Microsoft Learn MCP. Recursos variam por harness: confirme em qual harness o recurso existe. Não invente.

## Fluxo
1. Escolha o harness pelo caso (references/capacidades-limites.md).
2. Defina instruções (Prompt-Base da skill smith-prompt, até 8.000 caracteres), fontes de conhecimento e ferramentas (references/topicos-ferramentas-conhecimento.md).
3. Se houver captura e gravação de dados, use o padrão de references/pipeline-dados.md.
4. Estime o consumo e informe o modelo de cobrança (references/licenciamento-creditos.md).
5. Oriente teste no painel de teste e publicação no canal adequado.

## Regras
- Crie o agente pela interface web e não misture edição pela interface com edição dos arquivos YAML.
- Escreva descrições detalhadas para fontes de conhecimento, ferramentas e tópicos: o orquestrador generativo decide por elas.
- Nas instruções, cite ferramentas e tópicos com "/" e pelo nome exato.
- Não altere nem suprima o comportamento de citações nas instruções.
- Temperature só existe na ferramenta de Prompt (0 a 1, padrão 0, desabilitada em modelos de raciocínio); não é configurável no agente.

## Recursos
| Arquivo | Quando carregar |
|---|---|
| references/capacidades-limites.md | Para harnesses, limites e campos do agente |
| references/topicos-ferramentas-conhecimento.md | Para conhecimento, ferramentas, tópicos e instruções |
| references/pipeline-dados.md | Para captura de dados com fluxo e gravação (SharePoint, Dataverse) |
| references/licenciamento-creditos.md | Para cobrança, licenças e estimativa de Copilot Credits |
| references/fatos-volateis.md | Ponto de partida para limites e valores; confirmar no Learn |
