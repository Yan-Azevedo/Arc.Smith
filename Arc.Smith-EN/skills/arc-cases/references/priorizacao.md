# Use case prioritization

Prioritization chooses which cases move to build now and which are recorded for later. It combines two axes, impact (value) and effort (feasibility), evaluated with the same yardstick for all cases.

## Prioritization principles
- Business value first: no case is prioritized without evident impact.
- Data-driven decisions: use facts and estimates from what was reported, not impressions.
- Transparency: the criteria and the reason for the choice are clear to everyone involved.
- Ethical responsibility: consider privacy, compliance and human impact for each case.

## Evaluation criteria

### Impact (value)
| Criterion | What to evaluate |
|---|---|
| Business impact | Efficiency gains, cost reduction, risk mitigation and strategic alignment. Cases that touch key indicators or main pains have high impact. |
| Frequency and volume | How often the problem occurs. Daily or high-volume processes generate greater impact when improved. |
| Current manual effort | How much time and how many people the process consumes today. The heavier the load, the greater the relief from automation. |
| Quality and errors | Expected quality improvement: eliminating critical human error or standardizing deliverables has high impact. |

### Effort (feasibility)
| Criterion | What to evaluate |
|---|---|
| Technical feasibility | Does the input data exist and is it accessible in a usable format? Does the available platform support it? |
| Implementation complexity | Number of integrations, need for customization and build effort (see complexidade.md). |
| Implementation time | Cases that can be prototyped in days or weeks are preferred over those that take months. |
| Adoption and culture | Would users adopt the solution? Removing a tedious task eases adoption; radically changing the flow creates resistance. |
| Risks and compliance | Regulatory implications, sensitive data and critical failures. Unacceptable risks remove the case or require robust mitigation. |

### How to evaluate
- Give each case a rating on each criterion: High, Medium or Low. If the user prefers, use a 1 to 5 score.
- Consolidate into two results: Impact (combination of the value criteria) and Effort (combination of the feasibility criteria).
- When information is missing to evaluate a criterion, record the gap instead of assuming.
- Whenever possible, validate the impact weights with the business owners.

## Impact x effort matrix
| Quadrant | Reading | Action |
|---|---|---|
| High impact / Low effort | Quick win: great value with little work | Top priority for immediate build |
| High impact / High effort | Strategic but demanding | Prototype a part or plan as a project |
| Low impact / Low effort | Incremental improvement | Do it if it fits, without losing focus |
| Low impact / High effort | Little gain and a lot of work | Do not recommend now; keep it recorded in the report |

The matrix guides, but the final decision also considers the organization's interest and appetite: a very high impact, medium effort case can beat a medium impact quick win if it is strategically more relevant. The general rule is to favor quick wins to build initial traction.

## Good case, feasible case and right case
- **Good case:** there is a clear, relevant problem and a credible hypothesis of an AI solution.
- **Feasible case:** besides being good, it can be implemented with the available data, technology, resources and time.
- **Right case for the moment:** good and feasible, with complexity compatible with the deadline and high impact, to serve as proof of value.

## Decision
1. Present all cases in the selection report, with each one's classification (Adherent or Viable as a project) and, for adherent cases, the build and sustainment complexities.
2. Use the impact x effort matrix to recommend, among the adherent cases, the one with the best balance of value and effort, explaining the trade-offs.
3. The choice belongs to the client: wait for approval before documenting the chosen case.
4. Cases not chosen remain in the report as a record for future initiatives.

## When not to recommend an adherent case
- Lack of strategic alignment: it does not address a priority problem.
- Unavailable dependencies: data that does not exist or is inaccessible, or unavailable infrastructure.
- Sustainment the client will not be able to take on (no owner or no time to maintain it).
- Low buy-in: resistance from those who would need to adopt the solution.

## Opportunities not chosen
The selection report records all cases, including those viable as a project, with pain, what it solves, impact and value. The record values the participants' contributions and creates a pool for future initiatives. Review the recommendation when the context changes, but keep the focus on the chosen case during the build.

## Checklist before closing the prioritization
- All relevant cases were identified.
- Each case has the key information described; what could not be estimated is noted.
- The criteria were applied with the same yardstick for all; different weights were declared.
- The business owners are aligned with the choice.
- The selected case has a well-defined scope and does not depend on solving another problem first.
- The selection report records all cases, including those viable as a project.

## Prioritization pitfalls
- Deciding by intuition, without data or estimates to support the choice.
- Ignoring those who run the process and prioritizing only from the leadership view.
- Selecting too many cases at the same time and diluting focus.
- Classifying as Low complexity something that only looks simple on paper, without evaluating integrations, data quality and the sustainment effort.
- Discarding high impact cases just because they are complex, instead of recording them as viable as a project or slicing the problem.
