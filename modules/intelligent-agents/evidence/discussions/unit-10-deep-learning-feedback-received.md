---
title: Collaborative Discussion 3 — Peer Feedback Received
permalink: /modules/intelligent-agents/evidence/discussions/unit-10-deep-learning-feedback-received/
---

# Collaborative Discussion 3 — Peer Feedback Received

**Topic:** Deep Learning  
**Unit:** 10  
**Status:** Two peer responses received

*The feedback below is reproduced from the discussion forum. Peer names and profile links are omitted from the public e-Portfolio.*

## Peer Feedback 1

Hi Panagiotis,

I agree with your argument that the ethical challenge of generative AI is sociotechnical rather than purely technical. This complements my initial post, particularly my concerns about bias, reliability, consent, and the need for meaningful human oversight. Your point that increasing model scale does not automatically eliminate bias is especially important because the underlying problem may originate from the composition and representation of the training data itself (Bender et al., 2021).

I also found your discussion of memorisation particularly useful. Carlini et al. (2023) show that diffusion models can reproduce examples from their training data, which strengthens the concern that generated content cannot always be assumed to be completely novel. From a preventative perspective, I think this requires safeguards before and after model training. Dataset provenance, consent mechanisms, and sensitive-data filtering should be considered before training, while output monitoring and mechanisms for reporting reproduced material should remain available after deployment.

Your discussion of misinformation also connects with my concern about information integrity. I would add that provenance information alone may not be sufficient because users may ignore or misunderstand warnings. NIST (2024) therefore supports a broader risk-management approach involving testing, monitoring, and human oversight.

I particularly agree with your suggestion of stronger controls for high-impact applications. However, these controls should be continuous rather than limited to deployment. Models and their operating environments can change, so periodic evaluation for bias, privacy leakage, and harmful outputs should form part of responsible deployment.

Overall, your post reinforces the need to treat ethical safeguards as part of the entire AI lifecycle rather than as controls added after development.

**References**

Bender, E.M., Gebru, T., McMillan-Major, A. and Shmitchell, S. (2021) ‘On the dangers of stochastic parrots: Can language models be too big?’, *Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency*, pp. 610–623. doi:10.1145/3442188.3445922.

Carlini, N. et al. (2023) ‘Extracting training data from diffusion models’, *32nd USENIX Security Symposium*, pp. 5253–5270.

National Institute of Standards and Technology (NIST) (2024) *Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile*. NIST AI 600-1. Gaithersburg, MD: NIST.

---

## Peer Feedback 2

Hi Panagiotis,

Your sociotechnical framing is persuasive, but I think one of your proposed safeguards, human review for high-impact uses, deserves further scrutiny. Keeping a human “in the loop” does not necessarily mean that oversight is effective.

Sele and Chugunova (2024), for example, found that allowing participants to adjust algorithmic recommendations increased their willingness to use automated decision support and their confidence in the predictions they submitted. However, human adjustments reduced average decision accuracy, and participants were less likely to adjust recommendations containing larger errors. Although their experiment involved a specific prediction task rather than generative AI, it challenges the assumption that adding human review automatically improves decision quality. This may be particularly important for generative AI, where outputs are often open-ended and reviewers may lack an obvious ground truth against which to assess whether plausible-looking content is actually accurate.

This also complicates your point about clear accountability. Novelli, Taddeo and Floridi (2024) conceptualise accountability as a relation between an agent, who must answer for conduct, and a forum, to whom that account is owed. Applied to human review, this raises a practical problem: if a reviewer approves an AI-generated output but lacks sufficient information or expertise to identify an error, it may be unclear who is actually answerable. The authors also identify distributed responsibility as a potential source of accountability gaps. Where responsibility is spread across developers, deploying organisations and individual users, placing a human at the final step may create the appearance of accountability without ensuring that anyone is effectively held to account.

For this reason, I would not treat human review as a sufficient safeguard in itself. In my view, meaningful oversight also requires reviewers to have appropriate expertise, information and authority, alongside clearly defined accountability structures. Which of these conditions do you think would be hardest to guarantee in practice?

**References**

Novelli, C., Taddeo, M. and Floridi, L. (2024) ‘Accountability in artificial intelligence: what it is and how it works’, *AI & Society*, 39, pp. 1871–1882. Available at: https://doi.org/10.1007/s00146-023-01635-y

Sele, D. and Chugunova, M. (2024) ‘Putting a human in the loop: increasing uptake, but decreasing accuracy of automated decision-making’, *PLOS ONE*, 19(2), e0298037. Available at: https://doi.org/10.1371/journal.pone.0298037

---

## How I used the feedback

The first response strengthened my view that safeguards should operate across the full AI lifecycle rather than only at deployment. The second challenged an assumption in my initial post by showing that human review is not automatically effective. I therefore refined my position to distinguish **human involvement** from **meaningful oversight**, which requires suitable expertise, access to evidence, authority to reject outputs, and clearly defined accountability.
