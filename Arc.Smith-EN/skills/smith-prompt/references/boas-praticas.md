# Prompt engineering best practices

## When writing
- Be specific: vague prompts produce vague answers.
- Provide the goal and target audience.
- Use imperative voice ("List the three main risks", not "What would the risks be?").
- Ask for the format explicitly when the output must be a list, table or another pattern.
- Provide enough context: scenario and, when useful, an input example.
- Review and simplify: a concise prompt is easier to understand.
- Tailor tone and format to each scenario.

## When building iteratively
- Start with the Base Prompt containing goal, context, task and format.
- Test with real or simulated examples and check whether the output follows the requested format.
- Refine: add what was missing, simplify what confused the model and include an answer example when the pattern is not being followed.
- Repeat until the Goal is met. Prompt engineering is a continuous process.
- Document the prompts that worked, for reuse.

## Acceptance criteria
Before considering the prompt ready, confirm:
- The mandatory content appears in all test answers.
- The format is followed without variation.
- The level of detail matches the request.
- The agent reacts correctly when data is missing (it does not invent).
