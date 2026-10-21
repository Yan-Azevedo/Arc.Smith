# Guia de Criação por plataforma

Como adaptar o modelo-entrega.md a cada plataforma. Os passos de tela vêm da skill da plataforma e do Microsoft Learn MCP no momento da geração.

| Plataforma | Skill de apoio | Seção 4 (criação) | Seção 5 (instruções) | Seções 6, 7 e 8 |
|---|---|---|---|---|
| Agent Builder no Copilot Basic | copilot-chat e copilot-m365-agent-builder | Modo Detalhado (aba Configurar) ou modo Assistente (briefing na conversa de criação) | Prompt-Base no campo Instruções | Recursos confirmados na verificação de recursos; na última verificação, sem dados do tenant |
| Agent Builder no Copilot Premium | copilot-m365-agent-builder | Modo Detalhado (aba Configurar) ou modo Assistente (briefing na conversa de criação) | Prompt-Base no campo Instruções | Fontes com limites do Agent Builder; capacidades "Create documents, charts, and code" e "Create images"; skills; prompts sugeridos |
| Agents Toolkit | copilot-m365-toolkit | Projeto no VS Code, arquivos do pacote e provision | Prompt-Base no instruction.txt | Capabilities no declarativeAgent.json; conversation_starters; público técnico |
| Copilot Studio | copilot-studio | Criação do agente, harness, conhecimento, ferramentas e tópicos | Prompt-Base no campo Instruções | Fontes e ferramentas do Copilot Studio; custo em Copilot Credits quando aplicável |
| Copilot Notebooks | copilot-notebooks | Criação do notebook | Prompt-Base em "Copilot instructions" | Seção 6 vira lista de referências; seção 7 vira saídas do notebook; seção 8 vira perguntas sugeridas para o chat |

## Regras por plataforma
- Agent Builder, modo Assistente: na seção 4, inclua o briefing em bloco de cópia e o checklist pós-criação.
- Agent Builder e Agents Toolkit com skills: na seção 4, inclua como subir ou registrar cada skill e o SKILL.md em bloco de cópia.
- Agents Toolkit: inclua os arquivos (declarativeAgent.json e instruction.txt) em bloco de cópia e os comandos de provision; avise que exige permissão de upload de aplicativos personalizados.
- Copilot Studio: inclua, quando houver, a configuração dos fluxos, tópicos e ferramentas, e a estimativa de consumo.
- Copilot Notebooks: avise que notebook excluído não pode ser recuperado e que as instruções ficam visíveis para quem recebe o compartilhamento.
- Em todas: nome e descrição dentro do limite da plataforma, e nenhum caminho de tela sem confirmação no Learn.
