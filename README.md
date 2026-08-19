# ALMA Research

**Research Initiative on Evidence-Based Cognitive Architecture for Long-Term Psychological Understanding**

ALMA Research investigates how artificial intelligence can build cumulative psychological understanding through evidence-based reasoning rather than engagement optimization.

The project explores a new class of cognitive architectures designed to model human psychological patterns across multiple conversations while maintaining explicit uncertainty, competing hypotheses, evidence, and longitudinal learning.

The objective is not prediction or persuasion, but evidence-based cognitive modeling that can support deeper self-understanding and long-term relational understanding.

---

## Research Motivation

Most conversational AI systems are optimized primarily for the quality of the immediate response.

ALMA explores a different direction.

Instead of generating isolated responses, ALMA incrementally constructs an evolving **Cognitive Model** representing accumulated understanding across interactions.

The system is designed to preserve evidence, distinguish observations from hypotheses, maintain uncertainty, and allow competing explanations to coexist until sufficient information is available.

This creates a foundation for longitudinal reasoning rather than one-off conversational responses.

---

## Core Principle

### LLM provides reasoning. ALMA provides cognitive continuity.

The LLM is intentionally given substantial freedom to:

- interpret information;
- identify patterns;
- formulate hypotheses;
- reason about relationships between observations;
- generate clarification questions;
- explore possible explanations.

ALMA remains responsible for the persistent cognitive model.

The LLM does not independently own or silently rewrite that model.

The intended architecture is:

```text
User information
       ↓
      ALMA
       ↓
Relevant context
       ↓
      LLM
       ↓
Reasoning / hypotheses / questions
       ↓
      ALMA
       ↓
Validation
       ↓
Evidence + Cognitive Model
```

When information is insufficient, ALMA can preserve uncertainty and request additional user context instead of forcing a conclusion.

---

## Current Prototype

ALMA has progressed from conceptual architecture research to a working AI prototype.

The current core includes working mechanisms for:

- observations;
- hypotheses;
- evidence;
- memory analysis;
- memory reasoning;
- relationship reasoning;
- reasoning orchestration;
- cognitive model updates;
- uncertainty handling;
- clarification questions;
- user-input escalation;
- Conversation Guard;
- LLM integration;
- cognitive model ownership and validation.

The prototype has also validated the basic clarification and adaptive reasoning loop:

```text
Observation
    ↓
Memory Analysis
    ↓
Memory Reasoning
    ↓
Cognitive Model
    ↓
Reasoning
    ↓
Uncertainty / Missing Context
    ↓
User Question
    ↓
User Answer
    ↓
New Observation
    ↓
Model Update
```

The system is therefore no longer only a conceptual architecture. It is an actively developed working prototype.

---

## Conversation Guard

ALMA includes a Conversation Guard layer designed to preserve the boundaries of the cognitive dialogue while allowing the LLM substantial reasoning freedom.

The Guard can identify situations such as:

```text
NORMAL
    ↓
ordinary processing

TOPIC_DRIFT
    ↓
message is unrelated to the current cognitive goal

RELEVANCE_CHECK
    ↓
user claims a connection, but the relevance is unclear

HYPOTHESIS_CHECK
    ↓
new information may conflict with an existing model
```

The Guard does not replace the reasoning system.

Its purpose is to signal when additional reasoning or clarification may be required.

This is particularly important when a user introduces an unrelated topic and then claims that it is directly connected to an existing psychological issue. ALMA should not automatically accept or reject that connection without examining the available context.

---

## Adaptive Dialogue

One of the central directions of the current prototype is an adaptive dialogue in which the next question is determined by the current cognitive model rather than by a fixed questionnaire.

The intended flow is:

```text
User Goals
    ↓
Initial Assessment
    ↓
Initial Cognitive Profile
    ↓
Adaptive Question
    ↓
User Answer
    ↓
Observation
    ↓
ALMA Reasoning
    ↓
Cognitive Model
    ↓
Next Adaptive Question
```

The initial prototype target is approximately **30 questions**.

This is an operational prototype target, not a scientifically validated test length.

The objective is to explore whether ALMA can dynamically:

