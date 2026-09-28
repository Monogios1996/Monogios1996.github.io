# Collaborative Discussion 2 — Peer Responses

**Topic:** Agent Communication Languages  
**Unit:** 6  
**Status:** Submitted

## Peer Response 1

The classmate's post clearly distinguished KQML from direct method invocation and emphasised KQML's performatives, heterogeneous-agent communication and lack of full standardisation. My response agreed with the broad distinction but challenged the claim that Python and Java method calls are always obeyed.

I argued that method execution can still fail because of exceptions, access restrictions, invalid state or rejected input. The more useful distinction is where decision-making authority resides: in an agent system, the receiver may interpret a request against its own goals, beliefs or policies before deciding whether to act (Wooldridge, 2009).

I also argued that the interoperability benefit of KQML depends on governance. Measures such as restricting the permitted performatives, agreeing shared ontologies, validating messages, testing protocol conformance and defining explicit error-handling rules can reduce ambiguity. I concluded that a hybrid design may often be strongest, with ACL messages coordinating autonomous agents at system level while ordinary Python or Java methods implement deterministic internal operations.

I ended by asking whether modern multi-agent systems still require a dedicated ACL such as KQML, or whether similar autonomy could be achieved through standard messaging technologies combined with agreed schemas and policies.

### References

Finin, T., Fritzson, R., McKay, D. and McEntire, R. (1994) ‘KQML as an agent communication language’, *Proceedings of the Third International Conference on Information and Knowledge Management*, pp. 456–463.

Singh, M.P. (1998) ‘Agent communication languages: rethinking the principles’, *Computer*, 31(12), pp. 40–47.

Wooldridge, M.J. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: Wiley.

---

## Peer Response 2

The second classmate framed ACL communication as communicative action and method invocation as direct execution, highlighting autonomy, loose coupling and ontology alignment. My response agreed with the importance of communicative intent but qualified the claim that method invocation necessarily requires compile-time knowledge of an interface.

I noted that Python is dynamically typed and that Java can use mechanisms such as interfaces, reflection and remote invocation to reduce direct coupling. I therefore argued that the stronger distinction is one of abstraction and semantics: ACLs explicitly model acts such as requesting, informing or negotiating, whereas ordinary methods usually encode the operation itself.

I also developed the ontology-governance issue. Shared domain ontologies, ontology versioning, capability advertisement and message validation could reduce semantic mismatch before agents are allowed to interact. Where uncertainty remains, agents could escalate ambiguous requests or negotiate mappings rather than act automatically. This preserves autonomy while reducing the risk of apparently valid but semantically incorrect communication.

I concluded that ACLs are most valuable when participant relationships are dynamic and communicative intentions matter independently of implementation. In tightly governed systems, simpler messaging or method invocation may be easier to test and maintain. I ended by asking whether ontology governance is a larger practical barrier to ACL adoption than KQML's lack of formal semantics.

### References

Labrou, Y., Finin, T. and Peng, Y. (1999) ‘Agent communication languages: the current landscape’, *IEEE Intelligent Systems*, 14(2), pp. 45–52.

Wooldridge, M.J. (2009) *An Introduction to MultiAgent Systems*. 2nd edn. Chichester: Wiley.
