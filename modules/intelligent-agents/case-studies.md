---
title: Three Reflective Case Studies — Intelligent Agents
permalink: /modules/intelligent-agents/case-studies/
---

# Three Reflective Case Studies — Intelligent Agents

The cases follow Rolfe, Freshwater and Jasper’s (2001) reflective questions: what occurred, why it mattered and how it will inform future practice.

## Case Study 1: AI Safety Constraints and Bounded Autonomy

### What?

For the team project of Unit 6 my role was the development of the architecture and sequence diagrams and also to check the consistency between them and the written design. Because of representing retries, replanning and approval I was required to decide how the control flow should be communicated. There was a failed validation check and then a retry seemed straightforward. The implementation of the academic research agent for Unit 6 showed the assumptions behind those arrows.

With the implementation of the local model sometimes it returned malformed JSON or very few research subtasks, so to tackle this I improved the schema constraint and planning requirement, and at the same time the LangGraph workflow imposed limits on retries and replanning. Also the export function checked the workflow state and an explicit approval step before writing the final research package.

### So what?

The failures I had showed me that even when you establish a recovery path it does not mean that recovery will be successful, because a retry might reproduce the same invalid response. Also I realised that by allowing repeated attempts without a limit this would consume a lot of resources without accomplishing anything, so I had to make sure the model’s suggestion will be checked before the application acts on them.

So this approach limited the autonomy of the agent. The model would propose research tasks, but deterministic rules are the ones responsible for the continuation of the workflow. This approach or compromise, suits the project needs to be able to inspect execution, even though restrictive planning requirements can also reject a useful plan, this is something that I didn't take into consideration so i cant claim that tighter rules always improve research quality. The human approval step also introduced a limitation, because the code checked for permission to export but it cannot establish if the reviewer actually understood the evidence. Lara Koller’s discussion response challenged my assumption that human involvement was enough, drawing on Sele and Chugunova (2024). In their experiment they saw that human adjustments reduced average prediction accuracy, even though they didn’t test generative research agents, it gave me good reason to question how useful and how much protection the approval step actually provides.

The automated export tests checked rejection when approval or the required state was absent, they didn’t show that a person would reject a misleading research package. Now I can understand the difference between enforcing a workflow and having actually effective human oversight.

### Now what?

What I would do is extend testing to repeated invalid plans, exhaust retry limits and misleading evidence presented for approval. I would check if reviewers detect problems and can reduce exports, and also that the agent respects that decision. I would also record the useful plans rejected by the rules. This design work helped me to understand how to make control paths explicit, and the implementation showed me how to examine the assumptions that make those controls useful.

## Case Study 2: Explainable Decisions in Intelligent Agents

### What?

For the Unit 6 project my diagrams described the components responsibilities and the sequence of interaction. In Unit 11 where I implemented this design I extended the emphasis on visibility through an inspectable research plan, retrieved records, relevance score and audit trail, where the users could review these before approving the export.

At first I didn't consider showing the workflow as an important aspect for explainability, the realization came later when I considered whether someone could use the information to challenge a retained paper or summary.

### So what?

An audit record could show that the validation passed without showing why the evidence deserved confidence, and so I noticed a similar limitation with my lexical ranker that calculated relevance from word overlap, giving more importance to the title matches and using topic specific terms to reduce generic matches. This helped make the calculations inspectable but a high score could still reflect shared vocabulary and not an actual useful answer to the research question and also relevant work using different terminology could be ranked poorly.

The limitation became even more noticeable when I compared the rule based parts of my system with those of the language model. I could explain how the ranking scores were calculated because they followed predefined rules, however, in order to understand why the model produced the particular subtasks or summaries was more difficult .Although the system those outputs it didn't explain how the model arrived at those answers and this could give the user the wrong impression that the entire process was equally transparent.

Miller (2019) argues that explanation research should see how people seek and understand explanations and not relying on the developers' intuitions. This shows a weakness in my approach, because i designed it to be inspected but without testing what other users needed to understand, is based only on what i think, someone might want to know why a paper was retained over another candidate, rather than read just a sequence of processing events.

Missing abstracts made this problem more obvious. What I did is introduce limitation statements and conservative summarisation safeguards instead of allowing detailed claims when there wasn't enough information about a source. This helped so that potential users can understand what was missing but also it meant that they would receive less information. Even if a summary seems correct , without an abstract, the system could still overlook a relevant paper because of not enough information to assess its value.

