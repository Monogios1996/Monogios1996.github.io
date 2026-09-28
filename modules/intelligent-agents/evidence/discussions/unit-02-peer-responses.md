# Collaborative Discussion 1 — Peer Responses

**Topic:** Agent-Based Systems  
**Unit:** 2  
**Learning outcomes:** LO1 and LO4  
**Status:** Submitted

## Peer Response 1

A peer argued for Multi-Agent Systems (MAS) as an alternative to centralised manufacturing control, particularly where flexibility and responsiveness are required. I agreed with this direction but focused on the trade-off created by decentralisation: local autonomy can improve responsiveness without guaranteeing an optimal or predictable system-level outcome.

Leitão (2009) recognises that distributed manufacturing control introduces challenges associated with coordination, interoperability and the emergence of global behaviour from local decisions. This suggests that decomposing a manufacturing problem among autonomous agents can redistribute complexity rather than remove it. For example, agents independently optimising production speed, inventory or energy use could pursue conflicting objectives unless appropriate coordination mechanisms are established.

I therefore argued that standardisation alone may be insufficient. Pulikottil et al. (2023) highlight that industrial implementation also depends on validation, integration and confidence in agent-based solutions. Preventive measures could include simulation and testing before deployment, clearly defined responsibilities, communication protocols, monitoring of agent interactions and mechanisms for human intervention when unexpected behaviour occurs.

I concluded that the most effective manufacturing MAS may be hybrid: local agent autonomy combined with system-level constraints and human oversight. This led to the question of how much autonomy manufacturers should grant before decentralisation creates more risk than flexibility.

### References

Leitão, P. (2009) ‘Agent-based distributed manufacturing control: A state-of-the-art survey’, *Engineering Applications of Artificial Intelligence*, 22(7), pp. 979–991. doi:10.1016/j.engappai.2008.09.005.

Pulikottil, T. et al. (2023) ‘Agent-based manufacturing — review and expert evaluation’, *The International Journal of Advanced Manufacturing Technology*, 127(5), pp. 2151–2180. doi:10.1007/s00170-023-11517-8.

---

## Peer Response 2

A second peer described limited-supervision AI agents as increasingly attractive to organisations. I agreed that autonomy is central to their adoption but argued that describing an AI agent as an “employee” risks overstating its judgement and accountability.

Wooldridge and Jennings (1995) identify autonomy, reactivity and proactiveness as important characteristics of intelligent agents, but autonomy does not imply human-like judgement. This becomes especially important when agents can access organisational systems such as CRM platforms, email or cloud storage. Russell and Norvig (2021) explain that rational agents select actions according to defined performance measures. If objectives, information or performance measures are poorly specified, an agent can take technically rational actions that conflict with wider organisational interests.

I therefore argued that the value of agent-based systems depends on how autonomy is governed. The NIST AI Risk Management Framework emphasises risk management throughout the design, deployment and evaluation of AI systems (NIST, 2023). Appropriate measures can include restricted permissions, human approval for high-impact actions, audit logs, testing and clear escalation procedures.

My conclusion was that organisational AI agents are better understood as bounded autonomous systems than as direct employee replacements, with independence calibrated to the consequences of failure.

### References

National Institute of Standards and Technology (NIST) (2023) *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. Gaithersburg, MD: NIST. doi:10.6028/NIST.AI.100-1.

Russell, S.J. and Norvig, P. (2021) *Artificial Intelligence: A Modern Approach*. 4th edn. Harlow: Pearson.

Wooldridge, M. and Jennings, N.R. (1995) ‘Intelligent agents: theory and practice’, *The Knowledge Engineering Review*, 10(2), pp. 115–152.
