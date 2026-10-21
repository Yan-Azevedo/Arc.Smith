# Agent Builder: capabilities and limits

Values verified on 2026-10-19. Confirm in the Microsoft Learn MCP before stating them to the user.

## Agent fields (Configure tab)
| Field | Rule |
|---|---|
| Name | Up to 30 characters. Descriptive and unique. |
| Icon | PNG, up to 192 x 192 pixels and 1 MB. Can be AI-generated, picked from the library or uploaded. |
| Model (response mode) | Auto (default), Quick response or Think deeper. Users can change it when using the agent. |
| Description | Up to 1,000 characters. Helps the model identify when to use the agent and is shown to users. Short, precise and simple. |
| Instructions | Up to 8,000 characters. In the Describe tab, they are generated automatically. |
| Knowledge | Public websites, work content, uploaded files and connectors. Limits by type below. |
| Suggested prompts | Each with a name and description. No documented minimum. |

## Knowledge sources (limit per agent)
| Source | Limit and rules |
|---|---|
| Public websites | 4 URLs. At most two path levels and no query parameters. To use any site, turn on "Search all websites". |
| SharePoint (files, folders, sites) | 100 files. URL with the site path (/sites/name) and no parameters. A site does not include its lists. |
| SharePoint lists | 1 list, up to 20,000 items and 50 MB of text. List attachments are not used. |
| OneDrive | 50 files, by shareable link. |
| Teams | 5 chats and 5 meetings, or "My Teams chats and meetings" (whole history and calendar). |
| Outlook | "My emails": the whole mailbox, no scoping. Users the agent is shared with do not access the creator's email. |
| Uploaded (embedded) files | 20 files. .doc, .docx, .pdf, .ppt, .pptx and .txt up to 512 MB; .xls and .xlsx up to 30 MB. Folders, password-protected files, Double Key Encryption and labels with user-defined permissions are not accepted. |
| Copilot connectors | No documented numeric limit. The administrator must enable them. |
| Dynamics 365 and Power Apps | No documented numeric limit. Requires "Business Applications in Work IQ" enabled. Read only. |

Notes:
- "Only use specified sources" prioritizes the given sources for search questions, but does not block the model's general knowledge. For stricter control, use Copilot Studio.
- Files newly uploaded to SharePoint or OneDrive stay "Preparing" for a few minutes and only enter the answers when ready.
- Excel works best with the data in a single sheet.
- Restricted SharePoint Search, if enabled, prevents using SharePoint as a source.

## Capabilities
| Capability | How to enable |
|---|---|
| Code Interpreter | "Create documents, charts, and code" |
| Image generator | "Create images" |
| Skills (preview) | Availability by level is changing: confirm in the feature check. At the last check, the Learn page mentioned a license or pay-as-you-go billing and the Frontier Program. Through a natural language description (Assistant mode) or a .zip package up to 50 MB in the Configure tab, Skills, Add (Detailed mode). Up to 8 per agent, 25 MB per file, 350 files in total and depth 3. Cannot be combined with uploaded (embedded) files and does not work with Purview Information Barriers. |

Not available in Agent Builder: actions that integrate external services. For that, copy the agent to Copilot Studio.

## Levels
- **Copilot Premium** (Microsoft 365 Copilot license or pay-as-you-go billing turned on): all sources above. Documented exception: email, people, Teams chats and meetings as sources require the Microsoft 365 Copilot license; pay-as-you-go billing alone does not unlock them.
- **Copilot Basic** (Copilot Chat without a license): see the copilot-chat skill.

## Availability
- The natural language experience (Describe tab) supports the languages supported by Microsoft 365 Copilot, including Brazilian Portuguese.
- Available in GCC and GCCH, with restrictions (in GCC there are no uploaded files as a source).

Sources: https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-build-agents ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-add-knowledge ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-regional-availability ; https://learn.microsoft.com/microsoft-365/copilot/extensibility/prerequisites
