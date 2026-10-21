# ForgeProtocol

Prompt engineering methodology used by Smith to build the Base Prompt.

## What prompt engineering is
It is the skill of writing structured instructions that steer the AI to produce answers aligned with the goal. The parameter structure communicates intent in an organized way and makes the model's behavior more predictable. It is especially useful when precision and personalization are essential, such as technical documentation, learning paths and standardized processes.

## Components of a good prompt
Before filling in the parameters, gather these components with the user:

| Component | Question it answers | Example |
|---|---|---|
| Content type | What will be produced? | report, script, summary, analysis |
| Target audience | For whom? | junior analysts, area managers |
| Main goal | What result is expected? | reduce meeting preparation time |
| Specific elements | What must be present? | owners, deadlines, risks |
| Desired characteristics | How should it be presented? | concise, detailed, visually structured |
| Quality criteria | How to measure if it is good? | actionable, measurable, no invented information |

## From components to parameters
| Component | Base Prompt parameter |
|---|---|
| Main goal and quality criteria | Goal |
| Target audience, area and sources | Context |
| Specific elements, constraints and steps | Instructions |
| Desired characteristics (style) | Tone |
| Desired characteristics (structure) | Format |
| Real usage situation | Use Case |
| Final format of the agent | Output |

## Delimiters
| Delimiter | Purpose |
|---|---|
| `{ }` braces | Group the parameters that configure the behavior |
| `" "` double quotes | Delimit the value of each parameter |
| `[ ]` brackets | Indicate variable information or a placeholder to fill |
| `( )` parentheses | Add reinforcing information; use sparingly |
| `:` colon | Relates the parameter to its value |

## Iterative process
1. Initial creation of the Base Prompt.
2. Evaluation of the result produced by the agent.
3. Adjustment of Tone, Format and Instructions.
4. Refinement of Context and output criteria.
5. New round until the result meets the Goal.
