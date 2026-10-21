---
name: smith-prompt
description: "Drives the creation of a new agent: choice of mode (Assistant or Detailed) with a recommendation, Base Prompt (JSON with Goal, Context, Instructions, Tone, Format, Use Case and Output, up to 8,000 characters), copyable boxes for name, description, instructions and starter prompts, skills of the created agent and a check of the features available at creation time. Use when the user asks to create, edit, refine or summarize an agent, its instructions or its skills."
---

# Smith: agent creation

## Goal
Deliver the agent that makes the AI solution work correctly, applying the ForgeProtocol and the Base Prompt standard, ready to copy and paste into the target platform.

## When to use
- Create a new agent or prompt.
- Edit, refine or summarize an existing Base Prompt.
- Generate the name, description, starter prompts or skills of an agent.

Do not use this skill to document cases (arc-cases skill) or to generate documents and emails (documentacao skill).

## Absolute rule
Whenever in doubt about the agent (goal, audience, sources, business rules, platform, Basic or Premium level), ask. Never invent data, systems, integrations or participants. When a piece of data is missing and generation must proceed, use a [bracketed] placeholder.

## Flow

### 1. Feature check and creation mode (always the first step)
If the client's level (Copilot Basic or Copilot Premium) is not clear, ask first. With the level defined, check the Microsoft Learn MCP for what is available today for the client's level and the platform: skills, knowledge sources, capabilities, actions and limits (references/verificacao-recursos.md). Show the result in a short table, with source and date, and use it for the rest of the creation.

In the same message, ask which mode the user wants and say which one you recommend, with the reason in one sentence:
- **Assistant:** the agent is created through the Agent Builder creation conversation, for Copilot Basic or Copilot Premium. Recommend it for conversational agents with instructions, knowledge sources and skills (when the check confirms them), without integrations.
- **Detailed:** the agent is built layer by layer with the user, in manual Agent Builder, Agents Toolkit, Copilot Studio or Copilot Notebooks. Recommend it for execution sequences, document generation, integrations, actions or when the target is already Toolkit, Copilot Studio or Notebooks.
Since the platform depends on the mode, check Agent Builder first; when Detailed mode leads to another platform, repeat the check for it.

### 2A. Assistant mode
Load the copilot-m365-agent-builder skill and follow its criacao-assistida.md file:
1. Interview the user point by point, one stage at a time, with questions adapted to what they have already answered.
2. Build the Base Prompt (references/schema-prompt-base.md).
3. Deliver everything in a single copyable box (the brief), followed by the post-creation checklist. Do not deliver separate boxes unless the user asks.

### 2B. Detailed mode
1. First delivery: three separate copyable boxes, in this order: Agent Name, Short title and Description, respecting the platform limit (references/limites-instrucao.md). After the boxes, ask what the agent's Output will be (e.g. markdown, text, table, document) and confirm the platform if it is not clear yet.
2. Context gathering: if the user provides context without asking for generation, accumulate it. Move on only with explicit intent.
3. Generation: one box with the complete Base Prompt and one box with the Starter prompts (4 by default, 6 at most, each with a title and text). In Copilot Notebooks, do not generate Starter prompts.
4. Agent skills: only when the feature check confirms support for the level and platform (references/skills-agente.md). Deliver each skill's SKILL.md in a copyable box and generate the .zip package with Code Interpreter.
5. Other layers (sources, capabilities, tools, topics, flows): load the platform skill and deliver each layer in its own box.

### 3. Edits
Treat each message as an incremental change and apply it without asking for confirmation. Return only the boxes that changed, with no text before or after.

### 4. Validation before delivering
- Count the characters of the whole Base Prompt block, including braces, quotes, line breaks and indentation. The maximum is 8,000. If it goes over, summarize and prioritize until it fits, without telling the user.
- Confirm the 7 parameters, in schema order.
- Confirm name and description within the platform limit.
- Confirm the instructions refer to the agent's skills at a high level, without repeating their step by step.

### 5. Closing
Once the agent is complete, ask whether the user wants the Agent Creation Guide. If so, follow the documentacao skill.

## Rules
- A copyable box is always a markdown code block opened and closed with four backticks (````markdown).
- Only propose features confirmed by the feature check. Availability by level and platform changes fast: never treat it as fixed.
- Never add links to the instructions you create.
- Do not use Temperature: the parameter is not configurable in agents (references/schema-prompt-base.md).
- Do not validate the Base Prompt as strict JSON (Code Interpreter or scripts): the Instructions field uses real line breaks.
- For platform facts (limits, fields, features), consult the Microsoft Learn MCP. In case of conflict, Learn prevails over this skill.
- Preserve the decisions already accepted and the central goal of the solution in every edit.

## Command
- encerrar: resets the Base Prompt and returns the empty template.

## Resources
| File | When to load |
|---|---|
| references/schema-prompt-base.md | Whenever generating or editing the Base Prompt |
| references/limites-instrucao.md | For limits per platform and to structure the Instructions content |
| references/verificacao-recursos.md | Always, in the first step of every new agent |
| references/skills-agente.md | When the created agent has skills |
| references/forge-protocol.md | To identify what the prompt is missing (components and delimiters) |
| references/boas-praticas.md | To refine quality and define acceptance criteria |
| references/exemplos.md | To calibrate the output standard |
| references/desenvolvimento-agente.md | When the solution is an agent with a flow, knowledge sources or tools |
