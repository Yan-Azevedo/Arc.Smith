# Declarative agent with Agents Toolkit: overview and limits

Verified on 2026-10-20. Confirm in the Microsoft Learn MCP.

## What it is
A declarative agent is a package (app package) with manifest.json, declarativeAgent.json, instructions, icons and, optionally, plugins and skills. It runs in Microsoft 365 Copilot, with Copilot's orchestrator and models.

## Prerequisites
- Visual Studio Code with the Microsoft 365 Agents Toolkit extension, or the CLI (atk).
- A tenant that allows uploading custom apps (sideload). Without it, provision fails. The administrator enables it in Teams admin center, Teams apps, Setup policies, "Upload custom apps".
- Without a Microsoft 365 Copilot license you can build, but agents with organizational data require a license or pay-as-you-go billing.

## Capability availability by license
- Users without a license only access agents with capabilities beyond WebSearch if the tenant has pay-as-you-go billing or if they have a license.
- Email, people, Teams messages and meetings require a Microsoft 365 Copilot license.
- Details by scenario: copilot-chat skill (references/capacidades-limites.md).

## Main limits
| Item | Limit |
|---|---|
| name | 100 characters |
| description | 1,000 characters |
| instructions | 8,000 characters |
| conversation_starters | 12 items (schema 1.8) |
| actions | 1 to 10 plugins |
| Strings without their own limit | 4,000 characters |
| disclaimer | 500 characters |
| editorial_answers | 300 question and answer pairs |
| Package with skills | 10 MB; up to 8 skills; 350 files; depth 3 |

## When not to use the Toolkit
- Business user without a repository and without sideload access: prefer Agent Builder.
- Flows with topics, Power Platform connectors or external channels: prefer Copilot Studio.

Sources: https://learn.microsoft.com/microsoft-365/copilot/extensibility/build-declarative-agents ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/prerequisites ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8 ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills
