# Copilot Studio: harnesses e limites

Verificado em 2026-10-20. Confirme no Microsoft Learn MCP.

## Harnesses (runtime do agente)
| Harness | Melhor para | Como funciona | Observações |
|---|---|---|---|
| GitHub Copilot harness | Processos de negócio complexos e de várias etapas | Recebe um objetivo, divide em etapas, chama ferramentas e se recupera de falhas | Cria e edita Word, Excel, PowerPoint e PDF; tem skills e memória; publica para equipes internas ou clientes externos; cobrança em Copilot Credits. Não é o serviço GitHub Copilot. |
| Standard harness | Agentes baseados em regras e conversas estruturadas | Segue os tópicos, prompts e caminhos definidos | Comportamento previsível; publica para equipes internas ou clientes externos. |
| Copilot chat harness | Estender o Microsoft Copilot Chat com conhecimento da organização | Conecta o conhecimento da empresa ao Copilot Chat | Publica para equipes internas; cobrança por consumo ou incluída na licença do Microsoft 365 Copilot. |

Recursos e documentação variam por harness: muitos artigos indicam no topo a qual harness se aplicam.

## Campos do agente
| Campo | Regra |
|---|---|
| Nome | Até 42 caracteres, sem < e > |
| Descrição | Até 1.024 caracteres |
| Instruções | Até 8.000 caracteres (agente para o Microsoft Copilot) |
| Ícone | PNG, 192 x 192 pixels; a doc diverge sobre o tamanho (menos de 72 KB em um artigo, 100 KB em outro) |

## Limites do Copilot Studio (aplicativo web)
| Item | Limite |
|---|---|
| Fontes de conhecimento | 500 objetos por agente (arquivos, pastas, artigos, sites) |
| Sites públicos e URLs do SharePoint | 25 na orquestração generativa; 4 na clássica e no nó de respostas generativas |
| Arquivos enviados | 500 arquivos, até 512 MB |
| Tópicos | 1.000 por agente em ambientes com Dataverse |
| Frases de gatilho | 200 por tópico |
| Payload de conector | 5 MB (450 KB em GCC) |
| Fluxo de agente | Responder em até 100 segundos |
| Resposta do modelo | Tempo limite de 5 minutos por resposta em streaming |
| Fontes de dados não estruturados | Até 5 tipos diferentes ao mesmo tempo |

Fontes: https://learn.microsoft.com/microsoft-copilot-studio/harnesses-overview ; https://learn.microsoft.com/microsoft-copilot-studio/authoring-first-bot ; https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/authoring-instructions ; https://learn.microsoft.com/microsoft-copilot-studio/requirements-quotas ; https://learn.microsoft.com/microsoft-copilot-studio/knowledge-copilot-studio ; https://learn.microsoft.com/microsoft-copilot-studio/knowledge-unstructured-data