So, my diagrams and logs show evidence of documentation and traceability, but don't show any evidence so that users can see incorrect decisions. This helped me to understand that by showing how the system works it doesn't mean they can also recognise when it makes a mistake.

### Now what?

Now, for the future, I would make it more clear and easier to understand for users why sources received each score, the reasons behind rejection and what information was missing. I would additionally link the summary claims to their original sources, if possible. In order to test if these changes actually helped i would have users try to find incorrect source selections and claims that didnt have enough evidence, by this i could show if the explanations helped users recognise mistakes. If I just added more logs it wouldn't be enough, because too much information would make it even harder to review the system. Case Study 3: Responsible Deployment and Unintended Behaviour

### What?

In the live testing my research agent retrieved some duplicate records across different subtasks, it kept some not so relevant sources and it also included unsupported information in summaries. For example in one of the summaries the benchmark names mentioned were nowhere to be found in the source. This was an important concern because by this the research output can appear reliable while showing information that was not supported by any evidence.

When I saw those problems at first I became frustrated because I thought the implementation should be working correctly, as planned. So instead of making hasty decisions and quick changes, I went back through the code to understand the problems. I paid more attention to technical details which I had missed before and I made improvements based on the review I did. Some of the improvements were i removed duplicates across subtasks, enhanced the relevance filtering and adding checks for unsupported claims. Also I added safer fallback options for the occasions the generated content could not be trusted.

### So what?

I realised that I was overconfident in the initial design of the system, and the testing results justify this. But exactly because of the investigation of these problems the way I approach development has changed. Now I have started to pay more attention to how the different components work together, instead of assuming they will behave as I had in the design and even though the changes “fixed” the problems I had in mind, I wouldn't assume that this would work equally well on other topics.

Limitations were found also in the checks for unsupported claims. For example checking if there are unsupported acronyms or numbers did help in catching specific mistakes but it couldn't find every misleading statement or missing information. Additionally using text from the source can leave out important content and even stricter relevance filtering can reject useful papers. This made me realize that solving one problem can sometimes create another.

The results I submitted showed 83 passing automated tests and 12 structural passes from12 live evaluation cases. These results showed that the system did work in the tested condition, but they did not prove that the results were actually accurate. On the same note, having a valid DOI or URL helped me in tracing a source it did not guarantee that the summary represented it correctly.

I only recently received and reviewed the Unit11 tutor feedback which highlighted the lack of an independent accuracy evaluation. That of course, did not influence the changes i had already made but it gave me focus on what i should improve next. NIST (2024) also highlights how important it is to check sources and citations and to continue monitoring the performance of the system. It also shows that getting good results from a few tests doesn't mean the system will always work well.

### Now what?

Before making this system available for users or even for personal use, I would test it first with a wider range of research topics and manually check the results. I would first examine the selected papers for their relevance. If citations were valid and if summaries were supported by the original sources. Then I would repeat these checks if I changed the model or filtering rules to see if the changes actually improved performance without creating other problems. Additionally, I would make use that the users understood how the system works with research metadata and it may not have access to the complete papers.

This experience showed me that a system completing the tasks successfully doesn't mean that its research results can be trusted. The quality of those results needs to be tested before considering the system ready for use.

### References

Miller, T. (2019) ‘Explanation in artificial intelligence: insights from the social sciences’, Artificial Intelligence, 267, pp. 1–38. Available at: https://doi.org/10.1016/j.artint.2018.07.007 (Accessed: 19 October 2026).

National Institute of Standards and Technology (NIST) (2024) Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile. NIST AI 600-1. Gaithersburg, MD: NIST. Available at: https://doi.org/10.6028/NIST.AI.600-1 (Accessed: 19 October 2026).

Rolfe, G., Freshwater, D. and Jasper, M. (2001) Critical reflection in nursing and the helping professions: a user’s guide. Basingstoke: Palgrave Macmillan.

Sele, D. and Chugunova, M. (2024) ‘Putting a human in the loop: increasing uptake, but decreasing accuracy of automated decision-making’, PLOS ONE, 19(2), e0298037. Available at: https://doi.org/10.1371/journal.pone.0298037 (Accessed: 19 October 2026).
