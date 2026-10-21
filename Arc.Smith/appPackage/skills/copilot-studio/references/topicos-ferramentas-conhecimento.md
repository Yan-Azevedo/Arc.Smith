# Copilot Studio: conhecimento, ferramentas, tópicos e instruções

Verificado em 2026-10-20. Confirme no Microsoft Learn MCP.

## Fontes de conhecimento
- Tipos: sites públicos, arquivos enviados, SharePoint, OneDrive, Dataverse, Azure AI Search, conectores em tempo real, Copilot connectors e dados não estruturados.
- Cada fonte exige nome único e descrição; a descrição detalhada orienta a orquestração generativa.
- Orquestração generativa: até 25 sites ou URLs do SharePoint; acima de 25 fontes, o agente filtra por um modelo interno. Arquivos enviados não contam nesse limite.
- Orquestração clássica e nó de respostas generativas: 4 sites, 4 URLs do SharePoint, 2 fontes Dataverse (15 tabelas cada). Exceder esse limite no nó impede a publicação.
- SharePoint e Dataverse usam a autenticação do usuário: o agente só mostra o que o usuário pode acessar.
- Documentos com rótulo de confidencialidade ou senha não são indexados.
- "Tenant graph grounding with semantic search" melhora a busca no SharePoint e em conectores; exige orquestração generativa, autenticação Microsoft e tem custo adicional para usuários sem licença.
- Citações retornadas pelo conhecimento não podem ser usadas como entrada de outras ferramentas.

## Ferramentas
| Tipo | Quando usar | Regras |
|---|---|---|
| Conectores | Integrar serviços com conector pronto (SharePoint, Outlook, Salesforce, ServiceNow etc.) | Selecione só as ações necessárias; revise a descrição |
| Fluxo de agente | Processos determinísticos de várias etapas | Gatilho "When an agent calls the flow", ação "Respond to the agent", resposta síncrona, publicado, até 100 segundos |
| Prompt | Tarefa específica com modelo de IA (extração, classificação, geração) | Define modelo, temperature (0 a 1) e entradas; pode ser usado no agente, no tópico ou no fluxo |
| MCP | Serviços próprios ou internos expostos por servidor MCP | Revise nome e descrição de cada ferramenta; mantenha poucos servidores por agente |
| Workflows | Processos automatizados no designer de fluxos | Disponível conforme o harness |

A descrição da ferramenta é o que o orquestrador usa para decidir quando chamá-la: escreva quando usar e quando não usar.

## Tópicos (standard harness)
- Gatilho por descrição: escreva a descrição de forma explícita e detalhada (exemplo: "Aciona SEMPRE que o usuário confirmar: Sim, Confirmo, Pode registrar"). Descrições vagas fazem o orquestrador ignorar o tópico.
- Variáveis que passam de um tópico para outro precisam ser globais.
- Use tópicos quando a resposta precisa ser exatamente a mesma sempre.

## Instruções
- Até 8.000 caracteres; aceitam Markdown e o Prompt-Base da skill smith-prompt.
- Digite "/" para referenciar ferramenta, tópico, outro agente, variável ou expressão Power Fx, usando o nome exato.
- Só instrua o uso de ferramentas e conhecimento que o agente tem configurados.
- Se o agente não deve fazer perguntas ao usuário, diga isso explicitamente.
- Não altere o formato nem o comportamento de citações.

Fontes: https://learn.microsoft.com/microsoft-copilot-studio/knowledge-copilot-studio ; https://learn.microsoft.com/microsoft-copilot-studio/knowledge-add-existing-copilot ; https://learn.microsoft.com/microsoft-copilot-studio/flow-agent ; https://learn.microsoft.com/microsoft-copilot-studio/nlu-prompt-node ; https://learn.microsoft.com/microsoft-copilot-studio/prompt-model-settings ; https://learn.microsoft.com/microsoft-copilot-studio/mcp-add-components-to-agent ; https://learn.microsoft.com/microsoft-copilot-studio/authoring-instructions ; https://learn.microsoft.com/microsoft-copilot-studio/guidance/generative-mode-guidance
