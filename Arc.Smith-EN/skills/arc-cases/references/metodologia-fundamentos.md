# Methodology: fundamentals

ArcSmith's authorial methodology for building AI solutions with Microsoft Copilot: what to build, why to build it and how to deliver value. These criteria guide every decision in the other stages.

## Fundamental Criteria of the Methodology

The following principles are absolute guides of this methodology, working as a decision guide at every stage of building AI solutions:

- **Business value first.** AI solutions must address real problems and generate tangible business benefit.
- **AI as a cognitive extension — not a replacement.** AI exists to expand human capabilities, not to eliminate the role of people or processes.
- **Consulting before technology.** A deep understanding of the context and the problem comes before any choice of tool or technique.
- **Feedback-driven iteration.** Develop incrementally, involving users and adjusting continuously based on real feedback.
- **Simplicity and clarity.** Prefer simple, robust, easy-to-understand solutions; avoid unnecessary complexity and jargon.
- **Ethics and privacy by default.** Consider ethics, transparency and compliance from the design stage, ensuring responsible use of data and AI.
- **End-user focus.** The user experience and the effective resolution of their difficulties drive the design decisions of every solution.
- **Measurable value.** Establish metrics and indicators to evaluate the solution's success and prove the gains achieved.
- **Sustainability and scalability.** Design solutions that are sustainable in the long term and can be expanded and evolved as future demand requires.

| Fundamental criterion | Explanation / Implication |
|---|---|
| Business value first | Each solution is only justified if it addresses a priority problem and generates tangible business benefits (time savings, cost, quality improvement, etc.). |
| AI as a cognitive extension, not a replacement | AI should amplify and improve human work, automating repetitive and complex tasks while keeping people in control for decisions and oversight. |
| Consulting before technology | Before deciding what to build, understand why and for whom; technology selection only happens after the problem and its requirements are clear. |
| Feedback-driven iteration | Develop the solution step by step, test early and often, and incorporate user feedback; this ensures the solution fits reality. |
| Simplicity and clarity | Less is more: prioritize a simple, robust design that is easy to explain and maintain. Direct, jargon-free communication and documentation promote better understanding and adoption. |
| Ethics and privacy by default | There is no value without trust: building in data privacy compliance and ethical principles from the start ensures responsible use of AI and avoids future risks. |
| End-user focus | Solutions must solve users' "pains"; they need to be practical, intuitive and fit into the existing workflow, ensuring greater adoption. |
| Measurable value | Prove value: for every case, success indicators (KPIs) are defined. This makes it possible to measure the impact (before/after) and validate the return on investment. |
| Sustainability and scalability | Think ahead: the solution must be easy to maintain and improve internally, and allow future expansion to more users or cases, ensuring longevity. |

## Fundamentals of Building Solutions

## Methodology Overview

The methodology for building Artificial Intelligence (AI) solutions with Microsoft Copilot is consultative and iterative. It starts with discovery and gathering of needs and context, moves on to identifying and prioritizing opportunities to apply AI (**Arc** phase), goes through the design and rapid build of a working solution (**Smith** phase) and ends with tests, refinements, documentation and delivery.

Throughout each stage, understanding the context and the challenges comes before any technology decision. The central goal is to build solutions that enhance human cognition and solve real challenges quickly and with proven value.

## AI as a Cognitive Extension (not a Replacement of the Process)

We see AI as an extension of human cognition. This means the goal is to amplify people's capacity for analysis, synthesis and decision, not simply to replace existing processes or eliminate human intervention.

AI can automate tedious and repetitive parts of the work, freeing people for strategic, creative and relationship tasks. However, the human factor remains in control and oversees what the AI produces.

**Practical example:** Imagine a service team that has to read dozens of messages every day to identify frequent complaints. With an AI solution, it can be set up to go through the messages and generate a daily summary of the main complaints and suggested solutions. This speeds up problem identification and lets the professionals focus their energy on solving complex cases or offering more personalized service, using the information synthesized by the AI. In this case, AI extends the cognitive capacity of the service team without replacing it — it acts as an intelligent assistant that prepares and organizes data, but the final decision and action remain the responsibility of people.

## Consulting before Technology

Another pillar of the methodology is "consulting before technology": before proposing any tool, the context and the problem must be deeply understood.

