---
title: Professional Development Plan — Intelligent Agents
permalink: /modules/intelligent-agents/action-plan/
---

# Professional Development Plan

## Purpose and evidence base

This plan translates the areas for improvement identified in my [Professional Skills Matrix]({{ '/modules/intelligent-agents/skills-matrix/' | relative_url }}) and the official [Unit 6]({{ '/modules/intelligent-agents/evidence/feedback/unit-06-team-design/' | relative_url }}) and [Unit 11]({{ '/modules/intelligent-agents/evidence/feedback/unit-11-individual-implementation/' | relative_url }}) tutor feedback into specific, measurable development activities.

The Unit 6 team design and Unit 11 individual implementation each received **76%**. Feedback recognised sound architecture choices, meaningful technical implementation, effective remediation and critical awareness of limitations, while identifying shortcomings in independent research-quality evaluation, presentation precision, contemporary academic literature and static architectural documentation.

**Status as of 18 October 2026:** The goals below are **future personal development actions**, not completed coursework or retrospective changes to submitted assessments. Dates are self-imposed target dates rather than university deadlines. Progress will be updated only when evidence of completion exists.

## SMART action plan

| Priority / skill gap | Specific action | Measurable evidence of success | Personal target | Current progress |
|---|---|---|---|---|
| **1. Empirical evaluation and critical analysis** — Strong structural testing but limited independent measurement of scholarly relevance, planning quality and factual support | Create a small, manually annotated evaluation set of **15 research requests**. For each request, record what the plan should cover and judge the top retrieved results for relevance; inspect **at least 20 generated claims** against the cited sources. Keep structural workflow results separate from semantic-quality measures. | Versioned evaluation dataset and rubric; reported **precision@5**, citation/DOI validity rate, claim-support rate and a brief error analysis discussing failures and sample-size limits | **15 December 2026** | **Planned — not yet completed** |
| **2. Technical communication and time management** — Presentation spelling, inconsistent formatting, difficult-to-read screenshots and repetitive explanations | Create a reusable pre-submission checklist covering spelling, formatting, legibility, source references, concise narration and separation of test types. Reserve one review session before the next presentation rather than relying on final-day edits. | Checklist and review log used on **one future technical presentation or report**; screenshots verified at viewing size; clear table distinguishing automated tests, structural evaluation and semantic accuracy | **15 November 2026** | **Planned — not yet completed** |
| **3. Contemporary research and architectural comparison** — Limited recent Level 7 empirical literature and quantitative comparison of alternatives | Review **at least eight recent empirical papers** relevant to LLM agents, grounded summarisation, retrieval evaluation and human oversight. Create a structured comparison of the implemented LangGraph approach with **two alternative orchestration designs/frameworks**, describing design fit, control, state handling, testability and known limitations. | Annotated reading list; comparison matrix with citations; a **1,000-word maximum** critical synthesis identifying implications for future versions of the project | **15 January 2027** | **Planned — not yet completed** |
| **4. System documentation and local-model evaluation** — Missing UML class diagram and incomplete local model/hardware characterisation | Produce a **static UML class/component and data-structure diagram** for the implemented prototype, showing major roles, shared state and exchanged data. Record the Ollama model version and quantisation, hardware and RAM/VRAM, context settings, and test local planning performance on a fixed set of representative requests. | Versioned diagram checked against the actual Python implementation; reproducible benchmark notes reporting model configuration, hardware, median response time, output validity and limitations; no unsupported performance claims | **15 February 2027** | **Planned — not yet completed** |

## Why these priorities matter

### 1. From structural reliability to research quality

My submitted Unit 11 evaluation reported **83 automated tests passing** and **12/12 live research cases meeting structural requirements**. These results support the reliability of the tested workflow. They do not establish whether the best papers were selected or whether every factual claim is correct. The tutor explicitly identified independently verified retrieval and research accuracy as the most important missing evidence.

A manually reviewed benchmark would let me quantify where the prototype succeeds or fails semantically. The proposed sample would be a limited first step, not a claim of population-level accuracy. This goal develops **critical thinking, IT skills and problem-solving** and supports the technical focus of **LO2 and LO3**.

### 2. Make technical evidence easier to understand

Both my Unit 6 diagrams and my Unit 11 architecture explanation were recognised positively. However, the Unit 11 tutor identified slide proofreading, formatting, screenshot readability, repetition and imprecise presentation of measured performance as weaknesses.

The most practical response is to introduce a repeatable quality-control process for future work. This goal develops **communication, literacy and time management**.

### 3. Strengthen academic justification

The Unit 6 proposal justified LangGraph and Prometheus carefully, but Unit 11 feedback noted that a stronger Level 7 analysis would incorporate more contemporary empirical research and a systematic comparison of alternatives.

An annotated literature review and an explicit comparison framework would help distinguish theoretical suitability from performance demonstrated through evidence. This goal develops **academic critical analysis and professional research practice**.

### 4. Make the proposed architecture and local performance reproducible

The Unit 6 tutor noted that the system and sequence diagrams lacked a **formal static UML class diagram**, while the local fallback was not specified in sufficient hardware detail. Unit 11 introduced a real Ollama/Qwen3 fallback, but a full hardware and performance benchmark was not established in the submitted assessment.

Documenting the implemented structure and its reproducible local operating conditions would strengthen **IT and digital skills, technical communication and system evaluation**.

## Monitoring and review

For each goal, I will record the completion date, links to any created evidence, actual results and any reasons for modifying the target. A planned task will not be marked complete solely because the method has been described.

At the next portfolio review, I will consider:

- whether I produced the specified evidence;
- what the measurements or review revealed, including unsuccessful results;
- whether the work changed my understanding or practice;
- whether the original target or approach needs revision.

## Link to reflective practice

These priorities directly follow the progression from the [Unit 6 team design]({{ '/modules/intelligent-agents/evidence/artefacts/unit-06-group-e-team-design/' | relative_url }}) to the [Unit 11 individual implementation]({{ '/modules/intelligent-agents/evidence/artefacts/unit-11-academic-research-agent-implementation/' | relative_url }}). They will also inform my [final module reflection]({{ '/modules/intelligent-agents/reflection/' | relative_url }}), especially the distinction between what I demonstrated during the module and what I still need to develop.
