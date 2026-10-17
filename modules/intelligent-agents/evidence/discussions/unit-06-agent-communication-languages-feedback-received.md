---
title: Collaborative Discussion 2 — Peer Feedback Received
permalink: /modules/intelligent-agents/evidence/discussions/unit-06-agent-communication-languages-feedback-received/
---

# Collaborative Discussion 2 — Peer Feedback Received

**Topic:** Agent Communication Languages  
**Unit:** 6  
**Status:** One peer response received

*The feedback below is reproduced from the discussion forum. The peer's name and profile link are omitted from the public e-Portfolio.*

## Peer Feedback

Panagiotis, I agree with you that agent communication languages and method invocation are not direct replacements but distinct kinds of difficulties. I think your difference between closely connected components and autonomous, diverse actors is very essential. For the case when the interface is already known, a call to a method in Python or Java is efficient, but KQML is better suited when agents need to interact without disclosing their underlying implementation.

Also, your comment on shared semantics was really salient for me. Even with the identical KQML syntax, two agents may not be able to communicate if they perceive a performative or ontology differently. Labrou, Finin, and Peng (1999) also raise similar issues about conformity and interoperability. One way to mitigate this risk is to use a well-documented ontology for a given system, with a limited number of performatives, rather than unconstrained message interpretation.

Another safety measure would be to have message validation and permanent logging. By verifying each communication against an anticipated schema and storing it together with the sender, recipient, and purpose, errors are easier to identify. This also enhances accountability in multi-agent settings.

This is crucial to my ScholarPlan implementation, since I did not implement the whole KQML standard but utilized a restricted KQML-like vocabulary such as "request," "inform," "confirm," and "reject." Messages were logged on a shared chalkboard, which provided loose coupling but also traceability. The experience supported your judgment that flexibility in communication is only desirable if semantics, protocols, and governance are appropriately regulated.

**References**

Finin, T., Fritzson, R., McKay, D., and McEntire, R. (1994) ‘KQML as an agent communication language,' *Proceedings of the Third International Conference on Information and Knowledge Management*, pp. 456–463.

Labrou, Y., Finin, T., and Peng, Y. (1999) ‘Agent communication languages: the current landscape,' *IEEE Intelligent Systems and Their Applications*, 14(2), pp. 45–52.

---

## How I used the feedback

The response reinforced the importance of constrained semantics, message validation and traceability. It supported my conclusion that communication flexibility is only useful when the permitted performatives, ontologies and logging mechanisms are well governed. This complements the peer-review points I developed in my own responses on ontology governance, restricted performatives and hybrid designs.
