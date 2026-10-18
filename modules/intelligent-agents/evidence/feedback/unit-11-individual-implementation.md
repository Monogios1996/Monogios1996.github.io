---
title: Unit 11 — Official Tutor Feedback
permalink: /modules/intelligent-agents/evidence/feedback/unit-11-individual-implementation/
---

# Unit 11 — Individual Implementation: Tutor Feedback

**Assessment:** Unit 11 — Individual System Implementation and Presentation  
**Grade:** **76%**  
**Graded on:** Friday, 16 October 2026, 8:57 PM  
**Graded by:** Angesh Anupam

## Tutor feedback (transcribed from the assessment)

### 1. Knowledge and Understanding (25%)

The work demonstrates excellent understanding of intelligent agent concepts through a comprehensive LangGraph-based system combining LLM-powered planning, academic retrieval, evidence validation and human oversight. The implementation of bounded retries, re-planning and fallback from hosted to local models shows strong technical judgement. The separation of LLM reasoning from deterministic processing is particularly well considered. However, stronger evidence of planning effectiveness and independently verified research accuracy would further strengthen the technical contribution.

### 2. Presentation and Communication Skills (30%)

The presentation is logically organised and explains the system's architecture, implementation and evaluation clearly. The architecture diagram and screenshots showing the human approval process are particularly useful, while the narration demonstrates good familiarity with the implementation. However, some slides contain spelling errors, inconsistent formatting and screenshots that are difficult to read. Parts of the explanation are also repetitive or lack precision. More concise delivery and clearer presentation of measured system performance would improve communication.

### 3. Criticality (25%)

The work shows excellent critical reflection, particularly in identifying and addressing model failures, malformed outputs, duplicate records, weak relevance and unsupported summaries. The introduction of structured planning, deterministic safeguards and local model fallback demonstrates thoughtful responses to these problems. The recognition that the reported 100% structural success rate does not establish semantic accuracy is especially important. However, quantitative evaluation of retrieval relevance, factual accuracy and alternative architectural approaches would provide stronger evidence for the conclusions.

### 4. Structure and Presentation (10%)

The submission is very well organised, with a ten-slide presentation, narration transcript, comprehensive README and modular Python implementation. The automated tests, evaluation scripts, execution records and workflow telemetry provide substantial supporting evidence of development. The documented implementation problems and subsequent corrections also demonstrate a systematic approach. However, the presentation would benefit from more careful proofreading, consistent formatting and a clearer summary of the most important testing results.

### 5. Use of Relevant Sources (10%)

The work uses relevant foundational literature, including Bratman, Wooldridge and ReAct, to support the planning architecture and agent design. Technical documentation is also appropriately referenced to explain implementation choices. However, the formal academic literature is relatively limited for Level 7 work, particularly in relation to recent developments in LLM agents. Greater engagement with empirical research on retrieval accuracy, grounded summarisation, agent reliability and human oversight would strengthen the justification of the design decisions.

### Overall Comments

This is an excellent submission demonstrating strong technical understanding and a substantial implementation of an LLM-powered academic research system. The LangGraph architecture, structured planning, multiple scholarly retrieval sources, model fallback mechanisms and human approval process are strengths. The extensive documentation, testing and systematic resolution of implementation problems also reflect a well-considered development approach. The critical discussion is especially good in recognising that successful workflow execution does not necessarily mean the retrieved evidence or generated summaries are accurate. However, independent evaluation of retrieval relevance and factual correctness is needed to establish the quality of the research outputs. Broader engagement with contemporary academic literature and comparison of alternative architectures would also strengthen the work. The presentation communicates the system reasonably well but needs better proofreading, clearer screenshots and more concise explanations. Overall, this is a technically strong and critically informed submission that meets the assessment requirements, with further improvement needed in empirical evaluation and presentation quality.

## Assessment criteria and marks

| Assessment criterion | Weight | Mark awarded |
|---|---:|---:|
| Knowledge and understanding | 25% | 20 |
| Presentation and communication skills | 30% | 21 |
| Criticality | 25% | 20 |
| Structure and presentation | 10% | 8 |
| Use of relevant sources | 10% | 7 |
| **Total** | **100%** | **76** |

---

## Interpretation and development priorities

*This section is portfolio analysis, not a quotation from the tutor. It records actions to consider after the assessment; the submitted project has not been retroactively altered.*

The feedback recognised technical design, the scope of the working implementation, testing, documented remediation and responsible interpretation of the 12/12 structural evaluation. The key technical gap remains **independently measured semantic quality**: whether retrieved sources are genuinely relevant and whether generated claims are factually accurate and supported.

This creates three practical development priorities:

1. **Empirical research quality:** Define and test retrieval relevance and claim-level factual support against a manually reviewed reference set. Report measures separately from structural workflow success.
2. **Academic justification:** Review recent empirical work on retrieval quality, grounded summarisation, agent reliability and human oversight; compare relevant alternative architectures using explicit criteria.
3. **Technical communication:** Proofread slides, standardise layouts, improve screenshot readability and use concise quantitative summaries distinguishing automated tests, workflow evaluation and semantic quality.

These are **future development actions**, not claims that post-assessment changes were already made.

**Related evidence:** [Unit 11 individual implementation record]({{ '/modules/intelligent-agents/evidence/artefacts/unit-11-academic-research-agent-implementation/' | relative_url }}) · [Source code and evaluation documentation](https://github.com/Monogios1996/llm-academic-research-agent)
