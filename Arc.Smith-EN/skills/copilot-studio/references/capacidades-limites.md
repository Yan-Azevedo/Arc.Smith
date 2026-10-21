# Copilot Studio: harnesses and limits

Verified on 2026-10-20. Confirm in the Microsoft Learn MCP.

## Harnesses (agent runtime)
| Harness | Best for | How it works | Notes |
|---|---|---|---|
| GitHub Copilot harness | Complex, multi-step business processes | Takes a goal, splits it into steps, calls tools and recovers from failures | Creates and edits Word, Excel, PowerPoint and PDF; has skills and memory; publishes to internal teams or external customers; billed in Copilot Credits. It is not the GitHub Copilot service. |
| Standard harness | Rule-based agents and structured conversations | Follows the topics, prompts and paths you define | Predictable behavior; publishes to internal teams or external customers. |
| Copilot chat harness | Extending Microsoft Copilot Chat with organizational knowledge | Connects company knowledge to Copilot Chat | Publishes to internal teams; consumption billing or included in the Microsoft 365 Copilot license. |

Features and documentation vary by harness: many articles state at the top which harness they apply to.

## Agent fields
| Field | Rule |
|---|---|
| Name | Up to 42 characters, no < and > |
| Description | Up to 1,024 characters |
| Instructions | Up to 8,000 characters (agent for Microsoft Copilot) |
| Icon | PNG, 192 x 192 pixels; the docs diverge on size (under 72 KB in one article, 100 KB in another) |

## Copilot Studio limits (web app)
| Item | Limit |
|---|---|
| Knowledge sources | 500 objects per agent (files, folders, articles, sites) |
| Public sites and SharePoint URLs | 25 in generative orchestration; 4 in classic orchestration and in the generative answers node |
| Uploaded files | 500 files, up to 512 MB |
| Topics | 1,000 per agent in Dataverse environments |
| Trigger phrases | 200 per topic |
| Connector payload | 5 MB (450 KB in GCC) |
| Agent flow | Respond within 100 seconds |
| Model response | 5-minute timeout per streamed response |
| Unstructured data sources | Up to 5 different types at the same time |

Sources: https://learn.microsoft.com/microsoft-copilot-studio/harnesses-overview ; https://learn.microsoft.com/microsoft-copilot-studio/authoring-first-bot ; https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/authoring-instructions ; https://learn.microsoft.com/microsoft-copilot-studio/requirements-quotas ; https://learn.microsoft.com/microsoft-copilot-studio/knowledge-copilot-studio ; https://learn.microsoft.com/microsoft-copilot-studio/knowledge-unstructured-data
