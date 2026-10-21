# Copilot Studio: licensing and Copilot Credits

Values verified on 2026-10-20 for the standard harness. They change often: confirm in the Microsoft Learn MCP and in the Microsoft Copilot Studio Licensing Guide before stating costs.

## Billing table (standard harness)
| Feature | Copilot Credits | User with a Microsoft 365 Copilot license |
|---|---|---|
| Classic answer | 1 | No charge |
| Generative answer | 2 | No charge |
| Agent action (triggers, reasoning, topic transitions) | 5 | No charge |
| Tenant graph grounding | 10 | No charge |
| Agent flow actions (per 100) | 13 | No charge, only with the "When an agent calls the flow" trigger |
| Basic AI tools (per 10 responses) | 1 | No charge |
| Standard AI tools (per 10 responses) | 15 | No charge |
| Premium AI tools (per 10 responses) | 100 | No charge |
| Content processing (per page) | 8 | No charge |

Rules:
- One interaction can add up several features (example: tenant graph grounding, 10, plus generative answer, 2, equals 12 credits).
- Reasoning models add the feature rate plus the premium rate per 1,000 tokens.
- The inclusion for licensed users applies to internal scenarios (business to employee), with the licensed user's identity.
- Computer-using agents are not included in the license.
- When prepaid capacity runs out, new agent flow runs are blocked; at 125% consumption, custom agents are disabled.
- The GitHub Copilot harness has its own billing model; consult Learn.

## Estimate
Use the Microsoft Copilot Studio agent usage estimator to forecast consumption by agent type, traffic, orchestration, knowledge and tools.

Sources: https://learn.microsoft.com/microsoft-copilot-studio/requirements-messages-management ; https://learn.microsoft.com/microsoft-copilot-studio/billing-licensing ; https://learn.microsoft.com/power-platform/admin/manage-copilot-studio-copilot-credits-capacity
