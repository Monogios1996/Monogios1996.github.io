---
title: Unit 6 — Agent Dialogue Using KQML and KIF
permalink: /modules/intelligent-agents/evidence/artefacts/unit-06-agent-dialogue-kqml-kif/
---

# Unit 6 — Creating Agent Dialogues

**Activity:** Create an agent dialogue using KQML and KIF between two agents, Alice and Bob. Alice is responsible for procuring stock and Bob controls warehouse stock information. The dialogue must query both the available stock of 50-inch televisions and the number of HDMI slots they have.

**Type:** Individual learning activity  
**Status:** Completed  
**Primary module learning outcome evidenced:** LO1  
**Supporting development:** Conceptual preparation for LO3, but this activity is not presented as software implementation evidence.

## Completed answer

Alice is an agent responsible for procuring stock, while Bob is an agent that manages warehouse stock information.

Alice first asks Bob how many 50-inch televisions are currently available in stock.

```text
(ask-one
    :sender Alice
    :receiver Bob
    :language KIF
    :content "(stock-level television-50-inch ?quantity)"
)
```

Bob replies that there are 20 televisions available.

```text
(tell
    :sender Bob
    :receiver Alice
    :language KIF
    :content "(stock-level television-50-inch 20)"
)
```

Alice then asks Bob how many HDMI slots the 50-inch televisions have.

```text
(ask-one
    :sender Alice
    :receiver Bob
    :language KIF
    :content "(hdmi-slots television-50-inch ?slots)"
)
```

Bob replies that the televisions have 3 HDMI slots.

```text
(tell
    :sender Bob
    :receiver Alice
    :language KIF
    :content "(hdmi-slots television-50-inch 3)"
)
```

## Purpose and method

The activity applies the distinction between the **communication layer** and the **content language**. KQML provides the message wrapper and performatives (`ask-one` and `tell`), while KIF expresses the knowledge query or fact carried inside the message.

The first exchange uses a variable (`?quantity`) to request the stock level and then returns a concrete value. The second follows the same pattern for the number of HDMI slots. This demonstrates a simple request-response interaction between two agents with clearly defined roles.

## What I learned

The exercise made the difference between KQML and KIF concrete. KQML is not the domain knowledge itself: it specifies the communicative act, sender, receiver and content language. KIF represents the proposition being queried or communicated. Separating these layers makes it easier to understand how an agent can ask for information without requiring the knowledge representation to be embedded directly in the communication protocol.

## Limitations

This is intentionally a minimal dialogue. It does not demonstrate error handling, ontology declaration, conversation identifiers, authentication, refusal, unavailable stock, malformed content or more complex negotiation. It should therefore be treated as evidence of understanding the basic communication structure rather than evidence of a complete multi-agent communication system.

## Skills evidenced

- IT and digital: applying KQML and KIF syntax correctly in a structured agent dialogue.
- Problem-solving: translating a natural-language procurement requirement into machine-readable queries and responses.
- Critical reflection: distinguishing what the simple dialogue demonstrates from what would still be required in a real deployment.

## Learning-outcome connection

**LO1 — Identify and critically analyse agent-based systems, differentiating between architectures and approaches.**  
This artefact supports LO1 by demonstrating practical understanding of inter-agent communication using KQML performatives and KIF content, extending the conceptual analysis developed in Collaborative Discussion 2.

**LO3 — Tools and implementation.**  
The activity provides conceptual preparation for LO3, but it is not counted as full implementation evidence because no executable agent system was deployed or evaluated.
