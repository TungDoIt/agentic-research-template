# Autonomous research template

A small, tool-agnostic workspace for investigating a question, testing explanations, and producing an evidence-backed answer. Plain Markdown preserves the investigation across agents and interruptions. A capable agent with suitable research tools performs the work; this template does not itself run an agent or schedule background work.

## Start a project

1. Copy this template into a new project directory, or create a repository from it. Start with the blank template files, not the state of a previous investigation. `starter prompt.txt`, if present, is the template's design brief and is not needed in new projects.
2. Edit [PROJECT.md](PROJECT.md). Only the objective is required. Add private context, supplied-file links, constraints, or a stopping limit if they matter. The agent derives practical success criteria and discovers public background itself.
3. Open the directory in a capable research agent and send:

   > Read AGENTS.md and start or resume the research defined in PROJECT.md.

For example, an objective could be: “Which of the two supplied calibration methods better explains the drift in our sensor measurements?” Two short paragraphs about the apparatus and known anomalies, plus a link to the measurements, are sufficient context. Do not write a literature review or a research plan to get started.

## Files and ownership

| File | Owner | Purpose |
| --- | --- | --- |
| [PROJECT.md](PROJECT.md) | Human | Objective, context, constraints, and links to supplied materials. |
| [AGENTS.md](AGENTS.md) | Template maintainer | Operating instructions, evidence conventions, and stopping rules. |
| [STATE.md](STATE.md) | Agent | Current answer, uncertainty, alternatives, and a concrete handoff. |
| [evidence/RECORDS.md](evidence/RECORDS.md) | Agent | Traceable evidence and consequential decisions. |
| [outputs/REPORT.md](outputs/REPORT.md) | Agent | Final synthesis; initially an explicitly unfinished outline. |
| [README.md](README.md) | Template maintainer | How to use the project. |

Add folders only when useful:

- `inputs/`: human-supplied context and original data; preserve originals.
- `evidence/sources/`: permitted source copies or extracts that need local preservation.
- `analysis/`: calculations, scripts, derived data, models, and their run instructions.
- `outputs/`: the final report and any supporting figures or deliverables.

The agent normally edits state, evidence, analysis, and outputs. It preserves the human brief and supplied originals. Large investigations may split evidence into linked topic files; they retain the same entry point and stable record links. No database, package installation, or fixed research pipeline is required for the core template.

## Progress, interruption, and completion

Read [STATE.md](STATE.md) for the current interpretation and highest-value next action. Follow its evidence links to audit important claims. Its status describes the last saved checkpoint, not whether an agent process is currently running. Evidence records distinguish observations, source results, calculations, and interpretations; decision records explain major changes without recording private reasoning traces.

To resume, use the same launch prompt. A fresh agent reads `AGENTS.md`, `PROJECT.md`, and `STATE.md`, then only the records and artifacts needed for the next action. It verifies unfinished work before repeating it. If the host ends a run or loses context, restart with that prompt; the files provide continuity within the host's execution limits.

The agent handles routine reversible decisions. It asks for human input when essential inaccessible information, a consequential preference, changed scope, or an action requiring authorization prevents progress. Existing authorization continues to apply, and independent useful work can continue while an answer is pending.

A finished project has a synthesis in [outputs/REPORT.md](outputs/REPORT.md) and a matching state checkpoint that explains why investigation stopped. Outcomes may be an answer, a qualified answer, surviving alternatives, a negative result, or a currently unresolvable question. A reached budget can also end a run with an explicitly incomplete result. A temporary blocker is marked `blocked` and includes the exact input needed to resume. None of these statuses implies certainty.
