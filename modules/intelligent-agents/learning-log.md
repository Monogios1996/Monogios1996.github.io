---
title: Learning Log — Intelligent Agents
permalink: /modules/intelligent-agents/learning-log/
---

# Learning Log

This page is updated throughout the module so that development is recorded when it happens rather than reconstructed retrospectively.

## Units 1–3 — Agent-Based Systems Collaborative Discussion

**Topics studied:**  
Motivations for agent-based computing; operational multi-agent systems; agent-based modelling and simulation; reactive, deliberative and hybrid architectures; BDI agents; decentralisation; coordination; emergent behaviour; bounded autonomy; human oversight and orchestration.

**Activities completed:**  
Completed the Unit 1 initial post, responded critically to two peers in Unit 2, considered two pieces of peer feedback on my own post, and produced the Unit 3 summary.

**Important concepts or arguments:**  
My initial position focused on the organisational value of autonomy, local decision-making, modularity and adaptability. Through the discussion, this developed into a more precise understanding that agent-based design is not simply a choice between centralised and decentralised control. System quality depends on how autonomy is bounded, how agents communicate and coordinate, how emergent behaviour is validated, and where system-level constraints and human oversight are introduced.

**Questions or difficulties:**  
A key conceptual question was whether deterministic orchestration weakens the autonomy that makes a system genuinely agent-based. My current position is that it does not necessarily do so: agents may retain meaningful decision-making within defined roles, permissions and interfaces while orchestration provides sequencing, governance and auditability.

**Connection to prior learning or professional practice:**  
The discussion reinforced the importance of separating local optimisation from system-level objectives. This has direct relevance to organisational AI systems where multiple components may each behave rationally while still producing undesirable outcomes if objectives, permissions or communication structures are poorly specified.

**Evidence created:**  
- [Initial Post]({{ '/modules/intelligent-agents/evidence/discussions/unit-01-agent-based-systems-initial-post/' | relative_url }})
- [Peer Responses]({{ '/modules/intelligent-agents/evidence/discussions/unit-02-peer-responses/' | relative_url }})
- [Peer Feedback Received]({{ '/modules/intelligent-agents/evidence/discussions/unit-02-feedback-received/' | relative_url }})
- [Summary Post]({{ '/modules/intelligent-agents/evidence/discussions/unit-03-summary-post/' | relative_url }})

**Learning outcomes supported:**  
LO1 and LO4.

**Next action:**  
Carry the concepts of bounded autonomy, coordination, system-level constraints and validation into later technical and team exercises rather than treating them only as discussion concepts.

---

## Units 5–7 — Agent Communication Languages Collaborative Discussion

**Topics studied:**  
KQML; agent communication languages; performatives and speech acts; loose coupling; semantic interoperability; shared ontologies; protocol conformance; method invocation in Python and Java; autonomy; message validation; ontology governance; auditability and hybrid communication architectures.

**Activities completed:**  
Completed the Unit 5 initial post, wrote two critical peer responses in Unit 6, and submitted the Unit 7 summary post. No direct responses were received on my own initial post, so the final synthesis was based on genuine engagement with classmates' arguments and the Units 5–7 learning content rather than manufactured feedback.

**Important concepts or arguments:**  
My initial comparison focused on KQML as a semantic communication mechanism for autonomous, heterogeneous agents and method invocation as a more direct interface-oriented mechanism. During peer review, this distinction became more precise. Method calls are not necessarily “always obeyed”, and they do not always require compile-time interface knowledge. The stronger distinction concerns abstraction and decision authority: ACLs represent communicative intent, while methods normally encode operations.

I also developed a stronger understanding that syntactic compatibility does not guarantee semantic interoperability. Agents can exchange structurally valid messages while still interpreting their content differently. Shared ontologies, versioning, validation and governance therefore become part of the communication architecture rather than optional additions.

**Questions or difficulties:**  
A central question was whether dedicated ACLs such as KQML remain necessary when modern systems can use standard messaging technologies, APIs and schemas. My current position is that the value of an ACL lies less in transport syntax and more in explicitly representing communicative intent, autonomy and conversation semantics. Where those features are unnecessary, a simpler messaging or method-based design may be preferable.

**Connection to prior learning or professional practice:**  
The discussion connected intelligent-agent communication to broader software architecture. It reinforced that communication mechanisms should be selected according to system boundaries, autonomy requirements and failure consequences rather than because an ACL is inherently more advanced than ordinary software interfaces.

**Evidence created:**  
- [Initial Post]({{ '/modules/intelligent-agents/evidence/discussions/unit-05-agent-communication-languages-initial-post/' | relative_url }})
- [Peer Responses]({{ '/modules/intelligent-agents/evidence/discussions/unit-06-agent-communication-languages-peer-responses/' | relative_url }})
- [Summary Post]({{ '/modules/intelligent-agents/evidence/discussions/unit-07-agent-communication-languages-summary-post/' | relative_url }})

**Learning outcomes supported:**  
LO1 and LO4 for the formal e-portfolio mapping. The activity also developed technical understanding relevant to later implementation work.

**Next action:**  
Apply these communication concepts to later agent-system design work by distinguishing internal method calls, inter-agent message formats, shared semantics, validation requirements and governance mechanisms explicitly.

---

## Unit 6 — Creating Agent Dialogues Using KQML and KIF

**Topics studied:**  
KQML message structure, `ask-one` and `tell` performatives, sender and receiver fields, KIF as a content language, variables in knowledge queries and simple agent request-response communication.

**Activity completed:**  
Created a four-message dialogue between Alice, a procurement agent, and Bob, a warehouse stock agent. Alice queries the quantity of 50-inch televisions and their number of HDMI slots; Bob returns the corresponding facts.

**Important concept:**  
The exercise made the separation between KQML and KIF practical. KQML describes the communication act and message metadata, while KIF expresses the actual query or fact. This made the conceptual distinction from Collaborative Discussion 2 much clearer than reading definitions alone.

**Limitation recognised:**  
The dialogue demonstrates only a simple successful interaction. It does not address ontology declarations, refusal, errors, authentication, conversation management or executable implementation, so it should not be over-interpreted as evidence of a deployed multi-agent system.

**Evidence created:**  
- [Agent Dialogue Using KQML and KIF]({{ '/modules/intelligent-agents/evidence/artefacts/unit-06-agent-dialogue-kqml-kif/' | relative_url }})

**Learning outcome supported:**  
Primarily LO1. It also provides conceptual preparation for LO3 without yet constituting full implementation evidence.

**Next action:**  
Use later implementation exercises to move from manually structured messages to executable agent communication and evaluation.

---

## Weekly entry template

### Unit / week

**Topics studied:**  
To be added.

**Activities completed:**  
To be added.

**Important concepts or arguments:**  
To be added.

**Questions or difficulties:**  
To be added.

**Connection to prior learning or professional practice:**  
To be added.

**Evidence created:**  
To be added.

**Learning outcomes supported:**  
To be added.

**Next action:**  
To be added.
