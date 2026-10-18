---
title: Unit 6 — Group E Team Design Proposal
permalink: /modules/intelligent-agents/evidence/artefacts/unit-06-group-e-team-design/
---

# Unit 6 — Group E Team Design Proposal

**Project:** LLM-Powered Academic Research and Information-Gathering Planning Agent  
**Activity:** Team design proposal  
**Status:** Submitted  
**Evidence type:** Team-produced design, with individual contribution identified below

## Team project and outcome

Group E proposed an intelligent research-planning agent that accepts a high-level academic research goal, develops sub-questions, retrieves scholarly metadata, filters and ranks evidence, checks traceability, and exports a research package after human approval.

The submitted design document specified six agent roles:

1. Orchestrator / Supervisor
2. Planner
3. Academic Retrieval
4. Processing / Ranking
5. Evidence Validator
6. Storage / Export

The team chose a layered hybrid architecture and an adapted Prometheus agent-oriented design methodology. The proposed outer workflow followed Plan-and-Execute, with bounded targeted retries and escalation to replanning after validation failures. LangGraph was selected for its explicit workflow state and control over conditional routing. Crossref and OpenAlex were selected as structured scholarly retrieval sources; Semantic Scholar was optional.

The proposal considered error propagation between components, traceability and shared-state consistency, explainability, source availability and human control. These are *design decisions and intended controls*, not claims that the team document itself was an implemented or tested system.

## My individual contribution — diagrams and consistency checks

My principal responsibility was **diagrams and quality assurance**.

I developed and checked the two graphical design artefacts included in the team submission:

- **Figure 1 — System overview:** the six agent roles, information and control flow, scholarly data sources, supporting technical components, human approval and final output.
- **Figure 2 — UML sequence diagram:** the interaction sequence for a research request, including the successful validation path and the bounded retry / escalation path.

I also reviewed the design for alignment between text and diagrams. In particular, my consistency checks covered:

- consistent naming and sequencing of the six agent roles;
- inclusion of the Orchestrator / Supervisor in both diagrams;
- consistency of the validator's failure, retry and replanning routes;
- separating autonomous agent responsibilities from supporting components such as APIs, the language-model gateway, LangGraph and storage;
- identifying Semantic Scholar as optional rather than a mandatory integration;
- ensuring that the proposed human-approval checkpoint was represented before final export;
- structure, presentation and formatting consistency.

These responsibilities were part of the group's shared design process. I do **not** claim sole authorship of the full team proposal, its research or its architectural choices.

## Design artefacts described in the submitted document

**Figure 1 — System overview:** shows the major agent responsibilities and distinguishes supporting services from the agent roles. It depicts the control and evidence flow leading to a human-reviewed research package.

**Figure 2 — UML sequence diagram:** represents the ordering of interactions during an academic research request. It includes a validation branch, a retry route and escalation when the evidence does not meet requirements.

*The original diagrams are contained in the submitted Group E design document. This portfolio entry describes that original team submission; it is not a replacement or a claim of a new diagram-based implementation.*

## Critical evaluation

A strength of the proposal was its explicit separation of planning, retrieval, processing, validation and approval. Making the failure and retry paths visible in the diagrams also made the intended system behaviour easier to inspect.

The design remained a proposal. Its use of specialised agent roles, proposed control flow and source integrations did not by itself demonstrate runtime reliability. The later individual Unit 11 implementation provided an opportunity to test those ideas and revise them in response to actual provider failures, malformed plans, weak evidence and unsupported summaries.

## Teamwork and learning

The experience required coordinating a visual representation with a document written collaboratively. I learned that diagram consistency is not only a presentation concern: differences in component names, control paths or approval conditions can conceal ambiguous responsibilities and weaken a design's implementability.

## Learning-outcome connection

- **LO1:** Comparing agent architectures and designing clearly differentiated roles.
- **LO2:** Considering technical risks, uncertain retrieval results and bounded remediation paths at design stage.
- **LO3:** Applying design techniques, diagrams and technology-selection rationale; this remains design-stage rather than full implementation evidence.
- **LO4:** Contributing a defined deliverable to a team submission and carrying out cross-document consistency review.

**Related activity:** [Unit 6 — Individual Peer Evaluation]({{ '/modules/intelligent-agents/evidence/artefacts/unit-06-group-e-peer-evaluation/' | relative_url }})

**Later individual continuation:** [Academic Research Agent implementation repository](https://github.com/Monogios1996/llm-academic-research-agent)

*Source: submitted Group E design proposal, “LLM-Powered Academic Research and Information-Gathering Planning Agent”, Unit 6. The original Word document is retained as the source artefact.*
