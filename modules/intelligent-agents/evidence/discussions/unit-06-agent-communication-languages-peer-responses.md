---
title: Collaborative Discussion 2 — Peer Responses
permalink: /modules/intelligent-agents/evidence/discussions/unit-06-agent-communication-languages-peer-responses/
---

# Collaborative Discussion 2 — Peer Responses

**Topic:** Agent Communication Languages  
**Unit:** 6  
**Status:** Submitted

The text below reproduces my two submitted peer responses.

## Peer Response 1

Aldana, I agree with your central distinction that ACL communication is primarily about communicative intent, while method invocation is primarily about executing a defined interface. Your discussion of autonomy and ontology alignment is particularly important because a common message format does not guarantee that two agents attach the same meaning to its content (Labrou, Finin and Peng, 1999).

I would qualify one part of the comparison, however. Method invocation does not always require compile-time knowledge of an interface. Python is dynamically typed, and Java can use reflection, interfaces, remote invocation and other mechanisms that reduce direct coupling. This means the contrast is better understood as a difference in abstraction and semantics rather than simply “open” versus “closed” technology. ACLs explicitly model acts such as requesting, informing or negotiating, whereas ordinary methods usually encode the operation itself.

Your point about ontology alignment also suggests a practical weakness that organisations would need to manage. Shared domain ontologies, ontology versioning, capability advertisement and validation of message content could reduce semantic mismatch before agents are allowed to interact. Where uncertainty remains, agents could escalate ambiguous requests or negotiate mappings rather than acting automatically. This would preserve autonomy while limiting the risk of apparently valid but semantically incorrect communication.

I therefore see ACLs as most valuable when the relationship between participants is dynamic and their intentions matter independently of implementation. In tightly governed systems, simpler messaging or method calls may be easier to test and maintain.

Would you consider ontology governance a larger practical barrier to ACL adoption than the lack of formal semantics in KQML itself?

**References:**

Labrou, Y., Finin, T. and Peng, Y. (1999) ‘Agent communication languages: the current landscape’, *IEEE Intelligent Systems*, 14(2), pp. 45–52.

Wooldridge, M.J. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: Wiley.

---

## Peer Response 2

Khadijah, your distinction between KQML and direct method invocation is clear, particularly the point that KQML separates communicative intent from message content. I also agree that this separation supports heterogeneous agents because the sender does not need to know the receiver’s internal implementation (Finin et al., 1994).

One point I would qualify is the statement that Python and Java method calls are “always obeyed”. A method invocation is certainly more direct than an ACL request, but execution can still fail because of exceptions, access restrictions, invalid state or rejected input. The more important distinction is therefore not guaranteed execution, but where decision-making authority resides. In an agent system, the receiver may interpret a request against its own goals, beliefs or policies before deciding whether to act, which is central to agent autonomy (Wooldridge, 2009).

I also think the interoperability advantage of KQML depends heavily on governance. As Singh (1998) argues, inconsistent semantics can undermine the value of a shared communication language. Measures such as a restricted set of performatives, agreed ontologies, message validation, protocol conformance testing and explicit error-handling rules could reduce this problem. In practice, a hybrid design may be strongest: ACL messages can coordinate autonomous agents at the system level, while ordinary Python or Java methods implement deterministic operations inside each agent.

Do you think modern multi-agent systems still require a dedicated ACL such as KQML, or could similar autonomy be achieved using standard messaging technologies plus agreed schemas and policies?

**References:**

Finin, T., Fritzson, R., McKay, D. and McEntire, R. (1994) ‘KQML as an agent communication language’, *Proceedings of the Third International Conference on Information and Knowledge Management*, pp. 456–463.

Singh, M.P. (1998) ‘Agent communication languages: rethinking the principles’, *Computer*, 31(12), pp. 40–47.

Wooldridge, M.J. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: Wiley.
