---
title: Unit 11 — Individual Academic Research Agent Implementation
permalink: /modules/intelligent-agents/evidence/artefacts/unit-11-academic-research-agent-implementation/
---

# Unit 11 — Individual Academic Research Agent Implementation

**Assignment:** Individual system implementation and presentation  
**Module:** Intelligent Agents  
**Project:** LLM-Powered Academic Research and Information-Gathering Planning Agent  
**Status:** Submitted  
**Source code and technical evidence:** [LLM Academic Research Agent repository](https://github.com/Monogios1996/llm-academic-research-agent)

## Purpose and relationship to the Unit 6 design

For the individual Unit 11 deliverable, I implemented and evaluated a working prototype based on the [Group E Unit 6 design proposal]({{ '/modules/intelligent-agents/evidence/artefacts/unit-06-group-e-team-design/' | relative_url }}).

The team proposal defined an academic research agent intended to take a high-level research goal, break it into searchable questions, retrieve and assess scholarly evidence, and require human approval before producing an offline research package. My Unit 6 contribution had focused mainly on the system and UML diagrams and on consistency between the diagrams and written design. Unit 11 moved from this team-produced specification to the **individual implementation, testing, remediation and demonstration** of the system.

The prototype was deliberately scoped as an academic research **planning and evidence-gathering tool**, not an autonomous author of academic conclusions. It produces evidence for a person to review, rather than treating language-model output as a verified source.

## Implemented architecture

The final implementation uses **Python and LangGraph** to organise six logical responsibilities. These are functional components of a controlled agent workflow; they should not be confused with six fully independent, unrestricted agents.

| Responsibility | Implemented behaviour |
|---|---|
| Orchestrator / Supervisor | LangGraph state, routing, bounded retries, bounded re-planning, and workflow termination |
| Planner | LLM-supported decomposition of the research goal into structured, focused subtasks |
| Academic Retrieval | Structured metadata retrieval through Crossref and OpenAlex |
| Processing / Ranking | Deterministic deduplication and lexical relevance ranking |
| Summarisation / Validation | Constrained summaries, grounding safeguards and checks on evidence relevance, sufficiency and traceability |
| Persistence / Export | SQLite workflow checkpoints, JSON run telemetry, and human-approved Markdown, JSON and CSV export |

The primary hosted language-model gateway uses Hugging Face Inference Providers. Following live integration difficulties, the prototype gained an optional local Ollama fallback using `qwen3:4b`. The user can run the workflow through a command-line interface or the minimal Streamlit demonstration interface.

**Design principle:** The LLM supports flexible planning and summarisation; deterministic code governs retrieval handling, ranking, validation, control limits and export. This makes key workflow decisions easier to inspect and test.

**Implementation references:** [Final system overview](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/docs/final-system-overview.md) · [LangGraph orchestration](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/src/research_agent/orchestration.py) · [Data models](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/src/research_agent/models.py)

## Workflow and bounded autonomy

The implemented workflow follows this sequence:

```text
Research goal
  → structured plan and subtasks
  → Crossref / OpenAlex retrieval
  → deduplication and relevance ranking
  → evidence summarisation
  → validation
     ├─ pass → next subtask / completed evidence package
     └─ fail → targeted bounded retry
                 → bounded re-planning if necessary
                 → structured failure if unresolved
  → awaiting_approval
  → explicit human approval
  → Markdown / JSON / CSV export
```

Validation feedback is used to guide limited retries rather than allowing repeated calls without a stopping condition. The workflow can also terminate with a structured failure if the evidence requirements remain unmet.

The design intentionally places the approval checkpoint **after evidence has been collected and validated but before the consequential export action**.

## Human-approval and traceability control

Successful workflow execution ends at `awaiting_approval`, where the user can inspect the research plan, retained sources, traceability information, relevance scores, summaries and audit trail.

Export is separate from the LangGraph workflow. The export function itself checks **both** that the workflow is in the `awaiting_approval` state and that the caller has explicitly approved the action. If either check fails, no research package is written. The CLI and Streamlit interface reuse this guarded export function, rather than implementing a weaker UI-only approval control.

After approval, the same research package can be exported to **Markdown, JSON and CSV**.

**Implementation references:** [Approval/export design note](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/docs/approval-export.md) · [Export implementation](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/src/research_agent/exporter.py) · [Streamlit implementation](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/src/research_agent/streamlit_app.py)

## Development, failures and improvements

The project includes a chronological development record rather than only a polished final demonstration. Several problems encountered during testing led to specific changes:

| Observed problem | Implementation response |
|---|---|
| Hosted-model/provider or credit-related failures | Added and verified a local Ollama/Qwen3 fallback route |
| Local planner returned malformed structured output or too few subtasks | Added schema-constrained JSON output and explicit planning contracts |
| Duplicate papers appeared across subtasks | Added cross-subtask deduplication |
| Weakly related academic records passed basic matching | Strengthened topic-aware lexical relevance filtering |
| Summaries included unsupported benchmark or dataset details | Added grounding checks, deterministic no-abstract handling and source-based fallbacks |
| Truncation produced incomplete sentences | Added sentence-aware truncation |
| A live `HttpUrl` conversion caused a type error | Added explicit URL normalisation and regression coverage |
| SQLite checkpointing initially failed on Pydantic records | Adjusted serialization and tested checkpoint reopening with real domain objects |

The most useful lesson was that passing unit tests did not eliminate the possibility of live provider, serialization, retrieval or grounding failures. The implementation changed in response to observed behaviour.

**Development references:** [Chronological development timeline](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/docs/development-timeline.md) · [Critical evaluation](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/docs/critical-evaluation.md) · [Recorded test and remediation evidence](https://github.com/Monogios1996/llm-academic-research-agent/tree/main/evidence/test-results)

## Testing and evaluation

The submitted repository reports the following completed verification:

| Evidence | Reported outcome | What it establishes |
|---|---|---|
| Automated suite | **83 passing tests** | Unit/integration coverage of contracts, routing, retrieval, ranking, validation, failover, persistence, telemetry and export |
| Fixed live evaluation | **12/12 structurally successful cases (100%)** | The tested workflow met its structural pass criteria across a varied set of research requests |
| Predefined target | **At least 90%** | The reported 12-case structural success rate exceeded the stated target |
| Browser demonstration | Approval boundary and approved export verified | The Streamlit interface can display reviewable evidence and invoke the guarded export path |

For the fixed 12-case evaluation, structural success required a completed `awaiting_approval` state, at least two subtasks, at least two evidence items, at least 75% traceability, a passing validator and no unhandled exception. The recorded final live runs performed better than those thresholds: each retained at least five evidence items and reported 100% traceability.

**Important limitation:** **100% structural success is not 100% semantic or factual accuracy.** A source can be traceable but imperfectly relevant, and safeguards cannot guarantee that every generated statement is correct. The recorded figures are therefore evidence of workflow reliability under the tested conditions, not a general claim of perfect academic research quality.

**Testing references:** [Automated tests](https://github.com/Monogios1996/llm-academic-research-agent/tree/main/tests) · [12-case evaluation manifest](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/evaluation/cases.json) · [Evaluation runner](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/src/research_agent/evaluation.py) · [Recorded full evaluation](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/evidence/test-results/2026-10-10_end_to_end_evaluation_harness.md)

## Demonstration and submission evidence

The Unit 11 presentation showed the initial research goal, the implemented agent workflow, tests and remediation, the evidence available at the human-approval boundary, and the result after approved export. The PowerPoint deck, accompanying spoken transcript and recorded presentation were submitted separately for the university assessment.

The public project repository also contains the implementation, documentation, [demonstration evidence](https://github.com/Monogios1996/llm-academic-research-agent/tree/main/evidence) and [assessment evidence mapping](https://github.com/Monogios1996/llm-academic-research-agent/blob/main/docs/assessment-evidence-mapping.md). The submitted recording is **not** republished on this public portfolio page.

## Critical evaluation and limitations

**Strengths:** Explicit state transitions; source identifiers and auditability; structured scholarly retrieval; bounded retries/re-planning; human-controlled export; and local inference fallback when the hosted route is unavailable.

**Limitations:** Ranking remains primarily lexical, so it can miss relevant papers with different terminology. Crossref and OpenAlex records vary in completeness and may lack abstracts. The local model depends on the user's hardware and runtime environment. Grounding safeguards target observed errors but do not prove full factual correctness. The Streamlit UI is a demonstration, not a production service, and the 12-case evaluation does not replace independent, manually judged semantic evaluation.

**Future work:** Semantic retrieval, stronger claim-level source verification, provider usage accounting, improved recovery from interrupted runs and a larger human-reviewed evaluation set.

## Assessment result and tutor feedback

**Grade:** 76%, awarded 16 October 2026 by Angesh Anupam.

The tutor recognised the substantial LangGraph implementation, explicit division between model reasoning and deterministic safeguards, systematic failure remediation, tests and candid distinction between structural reliability and research accuracy. Areas identified for further development included independently measured retrieval and factual quality, comparison of architectural alternatives, more recent empirical research, and clearer presentation/screenshots.

**Evidence:** [Full Unit 11 official feedback and assessment marks]({{ '/modules/intelligent-agents/evidence/feedback/unit-11-individual-implementation/' | relative_url }})

## Learning and learning-outcome mapping

The project showed me that reliable agent behaviour comes not only from language-model capability but from the architecture and deterministic controls around it. In particular, structured planning, limited retry budgets, traceable evidence, grounding safeguards, tested persistence and explicit human approval were necessary to make the system inspectable.

- **LO1 (supporting):** Applied and refined the role-based architecture developed in the team design.
- **LO2 (primary):** Implemented and evaluated a goal-directed agent workflow in the presence of uncertain sources, provider failures and validation failures; documented the trade-offs and unresolved risks.
- **LO3 (primary):** Used Python, LangGraph, scholarly APIs, model gateways, Pydantic, SQLite, testing and a Streamlit demonstration interface; evaluated reliability, human oversight and professional limitations.
- **LO4 (linked through Unit 6):** The team contribution is evidenced by the separate [Group E design proposal]({{ '/modules/intelligent-agents/evidence/artefacts/unit-06-group-e-team-design/' | relative_url }}). The Unit 11 implementation was individual work and is not presented as a team deliverable.

**Original technical artefact:** [Browse the submitted implementation repository](https://github.com/Monogios1996/llm-academic-research-agent).
