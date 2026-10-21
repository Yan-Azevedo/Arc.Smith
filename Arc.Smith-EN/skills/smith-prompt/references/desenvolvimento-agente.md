# Iterative agent development

When the solution requires an agent (several steps, knowledge sources or tools), development is incremental.

## Stages
- Flow outline: define the steps the agent performs (e.g., receive the request, search data in a source, generate the answer, format and return it).
- Platform choice: load the skill of the target platform to confirm fields, sources and limits.
- Build in parts: first make the agent complete the main interaction; then add sources, tools and improvements.
- Test in stages: validate each part in isolation (knowledge source, tool, answer) and then the full flow.
- Exception handling: define how the agent reacts to errors and unexpected conditions (missing data, empty answer, unavailable source), always informing the user clearly.

## Test cycle recommended by Microsoft
1. Create the instructions and the starter prompts.
2. Publish the agent in the test environment.
3. Test: compare the answers with those of Copilot without the agent, check the starter prompts, confirm the agent follows the instructions and handles requests outside the starter prompts.
4. Iterate on the instructions and, if needed, on the knowledge sources.
