---
title: Final Reflective Piece — Intelligent Agents
permalink: /modules/intelligent-agents/reflection/
---

# Intelligent Agents — Final Reflective Piece

### What?

The Intelligent agents module took me from discussing and planning agent architecture to the actual implementation of an academic research system. I use Rolfe, Freshwater and Jasper’s (2001) reflective questions to explain how this experience influenced my understanding, working habits and professional judgement.

The module also had collaborative discussions, KQML/KIF communication, parsing and a deep learning application exercise. For the Unit 6 project my role was the architecture and UML sequence diagrams and later to check their consistency with the written proposal. For Unit11, from team designing I moved to the individual implementation of the system using Python, LangGrap, scholarly retrieval APIs and a combination of language model and deterministic components. My final implementation passed 83 automated tests and completed all live evaluation cases structurally.

### So what?

At first, I thought that agent based systems are associated with decentralized decision making, but that view got complicated. Wooldridge (2009) helped me understand different agent approaches, while the implementation made me have to think about the difference between specialised responsibilities and real independence. The components I used were coordinated through shared state and explicit routing and calling them six independently autonomous agents would be an exaggeration of what the system actually did.

I chose LangGraph because I wanted the state transitions, retries and replanning to be inspectable. That was a reasonable choice but it did make the system more complex where if i had used a more simple pipeline this might have been avoided, the alternatives were not compared experimentally so i cannot say if LangGraph was the best choice.

Now, looking back at the Unit 6 proposal, I was careful about consistency but less careful about what could possibly be missing from the design. The tutor did praise the clarity of the diagrams but also recommended adding a UML class diagram which we did not include. I was more focused on how the system would behave than showing the relationships between its components. Also I could have identified and raised this issue before we submitted it. The peer evaluation activity also helped me to think more about group responsibility, rather than focusing on my own tasks and contribution.

Additionally,I had problems that took a toll on my confidence in the design. When the live tests failed I felt frustrated because I thought that my approach was correct, however after inspecting the code carefully I did notice all the details and assumptions I had overlooked. I had spent more time thinking about how the system should work instead of checking how it actually behaved and then I started examining each failure more carefully before thinking what to change.

During the testing phase I made multiple corrections, I included stricter output requirements, i removed duplicated records across subtasks and i added checks for unsupported summaries. One of the important things i found was that fixing one problem could create another, for example the stricter relevance filtering could remove weak evidence but also could exclude useful paper, while safer summaries could leave out important details, so this means for me that a fix is not considered useful just because it solved the original problem. When I saw the 12/12 evaluation results it gave me confidence in the system, and it was later that I understood that those results only showed me that the system completed its required steps, that did not prove that the papers were the most relevant or that the summaries were accurate. Now that I look at it again I placed too much importance on where the workflow completed successfully. The tutor feedback I received for the Unit 11 assignment highlighted the lack of an independent accuracy evaluation, so maybe I should have prepared a small set of manually reviewed results from before, so then I could use them to assess and improve the quality of the system during the development phase.

The peer discussion also made me question whether the human approval stage in my system indeed had enough oversight. Lara Koller referred to a study by Sele and Chugunova (2024), where human adjustments didn't improve prediction accuracy. Even though the study was not about generative AI research agents, it did raise the question if a reviewer can always be able to identify unreliable academic evidence. In my case the system requires human approval in order to export the final output, but I didn't test if that review can actually be effective. Novelli, Taddeo and Floridi (2024) also helped me in understanding that accountability is also about being able to explain and justify decisions, not just have someone approve them.

Another issue became clear after the feedback on my presentation, because I had spent so much time developing and testing the system that I gave very little attention to spelling, slide consistency, screenshot readability and more clear explanations, which resulted in some parts of the presentation not communicating the points of my work correctly.

### Now what?

In the future I will spend more time on how to evaluate both the workflow and the quality of the results before proceeding with implementation. The idea is to use a small set of manually reviewed papers and summaries to check for relevance and accuracy. Then I will repeat these steps after making changes and know from before the limitations of my results. Also in choosing technologies to use I will be comparing simpler alternatives before deciding on the approach. Additionally I will also pay attention to the hardware requirements and limitations for the local models.

For group projects I will be more focused on questioning missing parts of the design, even if my assigned work seems completed. For my future presentations, I will plan ahead better in order to give the required time and effort for proofreading, rehearsing and checking mistakes, spelling, screenshots and explanations.

Now that I am finishing this module I am way more confident in my ability to develop agent based systems, but also I understand my limitations in testing and decision making. I now know that a system to work is only a part of the task, I need to check the reliability of the results and if the evidence really supports the conclusions.

### References

Novelli, C., Taddeo, M. and Floridi, L. (2024) ‘Accountability in artificial intelligence: what it is and how it works’, AI & Society, 39, pp. 1871–1882. Available at: https://doi.org/10.1007/s00146-023-01635-y (Accessed: 18 October 2026).

Rolfe, G., Freshwater, D. and Jasper, M. (2001) Critical reflection in nursing and the helping professions: a user’s guide. Basingstoke: Palgrave Macmillan.

Sele, D. and Chugunova, M. (2024) ‘Putting a human in the loop: increasing uptake, but decreasing accuracy of automated decision-making’, PLOS ONE, 19(2), e0298037. Available at: https://doi.org/10.1371/journal.pone.0298037 (Accessed: 18 October 2026).

Wooldridge, M. (2009) An Introduction to MultiAgent Systems. 2nd edn. Chichester: Wiley.
