# Project Pulse Dashboard Plan

## Goal
Build a static Project Pulse dashboard that presents each project with its name, owner, status, recent activity, priority, and contributor-friendly summaries. The first screen should be directly usable in a browser from the `app/` directory.

## File Assignments

| File | Owner | Assignment |
| --- | --- | --- |
| `app/index.html` | Coder | Build the accessible dashboard shell and data-driven project-card markup. Reference the stylesheet and project data, expose the required project fields, and keep the document usable at desktop and mobile widths. |
| `app/styles.css` | Designer | Define the responsive dashboard layout, accessible visual hierarchy, readable spacing, status and priority treatments, project-card styling, and the visual rules for `.dashboard`, `border-radius`, and `box-shadow`. |
| `app/project-data.json` | Coder | Define the project data schema and provide the dashboard's project records, including the fields rendered by the HTML. Keep the file valid, deterministic, and easy to extend. |
| `.vscode/launch.json` | Coder | Add a strict launch configuration named `Run Project Pulse Dashboard` that serves `app/` with `python3 -m http.server 5500` and opens `index.html`. |

## Designer Responsibilities

- Shape the responsive layout and information hierarchy in `app/styles.css`.
- Define clear, accessible visual distinctions for project status and priority.
- Establish readable typography, spacing, card structure, focus states, and behavior across desktop and mobile widths.
- Review the HTML structure for usability and accessibility concerns, while keeping implementation ownership with the Coder.

## Coder Responsibilities

- Implement `app/index.html` with semantic, accessible markup and project-card rendering.
- Implement `app/project-data.json` with the agreed schema and representative project records.
- Implement `.vscode/launch.json` with the required server and browser launch settings.
- Integrate the Designer's styling decisions with the HTML and data model.
- Keep the result deterministic and runnable without a build step.

## Dependencies

1. Agree on the data schema and required fields before finalizing the project-card markup.
2. The HTML structure must exist before the stylesheet can be integrated and verified against real content.
3. The launch configuration depends on the completed `app/` path and entry point.
4. Final visual integration depends on both the data-driven HTML and the Designer's CSS decisions.

## Parallel Work Decisions

- The Designer can define the visual system and responsive rules in parallel with the Coder defining the data schema and launch configuration.
- The Coder can prepare `project-data.json` and `.vscode/launch.json` while the Designer works on layout decisions.
- Final HTML/CSS integration must happen after the core markup and data shape are agreed.
- Orchestrator integration review and executable validation must happen after both Designer and Coder work is complete; those steps are sequential.

## Delivery Sequence

1. Planner establishes the data contract, UI requirements, dependencies, and validation checklist.
2. Designer and Coder work in parallel on their non-overlapping assignments.
3. Coder completes the dashboard markup and data integration; Designer completes the responsive styles.
4. Orchestrator reviews the integrated dashboard and resolves contract or ownership mismatches.
5. The integrated result is validated locally and in a browser.

## Validation Expectations

- Parse `app/project-data.json` and `.vscode/launch.json` with `python3 -m json.tool`.
- Confirm the HTML references `styles.css` and `project-data.json`, renders every required data field, and contains the expected semantic structure.
- Confirm the launch configuration is named `Run Project Pulse Dashboard`, serves from `app/` with `python3 -m http.server 5500`, and opens `index.html`.
- Start the launch configuration and verify the browser opens the Project Pulse interface rather than a directory listing.
- Inspect desktop and mobile layouts for overflow, overlap, readable text, visible focus states, and clear status/priority distinctions.
- Run `scripts/validate-exercise.sh` and address any reported structural or content failures.

Use plain Markdown and preserve the exact required file paths. After writing, report the file created and its scope.
