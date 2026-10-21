# Copilot Studio: data capture pipeline

Pattern validated in the author's projects (Notedy and Lessons Learned), combined with the official agent flow documentation. Confirm the platform points in the Microsoft Learn MCP.

## Standard architecture
1. Free conversation with the user, guided by the agent's instructions.
2. The agent shows a PREVIEW of the record and asks whether it can record it, and stops in that response.
3. In a separate turn, after confirmation, the agent answers starting with the record phrase.
4. A topic captures the generated response and calls the agent flow.
5. The flow extracts the fields as JSON with a prompt (model with JSON schema output) and writes to SharePoint (Create item) or Dataverse.

## Critical rules
- Confirmation and record in separate turns: if they appear in the same response, the capture breaks.
- Capture start topic: trigger by an explicit description of the confirmation; on confirmation, sets a global variable (example: Global.CanCapture = true).
- Capture topic: "AI response generated" trigger with a condition on the global variable; captures Response.FormattedText, resets the variable and calls the flow.
- Only String, Number and Boolean pass between the agent and the flow.
- A prompt with JSON schema output removes the need for the Parse JSON node.
- The flow must respond within 100 seconds; for long approvals, use an asynchronous pattern.
- Create the flow from the topic ("Add a tool", "new agent flow") so it is created already connected.

## Known limitations
- There is no system variable with the full conversation history.
- System.LastMessage.Text only holds the user's last message.
- Trigger phrases only fire on user messages.
- The "Create generative answers" node is search-based (RAG), does not use the conversation history and can save the answer in a variable (Advanced, "Save bot response as").

## Costs
- Prompt and flow consume Copilot Credits for users without a Microsoft 365 Copilot license (references/licenciamento-creditos.md). Document this cost in the delivery.

Sources: https://learn.microsoft.com/microsoft-copilot-studio/flow-agent ; https://learn.microsoft.com/microsoft-copilot-studio/advanced-use-flow ; https://learn.microsoft.com/microsoft-copilot-studio/nlu-prompt-node ; https://learn.microsoft.com/microsoft-copilot-studio/nlu-boost-node