- identify important patterns;
- clarify ambiguous answers;
- investigate contradictions;
- identify missing context;
- follow the user's goals;
- avoid redundant questioning;
- improve its understanding through each answer.

The user answers freely, while ALMA and the LLM determine what should be explored next.

---

## Product Direction

The research architecture is being developed toward a usable ALMA product.

The intended user journey is:

```text
Technical Onboarding
        ↓
User Goals
        ↓
Goal-Specific Assessment
        ↓
Portrait #1
        ↓
Adaptive Dialogue
        ↓
LEVEL 1
Personal Cognitive Profile
        ↓
Document / Conversation Analysis
        ↓
LEVEL 2+
Advanced Capabilities
```

### Initial onboarding

The first layer collects basic technical/profile information required to begin interaction.

### User goals

The user selects what they want ALMA to help them understand, potentially choosing multiple goals.

Examples include:

- understanding oneself better;
- understanding relationship patterns;
- recovering after a breakup;
- improving communication;
- understanding recurring emotional patterns;
- preparing for a future relationship;
- exploring compatibility.

### Goal-specific assessment

The long-term product should not rely on one universal questionnaire for every user.

The intended direction is:

```text
User Goal
    ↓
Relevant Psychological Domains
    ↓
Targeted Assessment
```

Different goals may require different assessment structures.

The current assessment remains a prototype. Production-level psychological assessment modules will require collaboration with qualified psychologists and relevant domain experts.

---

## Portrait #1

After initial onboarding, goals, and assessment information are available, ALMA creates an initial working representation of the user.

### Portrait #1 — Initial Cognitive Profile

Portrait #1 is not intended to be:

- a diagnosis;
- a final psychological assessment;
- a permanent personality classification.

It is a working model based on the evidence available at that stage.

It can contain:

- emerging patterns;
- supporting evidence;
- uncertainties;
- unresolved questions;
- areas requiring additional context.

The model is expected to evolve as new evidence appears.

---

## Level 1 — Personal Cognitive Profile

The first major product milestone is:

### ALMA Level 1

At Level 1, ALMA has established a meaningful evidence-based personal cognitive profile.

The intended Level 1 experience includes:

- Personal Cognitive Profile;
- adaptive dialogue;
- evolving understanding;
- continued free conversation;
- analysis of additional user-provided material.

Level 1 is an evolving model, not a final assessment.

---

## Document and Conversation Analysis

After Level 1, the user can provide external material for analysis.

The initial target formats include:

- Word;
- DOC;
- DOCX;
- PDF.

A primary use case is analysis of conversations or correspondence.

The intended architecture is:

```text
Document
    ↓
Text Extraction
    ↓
Conversation / Content Structuring
    ↓
Observations
    ↓
Memory Analysis
    ↓
Memory Reasoning
    ↓
LLM Reasoning
    ↓
ALMA Validation
    ↓
Cognitive Model Update
```

Uploaded material becomes an additional source of evidence.

It is not automatically treated as psychological truth.

This distinction is especially important when analyzing conversations involving other people.

---

## Level 2 and Beyond

ALMA is intended to progressively unlock additional capabilities as the user's cognitive model becomes more developed.

Potential future capabilities include:

- Partner Compatibility;
- Relationship Analysis;
- Friend Compatibility;
- Find a Partner;
- Find Friends;
- additional personalized AI capabilities.

Some future capabilities may be visible in the product interface before they become active.

These inactive features communicate the longer-term product direction without implying that the functionality has already been implemented.

The exact boundaries of Level 2, Level 3, and later levels will evolve with research and product development.

---

## Psychology and Domain Validation

The engineering architecture can be developed before a fully validated psychological assessment system exists.

However, production-level psychological assessment and interpretation will require collaboration with qualified professionals.

Future expert collaboration is expected to contribute to:

- assessment design;
- psychological constructs;
- question selection;
- goal-specific assessment modules;
- interpretation frameworks;
- validation;
- safety boundaries;
- non-clinical / clinical distinctions;
- research methodology.

The current prototype should therefore be understood as an AI reasoning and cognitive-modeling platform, not as a scientifically validated diagnostic system.

