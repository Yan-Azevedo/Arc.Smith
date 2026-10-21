# Methodology: identifying and separating use cases

## Identifying, Separating and Prioritizing Cases (Arc Module)

At the heart of the methodology is mapping the opportunities where AI can generate value. In this phase (Arc Module), everything discovered is compiled, possible AI cases are identified, each distinct use case is separated and then it is prioritized which ones are worth working on first, based on impact and feasibility criteria.

The expected result of this phase is a list of well-defined cases ordered by priority, from which one (or more) will be selected for development.

## Identifying AI Opportunities

With the discovery information at hand, a list of potential use cases where AI can bring gains is prepared. In particular, tasks or processes suited to AI improvement are evaluated; they tend to show at least some of the following characteristics:

- **Repetitive and manual:** frequent activities performed repetitively, consuming a lot of professionals' time in operational work.
- **Structured cognitive effort:** tasks that involve analyzing or processing data in a standardized way or based on defined rules (for example, always applying the same criteria to each new document or record).
- **Prone to human error:** long or complex activities, subject to human lapses due to fatigue or limited attention (for example, manual data re-entry, long spreadsheet calculations).
- **Long duration:** processes that require many hours of work or have queues, suggesting that intelligent automation could speed up their completion.
- **Dispersed knowledge:** tasks that require consulting multiple information sources or depend on knowledge spread across several documents or systems, a situation in which AI can consolidate and synthesize data quickly.

## AI Opportunity Analysis Table

To compare the opportunities, it is useful to build a table summarizing the key factors of each possible case:

| AI opportunity | Frequency | Current manual effort | Error proneness | Expected gain with AI | Other factors |
|---|---|---|---|---|---|
| **Monthly consolidation of indicators** (merging spreadsheets from several teams) | Monthly | High (about a day of manual work) | Moderate (copy and formula errors) | High: consolidation in minutes, freeing the team for analysis. | Data already structured in spreadsheets. |
| **Answers to frequent questions about internal policies** (lookup assistant) | Continuous (dozens of queries per week) | Medium (repeated queries to specialists) | Low (answers already standardized) | Moderate: immediate, standardized answers, freeing specialists for complex cases. | Requires an up-to-date, well-structured policy base. |
| **Extraction of fields from received documents** (PDF forms and requests) | Weekly (recurring volume) | High (manual typing of fields) | Moderate (typing errors) | High: less rework and greater accuracy in the extracted data. | Documents must be legible and follow a minimum pattern. |
| **Meeting summary with decisions and pending items** (standardized record) | Weekly | Medium (about 30 minutes per meeting) | Medium (forgotten pending items or items without an owner) | Moderate: quick, standardized record of decisions. | Requires a transcript or notes of the meeting. |

> *Table: fictitious examples of four opportunities, with qualitative estimates of impact and effort.*

## Separating Multiple Cases

Discovery often reveals several ideas for applying AI. Each identified idea must be worked on as an independent case, even if it comes from the same interview or area.

For example, in a conversation with a financial analyst, they may mention both automating payment reconciliation and improving a monthly report — two potential cases revealed at once. It is crucial to separate them into distinct descriptions, each with its own set of information (context, people involved, problems). This separation makes it possible to evaluate the merit of each case individually and decide objectively which ones will move forward.

## Mapping the Current Process (AS-IS)

For each case, first document how the process works today — the AS-IS scenario. List all current steps, who performs them, which tools are used and which information goes in and out at each step.

The AS-IS mapping must reflect the real world, not just the "official" procedure described in manuals or rules. This way, the map will also include informal practices, bottlenecks (points of slowness or queues) and critical points that came up in the interviews.

This mapping helps visualize where AI can make a difference. Pay special attention to the pain points in the current flow — the steps where there is slowness, errors or dissatisfaction. Understanding these pains is essential to plan where AI will add the most value.

## Capturing Exceptions and Variations

When documenting the AS-IS, it is important to include exceptions and variations of the process. Few processes strictly follow a single flow; there are usually deviations or special cases. To identify them:

- Actively ask about unusual situations: *"What do you do if information X is not available?"* or *"How do you handle a request outside the Y standard?"*.
- Note the alternative or informal paths users describe (for example, using auxiliary spreadsheets or manual procedures when the official system fails).
- Show these exception scenarios as branches or notes in the AS-IS mapping. This way, the process is properly represented.

## Designing the Future Process (TO-BE)

With a good AS-IS, design how the process will work with AI integrated — the TO-BE scenario. In this future design:

- **Keep iterations simple:** plan the first version with the minimum changes needed to achieve the main gain. Avoid trying to automate 100% at once (risk of overload).
- **Define AI vs. human roles:** make explicit which steps will be done by the AI solution and which will remain under human responsibility (for safety, validation or decision-making). This preserves trust and control.
- **Consider integrations and data:** identify whether the AI solution will need to connect to other systems or databases. Even if the POC uses sample data, plan what would be needed for a future real integration.

The TO-BE result must clearly show what changes compared with the AS-IS: which activities will be automated, modified or eliminated. This comparison will later be used to communicate the value of the improvement achieved.

## Presenting and Aligning the Cases

After being mapped and analyzed, the identified cases must be presented to the decision makers (managers or leaders involved in the process) for validation. In this presentation, it is recommended to start by briefly recapping the current process and its main problems, connecting them to the AI opportunities raised. Then list each identified case with a title and short description, including comments on expected value and complexity, and highlight the case(s) proposed to move forward.

Getting the agreement and approval of the sponsors or decision makers for the selected case is fundamental. This formal alignment ensures everyone agrees with the chosen focus and understands the reason for the selection. From there, you move confidently to the solution build phase (Smith Module), knowing that a validated, priority goal is being met.
