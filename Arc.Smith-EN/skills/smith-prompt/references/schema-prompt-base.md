# Base Prompt schema

The Base Prompt is the content that goes into the agent's instructions box. It is written as JSON, delivered inside a markdown box, and the platform reads it as text.

## Official template

```
{
  "Parameters": {
    "Goal": "",
    "Context": "",
    "Instructions": "",
    "Tone": "",
    "Format": "",
    "Use Case": "",
    "Output": ""
  }
}
```

## Parameters (fixed order)

| Order | Parameter | Content |
|---|---|---|
| 1 | Goal | Specific, measurable goal of the agent: the result it must deliver. |
| 2 | Context | Application scenario: target audience, area, available knowledge sources and environment constraints. |
| 3 | Instructions | Rules and steps the agent follows. One rule per line. |
| 4 | Tone | How the agent communicates (e.g., formal, consultative, technical, didactic). Also expresses the expected degree of precision or creativity. |
| 5 | Format | Structure of the agent's answers (e.g., list, table, sections, step by step) and level of detail. |
| 6 | Use Case | Practical situation in which the agent is used, preferably with a concrete example. |
| 7 | Output | Final output format of the new agent (e.g., markdown, text, table, yaml). Comes from the mandatory question of the first response. |

## Writing rules
- Always the 7 parameters, in this order, even if one of them is short.
- Values in double quotes.
- Never use `\n` inside the values.
- Running text by default. In Instructions, when there are several rules, put one rule per line, inside the same quotes:

```
"Instructions": "Rule 1.
Rule 2.
Rule 3."
```

- This format is not strict JSON, because it has real line breaks inside the quotes. It is made for the instructions box, which reads text. Do not validate it with a JSON parser.
- Do not use Temperature. In Microsoft 365 Copilot agents (Agent Builder and Agents Toolkit) and in Copilot Studio agents, the parameter is not configurable. It exists only in the Copilot Studio Prompt tool (prompt builder), as a 0 to 1 control, and is disabled for reasoning models. The desired effect (more precise or more creative) is described in Tone and Instructions.

## Limit
The whole block has at most 8,000 characters, counting braces, quotes, line breaks and indentation.

## Output criteria (Output and Format)
Clearly define what success means for the agent:
- Mandatory content: which information the answer must contain (e.g., "the three main causes, in order of priority").
- Format and style: list, table, paragraphs or another format the agent must follow.
- Level of detail: brief or in depth, and scope limits.
- Exception condition: how the agent reacts when it cannot complete the task (e.g., answer "Insufficient data for analysis" instead of guessing).
