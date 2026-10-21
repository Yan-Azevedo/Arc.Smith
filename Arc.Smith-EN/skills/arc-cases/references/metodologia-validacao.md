# Methodology: testing and validating the solution

## Building, Testing and Validating the Solution (Smith Module)

With a defined and prioritized case, the stage of actually developing and testing the AI solution begins. This module, internally called **Smith**, is the hands-on work of rapid prototyping and validation. The goal is to deliver a working solution (even if a pilot version) that proves the value of the case, ready to be used and evaluated in the real context.

## Testing the Solution

With the first version ready, testing begins:

- **Typical scenarios:** validate how it works with common inputs, similar to real day-to-day ones. Check whether the solution achieves the expected results in these standard cases.
- **Exception scenarios:** test unusual or problematic conditions (missing inputs, different formats, out-of-scope data). Evaluate whether the solution handles them properly (for example, without crashing or producing improper outputs).
- **Manual comparison:** whenever feasible, compare the AI output with the output a human specialist would produce under the same conditions. This helps calibrate quality and identify whether something important is missing or extra in the AI result.
- **Fast iteration:** as problems come up in testing, fix them and test again. This quick back-and-forth (test and adjust) is the best way to evolve the solution in little time.

## Validation with End Users

After internal testing, it is essential to involve real end users again to validate the solution under conditions close to the usage environment:

- **Guided demonstration:** present the prototype to users and explain how it works, in a scenario similar to the real one. Then invite them to try the solution themselves on a typical task.
- **Active observation:** observe how users interact with the solution. Do they easily find how to start and use it? Do they seem confused at any step?
- **Structured feedback collection:** ask about ease of use, quality of the AI output, speed, perceived reliability and whether they see themselves using the solution regularly. Encourage them to also report any suggestions or concerns.
- **Validation with additional cases:** ask users to test the solution in additional scenarios, preferably real situations they remember facing. This checks how broad the prototype's applicability is.

What matters at this stage is identifying and fixing disconnects between the solution and the user's expectations or way of working. All comments and reactions must be recorded to guide the final adjustments.

## Feedback Collection and Final Iterations

Having gathered the users' observations, decide which refinements to make:

- Prioritize changes that fix failures or add something strongly requested by users.
- Keep the team informed: share the adjustments and, if possible, run small demonstrations to show the feedback was addressed.
- Manage ambition: set a limit of iterations within the available time. Aim for a point where the delivered prototype reliably does what is expected and meets the defined criteria, even if it is not yet the perfect, final version. Improvement suggestions that did not fit the current iteration can be recorded for future development.

## Handling Below-Expectation Results

If, even after several rounds of refinement, the solution still does not reach a minimum quality level:

- **Clear communication:** inform those responsible about the limitations found and discuss the options. Managing expectations transparently is essential.
- **Reassess scope or approach:** consider whether the scope of the case can be narrowed to make it more feasible. For example, focusing on one part of the problem or simplifying criteria may allow a more consistent delivery.
- **Future roadmap:** if the desired solution clearly exceeds the current state of the technology or resources, position it as a long-term goal. Document the learning and propose a path (such as gathering additional data, running an in-depth project or waiting for technology to evolve) to get there later.

## Version and Change Control

Even when building a prototype, it is recommended to apply versioning practices:

- Keep copies of the different versions of the prompt or flow as it evolves (v1, v2...).
- Keep a short change log: describe what was changed and why as you iterate. E.g.: *"v0.2 – Prompt adjusted to include the owner's name in the summary after test feedback."*
- This helps track progress and serves as evidence of the iterative process. It also makes it easier to roll back if an adjustment does not have the expected result.
