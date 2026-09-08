# Agent team

The Mona's Project Pulse dashboard will be built by a coordinated team of four custom agents:

- **Orchestrator** — uses **Claude Opus 4.7 (copilot)** to coordinate the team, divide the work into phases, assign explicit file scopes, manage dependencies, and verify that the integrated result works together. Definition: `.github/agents/orchestrator.agent.md`.
- **Planner** — uses **Claude Opus 4.7 (copilot)** to research the repository and relevant documentation, identify dependencies, risks, edge cases, and validation needs, and produce an ordered implementation plan. Definition: `.github/agents/planner.agent.md`.
- **Coder** — uses **GPT-5.5 (copilot)** to implement application logic, fix bugs, create required runnable-app support files, and validate deterministic, testable behavior. Definition: `.github/agents/coder.agent.md`.
- **Designer** — uses **Gemini 3.1 Pro (copilot)** to shape the dashboard's UI/UX, accessibility, information hierarchy, responsive behavior, and visual styling, including clear project cards, status badges, priorities, and responsive layout. Definition: `.github/agents/designer.agent.md`.

GitHub Copilot CLI in a Codespace will orchestrate the work: the Orchestrator obtains the Planner's strategy, delegates implementation and design tasks to the Coder and Designer with non-overlapping file ownership, then integrates and verifies the final dashboard. All agents leave staging, committing, and pushing to the learner.

Orchestrator, Planner, Coder, and Designer.
The model assigned to each agent.
The responsibility of each agent.
The .github/agents/ file for each agent.
How the team will work together to build Project Pulse.
