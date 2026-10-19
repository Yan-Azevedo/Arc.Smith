# Fatos voláteis: Microsoft 365 Agents Toolkit

Fatos que mudam rápido. Em conflito, o Microsoft Learn prevalece. Revalidar conforme a coluna Revalidar.

| ID | Fato | Valor atual | Status (GA, Preview, Planejado) | Fonte (URL Learn) | Verificado em | Afeta | Revalidar (dias) |
|---|---|---|---|---|---|---|---|
| FV-01 | Máx. skills por agente | 8 | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit, declarativeAgent.json | 30 |
| FV-02 | Máx. arquivos nas skills (Toolkit) | 350 (matriz de suporte) / 400 (artigo do Toolkit): a doc diverge; usar 350 como limite | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills#support-matrix | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-03 | Profundidade máx. de diretório | 3 | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-04 | Tamanho do pacote (Toolkit) | 10 MB | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-05 | Skill como .zip no Toolkit | não suportado (diretório) | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-06 | Skills + embedded files | não combinam (suporte planejado) | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit, decisão de arquitetura (sem EmbeddedKnowledge) | 30 |
| FV-07 | Manifest mínimo para skills | declarativeAgent v1.9 | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit, declarativeAgent.json | 30 |
| FV-08 | Variável para habilitar | TEAMSFX_AGENT_SKILLS=true | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit, ambiente do desenvolvedor | 30 |
| FV-09 | Scripts na sandbox | sem rede, sem instalar pacotes, sem chamadas autenticadas, sem MCP/connectors | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-10 | Tenants com Purview Information Barriers | skills indisponíveis | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit, documentacao | 30 |
| FV-11 | ISVs / Partner Center | não suportado ainda | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | copilot-m365-toolkit | 30 |
| FV-12 | default_response_mode válidos | Auto, Quick response, Think deeper | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | a verificar | copilot-m365-toolkit, declarativeAgent.json | 90 |
| FV-13 | Limite de instructions do agente | 8000 caracteres | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-instructions | 2026-10-19 | smith-prompt, instruction.txt | 90 |
| FV-14 | Limite de SKILL.md | SKILL.md: instruções < 20.000 caracteres (recursos não entram na conta) | Preview | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills | 2026-10-19 | todas as skills | 30 |
| FV-15 | Conteúdo de fontes de conhecimento não é instrução confiável (XPIA): diretivas podem ser bloqueadas ou truncadas. Regras de comportamento ficam em instruction.txt e SKILL.md | Tratar como não confiável | GA | https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-instructions | 2026-10-19 | todas as skills, instruction.txt | 90 |
