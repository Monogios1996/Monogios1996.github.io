---
title: Unit 8 — Constituency-Based Parse Trees
permalink: /modules/intelligent-agents/evidence/artefacts/unit-08-constituency-parse-trees/
---

# Unit 8 — Constituency-Based Parse Trees

**Activity:** Create constituency-based parse trees for the three supplied sentences and add the completed trees to the e-Portfolio.

**Type:** Individual learning activity  
**Status:** Completed  
**Supporting module learning outcome:** LO3 — use of intelligent-system tools and techniques  
**Activity focus:** Natural-language structure, constituency parsing and syntactic ambiguity

## Completed parse trees

### 1. The government raised interest rates.

```text
S
├── NP
│   ├── Det: The
│   └── N: government
└── VP
    ├── V: raised
    └── NP
        ├── N: interest
        └── N: rates
```

### 2. The internet gives everyone a voice.

```text
S
├── NP
│   ├── Det: The
│   └── N: internet
└── VP
    ├── V: gives
    ├── NP
    │   └── Pron: everyone
    └── NP
        ├── Det: a
        └── N: voice
```

### 3. The man saw the dog with the telescope.

This sentence is syntactically ambiguous, so it has two valid constituency structures.

#### Interpretation A — the man used the telescope

Here the prepositional phrase **with the telescope** attaches to the verb phrase.

```text
S
├── NP
│   ├── Det: The
│   └── N: man
└── VP
    ├── V: saw
    ├── NP
    │   ├── Det: the
    │   └── N: dog
    └── PP
        ├── P: with
        └── NP
            ├── Det: the
            └── N: telescope
```

#### Interpretation B — the dog was with the telescope

Here the prepositional phrase **with the telescope** attaches to the noun phrase **the dog**.

```text
S
├── NP
│   ├── Det: The
│   └── N: man
└── VP
    ├── V: saw
    └── NP
        ├── Det: the
        ├── N: dog
        └── PP
            ├── P: with
            └── NP
                ├── Det: the
                └── N: telescope
```

## What I learned

The activity shows that constituency parsing represents language hierarchically by grouping words into phrases such as noun phrases (NP), verb phrases (VP) and prepositional phrases (PP). The third sentence demonstrates syntactic ambiguity: changing where the PP attaches changes the interpretation even though the words remain identical.

This is relevant to intelligent language-processing systems because syntactic structure alone may permit more than one interpretation. Context or semantic information may therefore be needed to determine the intended meaning.

## Limitation

These trees demonstrate manual constituency analysis. They do not by themselves evaluate the accuracy of an automated parser or its performance on larger or more complex language data.
