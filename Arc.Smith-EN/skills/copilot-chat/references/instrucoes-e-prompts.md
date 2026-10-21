# Copilot Basic: instructions for agents without tenant data

- The Base Prompt follows the smith-prompt standard (7 parameters, up to 8,000 characters).
- Without access to SharePoint or uploaded files, the agent works with: its instructions, the web (general or specific sites) and what the user pastes or attaches in the conversation.
- When the case depends on an internal document, instruct the agent to ask the user to attach or paste the content, and not to answer about it before that.
- Scope web search to the needed sites when the source is known (up to 4 URLs in Agent Builder).
- Put in the instructions the rules and fixed knowledge the agent needs, respecting the 8,000-character limit.
- Do not instruct the agent to use features that the feature check did not confirm for Copilot Basic (such as email, Teams, people, SharePoint or skills).
- Never include links in the instructions.
