# Declarative agent capabilities

Schema 1.8, verified on 2026-10-20. At most one capability of each type.

| Capability | Configuration | Notes |
|---|---|---|
| WebSearch | sites (optional) | The docs say up to 4 sites; 10 were provisioned successfully in the Marchtron project. URL with at most two path segments and no parameters. Without sites, searches the whole web. |
| OneDriveAndSharePoint | items_by_url or items_by_sharepoint_ids | Without either, accesses all content the user can see. Use the full path of the item. |
| GraphConnectors | connections (connection_id and filters) | Without connections, accesses all the organization's connectors. Filters by KQL, ID, URL, path or container. |
| GraphicArt | no parameters | Image generator. Unavailable in GCCH. |
| CodeInterpreter | no parameters | Runs Python, generates charts and downloadable files. |
| Dataverse | knowledge_sources (host_name, skill, tables) | The skill identifier is obtained by publishing an agent in Copilot Studio and downloading the .zip. |
| TeamsMessages | urls (optional) | Up to 5 URLs of channels, chats or meetings. Without urls, searches all. |
| Email | shared_mailbox, group_mailboxes, folders | Read only. Up to 25 group or shared mailboxes. |
| EmailActions | no parameters | Schema 1.8. Email write operations (triage, supervised send, rules, auto-reply, folders). Does not inherit the Email scope. |
| People | include_related_content | People data; with true it includes documents, emails and messages in common. |
| ScenarioModels | models (id) | Task-specific models. |
| Meetings | items_by_id (optional) | Up to 5 meetings. Without items, searches all. |
| MeetingActions | no parameters | Schema 1.8. Scheduling, time polls and calendar insights. |
| EmbeddedKnowledge | files | Up to 10 files of up to 1 MB (.doc, .docx, .ppt, .pptx, .xls, .xlsx, .txt, .pdf). Does not combine with skills in the preview. |

License rule: users without a license only access capabilities beyond WebSearch with pay-as-you-go billing enabled or with a license.

Source: https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-manifest-1.8
