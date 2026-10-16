---
title: Collaborative Discussion 1 — Peer Feedback Received
permalink: /modules/intelligent-agents/evidence/discussions/unit-02-feedback-received/
---

# Collaborative Discussion 1 — Peer Feedback Received

**Topic:** Agent-Based Systems  
**Unit:** 2  
**Status:** Two peer responses received

*The feedback below is reproduced from the discussion forum. Peer names and profile links are omitted from the public e-Portfolio.*

## Peer Feedback 1

Hi, Panagiotis

This is a thorough and well-referenced post that covers the rise of agent-based systems with commendable breadth. The distinction drawn between operational multi-agent systems and agent-based modelling and simulation is particularly valuable — many posts conflate the two, and separating them clearly strengthens the analytical quality of this contribution. The use of Bonabeau (2002, p. 7280) and Macal and North (2010, p. 151) to support the simulation argument is well-chosen and correctly cited.

The discussion of agent architectures — reactive, deliberative, and hybrid — is accurate and grounded in established literature. The warehouse robot example effectively illustrates why no single architecture is universally superior, which reflects a mature understanding of the field.

That said, a few areas could be developed further. First, while the post mentions that outcomes from agent interactions may be difficult to explain or validate, this touches on the important concept of emergent behaviour without naming it explicitly. Wooldridge and Jennings (1995, p. 116) note that emergent system-level behaviour is one of the defining challenges of multi-agent design, and using this terminology would sharpen the argument considerably.

Second, the post raises coordination costs and conflicting local objectives as limitations but does not suggest any mitigation strategies. Sycara (1998, p. 80) discusses coordination mechanisms such as negotiation protocols and contract nets as established approaches to managing these challenges — referencing these would balance the critical analysis with constructive solutions.

Third, the closing point about retaining meaningful human oversight is important but brief. Given the module's focus on human-in-the-loop design, expanding this point with a specific mechanism — such as adjustable autonomy — would strengthen the conclusion.

Overall, this is an impressive and well-structured post that demonstrates both depth and critical awareness.

**References**

Bonabeau, E. (2002) 'Agent-based modeling: methods and techniques for simulating human systems', *Proceedings of the National Academy of Sciences*, 99(Suppl. 3), pp. 7280–7287. Available at: https://doi.org/10.1073/pnas.082080899 (Accessed: 7 August 2026).

Macal, C.M. and North, M.J. (2010) 'Tutorial on agent-based modelling and simulation', *Journal of Simulation*, 4(3), pp. 151–162. Available at: https://doi.org/10.1057/jos.2010.3 (Accessed: 7 August 2026).

Sycara, K.P. (1998) 'Multiagent systems', *AI Magazine*, 19(2), pp. 79–92. Available at: https://doi.org/10.1609/aimag.v19i2.1370 (Accessed: 7 August 2026).

Wooldridge, M. and Jennings, N.R. (1995) 'Intelligent agents: theory and practice', *The Knowledge Engineering Review*, 10(2), pp. 115–152. Available at: https://doi.org/10.1017/S0269888900008122 (Accessed: 7 August 2026).

---

## Peer Feedback 2

Your warehouse example makes the difference between reactive and deliberative agents clear. A reactive component is useful when the environment changes quickly, while planning and procurement need a more deliberate approach. No single architecture is best for every task. The complication is that decentralisation does not automatically make the complete system more resilient. If specialist agents exchange weak or ambiguous information, each local decision may appear reasonable while the overall result is still poor.

That coordination problem is what our team is trying to control in an academic research assistant. Specialist agents handle planning, retrieval and evidence assessment, while deterministic code controls their order and message formats. They cannot negotiate as freely, but their actions leave a clearer audit trail. Finin *et al.* (1994) show why defined communication semantics matter. Wang *et al.* (2024) also explain that complex planning benefits from feedback instead of depending on a flawless initial plan.

This matters even more when the software handles private information. Decentralisation should not give every component access to all user data. A central policy boundary can keep sensitive information local while allowing a bounded agent to complete a specific task. Central coordination can therefore define useful autonomy rather than remove it.

Do you think a deterministic orchestrator makes a multi-agent system less genuinely agent-based, or can agents remain autonomous within clearly defined roles and permissions?

**References**

Finin, T., Fritzson, R., McKay, D. and McEntire, R. (1994) 'KQML as an agent communication language', in *Proceedings of the Third International Conference on Information and Knowledge Management*. New York: ACM, pp. 456-463. doi:10.1145/191246.191322.

Wang, L. *et al.* (2024) 'A survey on large language model based autonomous agents', *Frontiers of Computer Science*, 18, article 186345. doi:10.1007/s11704-024-40231-1.

---

## How I used the feedback

The feedback was incorporated into my Unit 3 summary. I explicitly named **emergent behaviour**, developed the discussion of coordination mechanisms and communication semantics, and expanded the relationship between autonomy, deterministic orchestration and human oversight. This moved my analysis from a simple centralised-versus-decentralised comparison toward the distribution of autonomy, coordination and oversight at system level.
