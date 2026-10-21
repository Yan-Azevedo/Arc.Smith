# Creation Guide by platform

How to adapt modelo-entrega.md to each platform. The screen steps come from the platform skill and from the Microsoft Learn MCP at generation time.

| Platform | Supporting skill | Section 4 (creation) | Section 5 (instructions) | Sections 6, 7 and 8 |
|---|---|---|---|---|
| Agent Builder in Copilot Basic | copilot-chat and copilot-m365-agent-builder | Detailed mode (Configure tab) or Assistant mode (brief in the creation conversation) | Base Prompt in the Instructions field | Features confirmed in the feature check; at the last check, no tenant data |
| Agent Builder in Copilot Premium | copilot-m365-agent-builder | Detailed mode (Configure tab) or Assistant mode (brief in the creation conversation) | Base Prompt in the Instructions field | Sources with Agent Builder limits; "Create documents, charts, and code" and "Create images" capabilities; skills; suggested prompts |
| Agents Toolkit | copilot-m365-toolkit | VS Code project, package files and provision | Base Prompt in instruction.txt | Capabilities in declarativeAgent.json; conversation_starters; technical audience |
| Copilot Studio | copilot-studio | Agent creation, harness, knowledge, tools and topics | Base Prompt in the Instructions field | Copilot Studio sources and tools; cost in Copilot Credits when applicable |
| Copilot Notebooks | copilot-notebooks | Notebook creation | Base Prompt in "Copilot instructions" | Section 6 becomes the reference list; section 7 becomes the notebook outputs; section 8 becomes suggested questions for the chat |

## Rules by platform
- Agent Builder, Assistant mode: in section 4, include the brief in a copy block and the post-creation checklist.
- Agent Builder and Agents Toolkit with skills: in section 4, include how to upload or register each skill and the SKILL.md in a copy block.
- Agents Toolkit: include the files (declarativeAgent.json and instruction.txt) in a copy block and the provision commands; warn that it requires permission to upload custom apps.
- Copilot Studio: include, when applicable, the configuration of flows, topics and tools, and the consumption estimate.
- Copilot Notebooks: warn that a deleted notebook cannot be recovered and that the instructions are visible to those it is shared with.
- In all: name and description within the platform limit, and no screen path without confirmation in Learn.
