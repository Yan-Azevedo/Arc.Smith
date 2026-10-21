# Solution type decision

The solution type (prompt, agent or project) is internal reasoning: it guides the classification and the platform choice, but never appears in the case text. The target platform is confirmed with the platform skill and with the Microsoft Learn MCP.

## Solution Type Decision

There is no single format for an AI solution — it can range from an isolated, well-calibrated prompt to a complete agent interacting with multiple tools. The choice depends on the characteristics of the case:

- **Structured prompt:** when the need can be met through a direct interaction with the generative AI model. Example: a command that, given an input text, returns a summary, a suggested reply or a reformatted list.
- **Integrated agent:** when the solution requires several steps, context or queries to data sources. In this case, an AI solution integrated with other tools is built, such as an agent in the productivity ecosystem (email, corporate chat, etc.) that interacts with the user and possibly with internal data before generating the result.
- **Dedicated project:** if the selected case requires an effort far beyond the immediate time or resources (for example, custom software development or complex integration with large-scale corporate systems), it is treated as a long-term project. In that case, the prototype can validate some concepts and outline a roadmap for a future full implementation.

**Technical criteria, Prompt vs. Agent:**

- **Interaction complexity:** a one-off interaction (e.g., a single text answer) tends to be solved with a prompt; flows with multiple questions and answers, or that need to keep context and interact throughout a dialogue, require an agent.
- **Integration with systems:** if the solution needs to read from and write to existing systems (email, files, databases), an agent (for example, using automation services) is more suitable than a prompt alone.
- **Output control and additional actions:** prompts can produce text or simple structured output. If the output needs post-processing or the solution must take concrete actions (such as automatically sending an email), an agent is needed to encapsulate these functions.
