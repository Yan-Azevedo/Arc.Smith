# Copilot Studio: licenciamento e Copilot Credits

Valores verificados em 2026-10-20 para o standard harness. Mudam com frequência: confirme no Microsoft Learn MCP e no Microsoft Copilot Studio Licensing Guide antes de informar custos.

## Tabela de cobrança (standard harness)
| Recurso | Copilot Credits | Usuário com licença do Microsoft 365 Copilot |
|---|---|---|
| Resposta clássica | 1 | Sem cobrança |
| Resposta generativa | 2 | Sem cobrança |
| Ação do agente (gatilhos, raciocínio, transição de tópicos) | 5 | Sem cobrança |
| Grounding no grafo do tenant | 10 | Sem cobrança |
| Ações de fluxo de agente (a cada 100) | 13 | Sem cobrança, só com o gatilho "When an agent calls the flow" |
| Ferramentas de IA básicas (a cada 10 respostas) | 1 | Sem cobrança |
| Ferramentas de IA padrão (a cada 10 respostas) | 15 | Sem cobrança |
| Ferramentas de IA premium (a cada 10 respostas) | 100 | Sem cobrança |
| Processamento de conteúdo (por página) | 8 | Sem cobrança |

Regras:
- Uma interação pode somar vários recursos (exemplo: grounding no grafo, 10, mais resposta generativa, 2, igual a 12 créditos).
- Modelos de raciocínio somam a taxa do recurso mais a taxa premium por 1.000 tokens.
- A inclusão para usuários licenciados vale para cenários internos (empresa para funcionário), com a identidade do usuário licenciado.
- Agentes de uso de computador (computer use) não estão incluídos na licença.
- Ao esgotar a capacidade pré-paga, novas execuções de fluxos de agente são bloqueadas; a 125% de consumo, agentes personalizados são desativados.
- O GitHub Copilot harness tem modelo de cobrança próprio; consulte o Learn.

## Estimativa
Use o Microsoft Copilot Studio agent usage estimator para prever o consumo por tipo de agente, tráfego, orquestração, conhecimento e ferramentas.

Fontes: https://learn.microsoft.com/microsoft-copilot-studio/requirements-messages-management ; https://learn.microsoft.com/microsoft-copilot-studio/billing-licensing ; https://learn.microsoft.com/power-platform/admin/manage-copilot-studio-copilot-credits-capacity