---

## Current Development Status

### Already implemented / validated

The current ALMA core includes working components for:

- cognitive observations;
- hypotheses;
- evidence;
- memory analysis;
- memory reasoning;
- relationship reasoning;
- reasoning orchestration;
- cognitive model updates;
- uncertainty handling;
- clarification questions;
- user-input escalation;
- Conversation Guard;
- LLM integration;
- cognitive model ownership and validation.

The architecture has been validated through integration testing covering:

- KEEP;
- REVISE;
- CONDITIONAL_EXCEPTION;
- SIBLING;
- CONTRADICTION;
- SPLIT;
- INSUFFICIENT_CONTEXT;
- user question escalation;
- user answer processing;
- evidence preservation;
- model preservation;
- model update;
- no-speculation behavior;
- model safety.

### Currently being developed

The immediate prototype work focuses on:

- improving adaptive question quality;
- making the approximately 30-question dialogue genuinely adaptive;
- connecting the ALMA core to the existing website;
- implementing document upload and analysis;
- enabling Level 1 capabilities;
- preparing visible future-level features.

### Future development

Future work includes:

- goal-specific psychologically grounded assessment modules;
- deeper adaptive assessment;
- richer relationship analysis;
- compatibility capabilities;
- partner/friend discovery;
- advanced personalized functionality;
- professional psychological validation.

---

## Development Strategy

The project is being developed in stages.

### Stage 1 — Engineering Foundation

Build and validate the ALMA cognitive architecture.

### Stage 2 — Working AI Interaction

Connect the cognitive architecture to an adaptive user dialogue.

### Stage 3 — Product Integration

Connect the ALMA core to the existing website.

### Stage 4 — Evidence Expansion

Allow users to provide conversations and documents for analysis.

### Stage 5 — Deeper Cognitive Levels

Gradually unlock additional capabilities as the cognitive model becomes sufficiently developed.

### Stage 6 — Psychological Validation

Work with qualified psychologists and domain experts to develop scientifically grounded assessment and interpretation layers.

---

## Research Areas

Current research areas include:

- Cognitive Architecture
- Longitudinal Psychological Modeling
- Knowledge Representation
- Evidence-Based Reasoning
- Reflection Mechanisms
- Human-AI Interaction
- Explainable Cognitive Systems
- Ethical AI

---

## Publications, Research Demonstrations and Documentation

The ALMA Research repository contains the project's research papers, architectural documents, executive materials, concepts, and historical documentation.

### Prototype Vision

For the current product direction, prototype architecture, user journey, levels, adaptive dialogue, and roadmap:

**[ALMA Prototype Vision & Product Architecture](./ALMA_PROTOTYPE_VISION.md)**

### Research Demonstrations

The following public demonstrations illustrate ALMA AI's evidence-based reasoning approach:

**Kaggle Dataset**  
Synthetic dataset demonstrating observations, evidence, hypotheses, confidence, uncertainty, and revision.
https://www.kaggle.com/datasets/almaairesearch/alma-ai-evidence-based-reasoning-demo-dataset/data?utm_source=chatgpt.com

**Kaggle Notebook**  
Executable demonstration of the ALMA AI evidence-based reasoning framework using the dataset.
https://www.kaggle.com/code/almaairesearch/alma-ai-evidence-based-reasoning-demo?utm_source=chatgpt.com

### Related Repository

The engineering implementation of the cognitive architecture is maintained separately:

**[ALMA-Core](https://github.com/MaksimNagaevEthicalAI/ALMA-Core)**

### Project Website

**https://alma-ai.space/**

---

## Project Website and Research Documentation

Project website and research documentation are maintained through the ALMA project ecosystem and Notion documentation.

---

## Contact

**Author**

Maksim Nagaev

**LinkedIn**

https://www.linkedin.com/in/maksim-nagaev-9a03013a8/

**Project Website**

https://alma-ai.space/

**Research Documentation**

https://button-alyssum-638.notion.site/ALMA-AI-Research-Overview-31745b82b9708019988ecb95b538ed3d

**Email**

alma.ai.research@gmail.com
