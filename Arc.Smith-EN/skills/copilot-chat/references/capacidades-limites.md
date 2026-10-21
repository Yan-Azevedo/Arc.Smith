# Capabilities by level

Verified on 2026-10-21. This table is a starting point: availability changes fast and is confirmed in the feature check of every creation.

- **Copilot Basic:** Copilot Chat without a Microsoft 365 Copilot license and without pay-as-you-go billing.
- **Copilot Premium:** Microsoft 365 Copilot license or a tenant with pay-as-you-go billing turned on.

| Agent feature | Copilot Basic | Copilot Premium |
|---|---|---|
| Custom instructions | Yes | Yes |
| Code Interpreter | Yes | Yes |
| Image generator | Yes | Yes |
| Web search (general or scoped to sites) | Yes | Yes |
| Custom actions | Yes | Yes |
| SharePoint and OneDrive | No | Yes |
| Uploaded files (embedded) | No | Yes |
| Copilot connectors | No | Yes |
| Dataverse | No | Yes |
| Skills | Rolling out in Copilot Chat (MC1493223, Oct–Nov 2026); confirm for agents | Yes (preview in Agent Builder agents, Frontier Program) |
| Email, people, Teams messages and meetings | No | Yes, only with the Microsoft 365 Copilot license |

Documented exception: with pay-as-you-go billing and no license, email, people and Teams are not available as sources. If a Premium client depends on these sources, confirm whether the users have the license.

Cost in Premium through pay-as-you-go billing:
- Agents with instructions or only public web data have no additional cost.
- Agents with tenant data (SharePoint, connectors) are billed in Copilot Credits.
- Pay-as-you-go billing is turned on by the administrator and is not supported in GCC and GCCH.

In Copilot Basic, the agent works with the web and the content the user provides: pasting text or attaching files in the conversation.

Sources: https://learn.microsoft.com/microsoft-365/copilot/extensibility/prerequisites ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/cost-considerations ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-add-skills
