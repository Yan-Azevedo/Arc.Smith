# Copilot Studio: knowledge, tools, topics and instructions

Verified on 2026-10-20. Confirm in the Microsoft Learn MCP.

## Knowledge sources
- Types: public websites, uploaded files, SharePoint, OneDrive, Dataverse, Azure AI Search, real-time connectors, Copilot connectors and unstructured data.
- Each source requires a unique name and a description; a detailed description guides generative orchestration.
- Generative orchestration: up to 25 sites or SharePoint URLs; above 25 sources, the agent filters with an internal model. Uploaded files do not count toward this limit.
- Classic orchestration and the generative answers node: 4 sites, 4 SharePoint URLs, 2 Dataverse sources (15 tables each). Exceeding this limit in the node blocks publishing.
- SharePoint and Dataverse use the user's authentication: the agent only shows what the user can access.
- Documents with sensitivity labels or passwords are not indexed.
- "Tenant graph grounding with semantic search" improves search in SharePoint and connectors; it requires generative orchestration, Microsoft authentication and has an additional cost for users without a license.
- Citations returned by knowledge cannot be used as input to other tools.

## Tools
| Type | When to use | Rules |
|---|---|---|
| Connectors | Integrate services with a ready-made connector (SharePoint, Outlook, Salesforce, ServiceNow, etc.) | Select only the needed actions; review the description |
| Agent flow | Deterministic multi-step processes | "When an agent calls the flow" trigger, "Respond to the agent" action, synchronous response, published, up to 100 seconds |
| Prompt | Specific task with an AI model (extraction, classification, generation) | Defines model, temperature (0 to 1) and inputs; can be used in the agent, the topic or the flow |
| MCP | Own or internal services exposed by an MCP server | Review the name and description of each tool; keep few servers per agent |
| Workflows | Automated processes in the flow designer | Available depending on the harness |

The tool description is what the orchestrator uses to decide when to call it: write when to use it and when not to.

## Topics (standard harness)
- Description-based trigger: write the description explicitly and in detail (example: "Trigger ALWAYS when the user confirms: Yes, I confirm, Go ahead and record"). Vague descriptions make the orchestrator skip the topic.
- Variables passed from one topic to another must be global.
- Use topics when the answer must always be exactly the same.

## Instructions
- Up to 8,000 characters; they accept Markdown and the smith-prompt Base Prompt.
- Type "/" to reference a tool, topic, other agent, variable or Power Fx expression, using the exact name.
- Only instruct the use of tools and knowledge the agent has configured.
- If the agent should not ask the user questions, say so explicitly.
- Do not change the format or behavior of citations.

Sources: https://learn.microsoft.com/microsoft-copilot-studio/knowledge-copilot-studio ; https://learn.microsoft.com/microsoft-copilot-studio/knowledge-add-existing-copilot ; https://learn.microsoft.com/microsoft-copilot-studio/flow-agent ; https://learn.microsoft.com/microsoft-copilot-studio/nlu-prompt-node ; https://learn.microsoft.com/microsoft-copilot-studio/prompt-model-settings ; https://learn.microsoft.com/microsoft-copilot-studio/mcp-add-components-to-agent ; https://learn.microsoft.com/microsoft-copilot-studio/authoring-instructions ; https://learn.microsoft.com/microsoft-copilot-studio/guidance/generative-mode-guidance
