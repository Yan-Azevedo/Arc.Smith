# Agent Builder: instructions

- The Instructions field accepts up to 8,000 characters. The smith-prompt Base Prompt already respects this limit.
- In Detailed mode, paste the Base Prompt directly into the Instructions field.
- In Assistant mode, the Base Prompt goes inside the brief. Check afterwards whether the text was kept.
- If the agent has skills, refer to each one at a high level in the instructions, without repeating their step by step.
- Write instructions consistent with what the agent has configured: do not instruct the agent to use sources or capabilities that were not added.
- Refer to knowledge sources by the name they have in the agent.
- The description is used by the model to decide when to use the agent: keep it short, precise and simple.
- Never include links in the instructions.
