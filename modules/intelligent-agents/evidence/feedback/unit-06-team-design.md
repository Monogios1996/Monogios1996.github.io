---
title: Unit 6 — Official Tutor Feedback
permalink: /modules/intelligent-agents/evidence/feedback/unit-06-team-design/
---

# Unit 6 — Group E Design Proposal: Tutor Feedback

**Assessment:** Unit 6 — Team Design Proposal  
**Grade:** **76% (Distinction)**  
**Graded on:** Friday, 11 September 2026, 11:09 AM  
**Graded by:** Angesh Anupam

## Tutor feedback (transcribed from the assessment)

### Knowledge and Understanding of the Topic/Issues Under Consideration (25%)

The submission demonstrates a thorough understanding of multi-agent concepts, with clear comparisons of deliberative and reactive agents, as well as vertical and horizontal architectures. The design is well grounded in established methodologies such as Prometheus and InteRRaP, demonstrating strong theoretical understanding.

### Application of Knowledge and Understanding (25%)

The practical tooling choices are very well justified, with clear reasoning for selecting LangGraph over CrewAI and Microsoft Agent Framework based on the need for explicit state management. The distinction between autonomous agents and supporting infrastructure, such as SQLite and model gateways, is also clearly and appropriately made.

### Criticality (25%)

Critical evaluation is a strong feature of the report, particularly in its discussion of error propagation, state consistency, and the limitations of LLM decision-making. The proposed mitigations, including bounded retries, audit logs, and the use of Plan-and-Execute with ReAct, provide practical ways to address these challenges.

### Structure and Presentation (25%)

The proposal is logically structured, concise, and presented to a high academic standard. The visual elements, including the system architecture and UML sequence diagram, clearly illustrate the workflow, retry logic, and human approval checkpoints.

### What the team did well

1. Your team has provided a strong theoretical basis for your layered hybrid architecture, drawing on both established agent theories and newer LLM approaches. This shows a good understanding of how the different approaches relate to your system design.

2. Your reasons for choosing Prometheus over Gaia and LangGraph over other frameworks are clearly explained. You have considered how these choices would support the actual implementation, rather than just focusing on the theory.

3. The system and sequence diagrams clearly show the main interactions, including retries, escalation back to the Planner and human review points. This makes the overall control flow much easier to follow.

### Guidance for Improvement

1. The report includes useful system and sequence diagrams, but there is no formal static view of the system structure. Adding a UML Class Diagram would help show the main roles, data structures, shared state and messages passed between agents.

2. Your team mentions having a local model as a fallback, but the report does not say which model you would use or what hardware it would require. Specify the model and quantisation level, along with its RAM needs, context limit and relevant performance measures.

3. You set a target of 90% error-free execution, but it is not clear what counts as an error or how accuracy will be measured. Define clear measures for retrieval, hallucinations and citation quality, and explain how your testing process will be used to check the 90% target.

---

## Evidence-based interpretation and later development

*This section is portfolio analysis, not a quotation from the tutor.*

The feedback validates the work I contributed to the team: the system overview and UML sequence diagram were specifically praised for making interactions, retry paths, escalation and approval clear. It also identified a genuine gap in the **static structural documentation**, which lacked a UML class diagram.

The suggestions about model fallback and evaluation were relevant to my subsequent **individual Unit 11 implementation**. That project specified a local **Ollama/Qwen3** fallback and formalised a fixed **12-case structural evaluation**, including the conditions for success. These were useful steps beyond the Unit 6 proposal. They did **not**, however, satisfy all the tutor's recommendations: the evidence does not establish a complete hardware/quantisation/context benchmark or an independent evaluation of retrieval relevance, hallucinations and citation accuracy. The additional UML class diagram is not presented as completed.

**Related evidence:** [Unit 6 Group E design and individual contribution]({{ '/modules/intelligent-agents/evidence/artefacts/unit-06-group-e-team-design/' | relative_url }}) · [Unit 11 individual implementation]({{ '/modules/intelligent-agents/evidence/artefacts/unit-11-academic-research-agent-implementation/' | relative_url }})
