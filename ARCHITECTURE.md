# Autonomous Research Architecture

A human and agent discuss a research idea; the agent translates it into the project brief and initial state. The director then selects useful actions and repeats the evidence-driven loop. The workspace preserves progress across runs. Both canonical prompts are in [README.md](README.md#start-a-project).

```mermaid
flowchart TD
    Discussion["Human–agent discussion<br/>Research idea and relevant context"] --> Setup["Project setup<br/>Agent drafts PROJECT.md and initializes STATE.md"]

    subgraph Workspace["Project Workspace"]
        Files["Project files, persistent state<br/>Sources, analysis, outputs"]
    end
    Setup --> Files

    subgraph Director["Research Director — Autonomous Loop"]
        Uncertainty["Identify key uncertainty"] ==> Choose["Choose next action<br/>Delegate when useful"]

        subgraph Actions["Research Actions"]
            Search["Literature search"]
            Analyze["Analysis / modeling"]
            Test["Hypothesis testing"]
            Verify["Verification / falsification"]
        end

        Choose ==> Search
        Choose ==> Analyze
        Choose ==> Test
        Choose ==> Verify
        Search ==> Evidence["Evidence"]
        Analyze ==> Evidence
        Test ==> Evidence
        Verify ==> Evidence
        Evidence ==> Update["Update State"] ==> Resolved{"Objective Resolved?"}
        Resolved ==>|No: choose next question| Uncertainty
    end

    Files -.->|Start or resume: read saved context| Uncertainty
    Update -.->|Save| Files
    Resolved -->|Yes| Report["Final research report"]
    Resolved -->|Blocked: missing data or experiment| Intervention["Human intervention"]
    Intervention -->|Input supplied| Files

    style Director stroke:#2563eb,stroke-width:3px
```
