---
title: Collaborative Discussion 1 — Peer Responses
permalink: /modules/intelligent-agents/evidence/discussions/unit-02-peer-responses/
---

# Collaborative Discussion 1 — Peer Responses

**Topic:** Agent-Based Systems  
**Unit:** 2  
**Status:** Submitted

The activity required responses to at least two peers, with each response limited to approximately 200–300 words. The text below reproduces my submitted responses.

## Peer Response 1

Luis, your discussion makes a strong case for Multi-Agent Systems (MAS) as an alternative to centralized manufacturing control, particularly where flexibility and responsiveness are required. However, I think the benefits of decentralization also create an important trade-off that deserves further consideration. Giving individual agents autonomy may improve local responsiveness, but it does not necessarily guarantee that their combined behavior will produce an optimal or even predictable system-level outcome.

Leitão (2009) recognizes that distributed manufacturing control introduces challenges associated with coordination, interoperability and the emergence of global behavior from local decisions. This suggests that simply decomposing a manufacturing problem among autonomous agents may transfer complexity rather than eliminate it. For example, agents independently optimizing production speed, inventory or energy use could pursue conflicting objectives unless appropriate coordination mechanisms are established.

I therefore agree that the absence of common architectures and standards is a significant barrier, but technical standardization alone may not be sufficient. Pulikottil et al. (2023) highlight that industrial implementation also depends on validation, integration and confidence in agent-based solutions. Preventive measures could therefore include simulation and testing before deployment, clearly defined agent responsibilities, communication protocols, monitoring of agent interactions and mechanisms that allow human intervention when unexpected behavior occurs.

Consequently, I would argue that the most effective manufacturing MAS may not be completely decentralized. A hybrid approach combining local agent autonomy with system-level constraints and human oversight could provide greater adaptability without sacrificing organizational control. How much autonomy do you think manufacturers should give individual agents before decentralization begins to create more risk than flexibility?

**References**

Leitão, P. (2009) ‘Agent-based distributed manufacturing control: A state-of-the-art survey’, *Engineering Applications of Artificial Intelligence*, 22(7), pp. 979–991. doi: 10.1016/j.engappai.2008.09.005.

Pulikottil, T. et al. (2023) ‘Agent-based manufacturing — review and expert evaluation’, *The International Journal of Advanced Manufacturing Technology*, 127(5), pp. 2151–2180. doi: 10.1007/s00170-023-11517-8.

---

## Peer Response 2

Khadijah, I agree that the ability of AI agents to operate with limited supervision is an important reason for their increasing organizational adoption. However, I think the comparison between an AI agent and an “employee” requires some qualification. Wooldridge and Jennings (1995) identify autonomy, reactivity and proactiveness as important characteristics of intelligent agents, but autonomy does not necessarily imply human-like judgement or accountability.

This distinction becomes particularly important when agents are given access to organizational systems such as CRM platforms, email or cloud storage. Russell and Norvig (2021) explain that rational agents select actions according to defined performance measures. Consequently, if objectives, available information or performance measures are poorly specified, an agent may take technically rational actions that nevertheless conflict with wider organizational interests. Therefore, early adoption alone may not guarantee the competitive advantages identified in your post.

The benefits of agent-based systems may instead depend on how effectively autonomy is governed. The NIST AI Risk Management Framework emphasizes incorporating risk management throughout the design, deployment and evaluation of AI systems (NIST, 2023). Organizations could therefore use measures such as restricted system permissions, human approval for high-impact actions, audit logs, testing and clear escalation procedures.

I would therefore view AI agents less as direct employee replacements and more as bounded autonomous systems whose level of independence should reflect the consequences of failure. How far do you think organizations should allow agents to act without human approval?

**References**

National Institute of Standards and Technology (NIST) (2023) *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. Gaithersburg, MD: NIST. Available at: https://doi.org/10.6028/NIST.AI.100-1 (Accessed: 9 August 2026).

Russell, S.J. and Norvig, P. (2021) *Artificial Intelligence: A Modern Approach*. 4th edn. Harlow: Pearson. Their agent framework explicitly distinguishes reflex, model-based, goal-based and utility-based agents and ties rational behaviour to performance measures.

Wooldridge, M. and Jennings, N.R. (1995) ‘Intelligent agents: theory and practice’, *The Knowledge Engineering Review*, 10(2), pp. 115–152.
