# Capacidades por nível

Verificado em 2026-10-21. Esta tabela é ponto de partida: a disponibilidade muda rápido e é confirmada na verificação de recursos de cada criação.

- **Copilot Basic:** Copilot Chat sem licença do Microsoft 365 Copilot e sem cobrança por consumo.
- **Copilot Premium:** licença do Microsoft 365 Copilot ou tenant com cobrança por consumo ativa.

| Recurso do agente | Copilot Basic | Copilot Premium |
|---|---|---|
| Instruções personalizadas | Sim | Sim |
| Code Interpreter | Sim | Sim |
| Gerador de imagens | Sim | Sim |
| Pesquisa na web (geral ou restrita a sites) | Sim | Sim |
| Ações personalizadas | Sim | Sim |
| SharePoint e OneDrive | Não | Sim |
| Arquivos enviados (embedded) | Não | Sim |
| Conectores do Copilot | Não | Sim |
| Dataverse | Não | Sim |
| Skills | Em implantação no Copilot Chat (MC1493223, out.–nov. 2026); confirmar para agentes | Sim (preview em agentes do Agent Builder, Frontier Program) |
| E-mail, pessoas, mensagens e reuniões do Teams | Não | Sim, só com a licença do Microsoft 365 Copilot |

Exceção documentada: com cobrança por consumo, sem a licença, e-mail, pessoas e Teams não ficam disponíveis como fonte. Se o cliente Premium depender dessas fontes, confirme se os usuários têm a licença.

Custo no Premium por cobrança por consumo:
- Agentes com instruções ou só com dados públicos da web não geram custo adicional.
- Agentes com dados do tenant (SharePoint, conectores) geram cobrança em Copilot Credits.
- A cobrança por consumo é habilitada pelo administrador e não é suportada em GCC e GCCH.

No Copilot Basic, o agente trabalha com a web e com o conteúdo que o usuário fornece: colar texto ou anexar arquivos na conversa.

Fontes: https://learn.microsoft.com/microsoft-365/copilot/extensibility/prerequisites ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/cost-considerations ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-add-skills
