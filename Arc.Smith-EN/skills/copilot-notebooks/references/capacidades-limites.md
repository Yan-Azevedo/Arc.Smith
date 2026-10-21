# Copilot Notebooks: capabilities and limits

Verified on 2026-10-20. Confirm in the sources before stating to the user.

## License and creation
- Available to users licensed for Microsoft Copilot and Copilot Chat. The admin documentation diverges (NB-01): confirm in the tenant.
- Creating a notebook requires a SharePoint or OneDrive license (service plan).
- The administrator controls creation through the Cloud Policy "Create and view Copilot Pages and Copilot Notebooks" (enabled by default).

## References
| Item | Copilot Chat | Microsoft Copilot |
|---|---|---|
| Number | Up to 50, all used for grounding | More than 300; only the first 300 used for grounding |
| Sources | Standard: PDF, Word, Excel, PowerPoint, Pages, images, audio, external URLs | Also premium: Teams, SharePoint, OneDrive, internal URLs |
| Entities | Web URL only | Outlook emails, Teams meetings, SharePoint sites and pages, folders |

- File types: .docx, .pptx, .xlsx, .pdf, .loop, .page, .txt and OneNote pages; .rtf and .md appear on different documentation pages (divergence NB-06). Coming soon: .csv, .tsv, .png, .jpg and Teams chats.
- Teams meetings come with transcript, chat and shared content.
- Copilot only uses the content of the references the user has permission to access.

## Custom instructions
- They are in the menu next to the notebook name, in "Copilot instructions"; they can be edited at any time.
- They control the format, focus and tone of the answers.
- People the notebook is shared with see and co-edit the instructions.
- Character limit not documented; ArcSmith adopts 8,000.

## Storage and governance
- .pod file in the user's SharePoint Embedded container, shared with Loop My workspace; counts toward the SharePoint quota.
- No recycle bin: a deleted notebook cannot be recovered.
- No bulk ownership transfer: instructions, references and Pages are recreated manually.
- Information Barriers not supported.
- When sharing, recipients are invited to the linked files (you need permission to share them); conversations with Copilot remain private.

Sources: https://learn.microsoft.com/microsoft-365/loop/cpcn-requirements ; https://learn.microsoft.com/microsoft-365/loop/cpcn-admin-configuration ; https://learn.microsoft.com/microsoft-365/loop/cpcn-compliance-summary ; https://learn.microsoft.com/microsoft-365/loop/grant-access ; https://support.microsoft.com/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook ; https://support.microsoft.com/microsoft-365-copilot/get-answers-and-insights-about-your-microsoft-365-copilot-notebook ; https://support.microsoft.com/topic/763a9536-d459-4f90-8835-c411863d91ce