The consultant acts as a strategic partner in the business context, deeply understanding the current challenges and workflows. Only after clarifying the real needs is it evaluated which AI technology (for example, a structured prompt, an integrated agent or even a larger-scale solution) can meet the demand.

This stance avoids hasty solutions that do not solve the central problem. It also strengthens trust in the approach, by showing that the priority is solving problems and adding value, not just implementing tools for novelty's sake.

## AI Maturity Journey

To properly position the solution and its implementation plan, the AI maturity journey is considered. This journey usually goes through five stages:

1. **Curiosity:** the organization becomes interested in AI but does not use it yet or is not clear on how to apply it.
2. **Basic use:** the organization experiments with AI in small uses, possibly in a one-off or isolated way, without much structure or strategy.
3. **Conscious use:** the organization already identifies suitable areas for AI, understanding its benefits and limits. It starts to integrate AI into certain tasks more systematically.
4. **Strategic use:** AI becomes part of key processes, with leadership support and clear improvement and innovation goals.
5. **Scalable use:** the organization develops the culture and infrastructure to expand AI use at scale, replicating learnings across multiple areas and seeking continuous improvement.

This journey is a reference to calibrate the implementation strategy. In the early stages (Curiosity and Basic use), the focus is on simple, direct demonstrations of AI's potential; in the more advanced stages, strategic impact and scalability are discussed, since the organization already aims to integrate AI broadly and sustainably.

## Difference between Idea, Case, POC, Prompt, Agent, Project

Throughout the process, different terms are used to define stages and formats of AI solutions. It is essential to understand and differentiate these concepts to use the terminology correctly:

| Term | Description |
|---|---|
| **Idea** | An initial insight about a possible application of AI. It comes from a perceived need or problem, but without detailed analysis or validation of relevance and feasibility. |
| **Case** | A specific, well-scoped use case identified as an opportunity to apply AI. It derives from an already qualified idea, described in a real business context, with clear goals and well-defined problems. |
| **POC (Proof of Concept)** | An experimental, small-scale implementation of a case, created to quickly validate the feasibility and value of an AI solution before a larger investment. It has a narrow scope and focuses on showing quick results. |
| **Prompt** | A structured instruction, in natural language, to guide a generative AI model. A well-crafted prompt can produce useful, consistent results without programming. |
| **Agent** | A more complex, multi-step AI solution, orchestrating several AI calls or integrating with other tools. A typical agent can perform sequential tasks (e.g., read a document, extract data and send an email automatically). |
| **Project** | A larger initiative involving formal planning, dedicated teams and possibly custom software development or system integration. Often, an initially identified case becomes a project if it requires more effort and investment than a simple POC. |

## Role of the Consultant

The consultant (or the professional responsible for the solution) usually plays several synergistic roles in the process:

- **Solution architect:** designs the strategy to place the AI solution in the organization's context, ensuring fit with the needs gathered and alignment with the overall goals and culture of the organization.
- **Facilitator:** runs the activities (interviews, discussions, validations) in an organized way, ensuring all relevant voices are heard and that the collaborative process stays fluid and productive.
- **Translator:** converts business language into AI technical requirements (and vice versa), ensuring that identified needs become specifications the technology can understand and that technical results are communicated in accessible language.
- **Journey designer:** plans the complete implementation and usage experience, from initial mobilization to user training and considerations for future expansion. This role involves orchestrating the process transformation step by step, always focused on value and user engagement.

## Non-Negotiable Principles in Practice

Applying the methodology successfully requires following some principles that cannot be compromised:

- **Business value first:** every proposed solution must generate a clear, measurable benefit (e.g., time savings, fewer errors, better quality). If the value is not clear, do not move forward.
- **Ethics and privacy ensured:** ensure the AI solution respects ethical and privacy standards. Sensitive data must be protected and the AI's behavior must align with relevant policies and rules.
- **Simplicity and clarity:** always prefer the simplest, most understandable solution that solves the problem, avoiding unnecessary complexity. Likewise, communicate ideas without jargon or ambiguity.
- **Iteration with feedback:** gather constant user feedback during development. This ensures the final solution meets real expectations and needs, adjusting as necessary.
- **Co-creation with users:** involve end users in the design and validation phases. When users feel part of the development, the chance of adoption increases and the solution tends to fit real use better.
- **Respect for the human context:** evaluate not only technical feasibility but also the social and operational context. Do not push AI where it does not fit well; consider the existing culture and processes and plan changes gradually and respectfully.
