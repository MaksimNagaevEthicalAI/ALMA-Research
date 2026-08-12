# ALMA AI — Prototype Vision & Product Architecture

## 1. Overview

ALMA AI is being developed as an AI system for building and continuously refining a user's cognitive model through evidence-based interaction.

ALMA is not designed as a conventional dating application, a static personality test, or a therapy replacement.

The core product idea is a progressive process:

**initial information → user goals → targeted assessment → initial cognitive profile → adaptive dialogue → evolving cognitive model → contextual analysis → higher-level capabilities**

The current prototype focuses on validating this architecture and bringing the core ALMA reasoning system into a usable product.

---

## 2. Core Architectural Principle

### LLM provides reasoning. ALMA provides cognitive continuity.

The LLM is intentionally given substantial freedom to:

- interpret information;
- identify patterns;
- formulate hypotheses;
- reason about relationships between observations;
- generate clarification questions;
- determine what information may be useful next.

ALMA remains responsible for the long-term cognitive model.

The LLM does not independently modify the persistent cognitive model.

Instead:

1. ALMA provides relevant context to the LLM.
2. The LLM performs interpretation and reasoning.
3. ALMA validates whether the reasoning is sufficient.
4. ALMA decides how the result relates to the existing cognitive model.
5. Evidence is preserved.
6. Uncertainty is retained when the available information is insufficient.
7. If necessary, ALMA asks the user for missing context.
8. The user's answer becomes a new observation and enters the reasoning process again.

This separation is fundamental to the architecture.

---

# 3. Current Product Entry Flow

The current website already contains the initial user journey.

## Step 1 — Technical Onboarding

The first questionnaire collects basic technical/profile information required to start the interaction.

This layer is intentionally minimal.

It is not intended to produce a psychological conclusion.

---

## Step 2 — User Goals

The user tells ALMA what they want to understand or achieve.

Multiple goals may be selected.

Examples include:

- understanding oneself better;
- understanding relationship patterns;
- recovering after a breakup;
- improving communication;
- understanding recurring emotional patterns;
- preparing for a future relationship;
- exploring compatibility.

The user's goals are important because they influence what ALMA needs to understand and which areas should receive greater attention.

---

# 4. Step 3 — Goal-Specific Assessment

The long-term product should not rely on one universal psychological questionnaire for every user.

Instead:

**User goal → relevant psychological domains → targeted assessment**

Different goals may require different assessment structures.

For example, a user focused on:

- self-understanding;
- relationship recovery;
- communication;
- compatibility;

may require different initial areas of exploration.

### Prototype status

The current questionnaire is still a demonstration implementation.

A production-quality psychological assessment layer should be designed and validated with qualified psychologists and other relevant domain experts.

The engineering prototype therefore distinguishes between:

**AI-driven exploratory assessment**

and

**scientifically validated psychological instruments**.

The latter is a future stage of the product.

---

# 5. Initial Cognitive Profile — Portrait #1

After the initial profile, goals, and assessment information are available, ALMA sends the relevant information to the LLM for an initial interpretation.

The result is the first working understanding of the user:

### Portrait #1 — Initial Cognitive Profile

Portrait #1 is not intended to be:

- a diagnosis;
- a final psychological assessment;
- a permanent personality classification.

It is a working cognitive model based on the evidence available at that point.

The model contains:

- emerging patterns;
- supporting evidence;
- uncertainties;
- unresolved questions;
- areas requiring additional context.

The model is expected to evolve.

---

# 6. Adaptive Dialogue

Portrait #1 becomes the starting point for an adaptive dialogue.

The user does not simply receive another fixed questionnaire.

Instead, ALMA and the LLM determine what should be explored next based on:

- the user's goals;
- the current cognitive model;
- observed patterns;
- unresolved hypotheses;
- contradictions or apparent conflicts;
- missing context;
- knowledge gaps;
- previous questions and answers.

The basic loop is:

```text
Portrait #1
    ↓
Current understanding
    ↓
Knowledge gaps / uncertainty
    ↓
LLM proposes next question
    ↓
User answer
    ↓
Observation
    ↓
ALMA reasoning and validation
    ↓
Cognitive model update
    ↓
Next question
```

The user answers freely, but the structure of the exploratory process is primarily driven by ALMA and the LLM rather than by a predetermined questionnaire.

---

# 7. Adaptive Dialogue — MVP Target

The first prototype target is an adaptive dialogue of approximately **30 questions**.

The number is an operational target rather than a scientifically validated test length.

The dialogue should be able to:

- identify important behavioral patterns;
- clarify ambiguous answers;
- investigate meaningful contradictions;
- explore relevant contexts;
- identify areas that remain poorly understood;
- follow the user's stated goals;
- avoid repeatedly asking questions that no longer add useful information.

The dialogue may eventually stop earlier when sufficient understanding has been reached, or continue differently depending on the user's needs.

For the MVP, approximately 30 questions provides a practical boundary for testing the adaptive reasoning process.

---

# 8. Adaptive Question Quality

A major development goal is not merely to generate questions, but to generate **useful questions**.

Before selecting the next question, ALMA should increasingly consider:

1. What is already known?
2. What is still uncertain?
3. Which user goals have been insufficiently explored?
4. Which hypotheses require additional evidence?
5. Did the user actually answer the previous question?
6. Did the user change the topic?
7. Is the new information relevant to the current line of reasoning?
8. Would another question materially improve the cognitive model?

This is what distinguishes adaptive dialogue from a dynamic-looking questionnaire.

---

# 9. Conversation Guard

ALMA includes a Conversation Guard layer intended to preserve the boundaries of the cognitive dialogue while allowing the LLM substantial reasoning freedom.

The Guard can identify situations such as:

```text
NORMAL
    ↓
ordinary processing

TOPIC_DRIFT
    ↓
the message is unrelated to the current cognitive goal

RELEVANCE_CHECK
    ↓
the user claims a connection, but the relevance is unclear

HYPOTHESIS_CHECK
    ↓
new information may conflict with an existing model
```

The Guard does not own the cognitive model.

Its role is to signal when additional reasoning may be necessary.

For example, if a user introduces an unrelated subject and then claims that it is directly connected to an existing psychological topic, ALMA should not automatically accept or reject the claimed connection.

Instead, it should determine whether additional context is required.

This allows ALMA to preserve conversational boundaries without artificially restricting the LLM.

---

# 10. Clarification and Uncertainty

ALMA is designed not to invent missing context.

When the available evidence is insufficient to safely determine how two patterns relate, the system can enter:

**INSUFFICIENT_CONTEXT**

The process is:

```text
Insufficient context
        ↓
LLM identifies the missing distinction
        ↓
ALMA generates / requests clarification
        ↓
User provides information
        ↓
Answer becomes a new observation
        ↓
Reasoning is performed again
        ↓
Cognitive model is updated
```

The user's answer is therefore not treated as an unrestricted direct modification of memory.

It is new evidence.

---

# 11. Level 1 — Personal Cognitive Profile

The first meaningful product milestone is:

## ALMA Level 1

At Level 1, ALMA has established an initial personal cognitive profile containing a meaningful set of evidence-supported patterns.

The user can then access additional capabilities.

The intended Level 1 experience includes:

- Personal Cognitive Profile;
- adaptive dialogue;
- evolving understanding;
- continued free conversation;
- analysis of additional user-provided material.

Level 1 is still an evolving model, not a final assessment.

---

# 12. Document and Conversation Analysis

After Level 1, the user can provide external material for analysis.

The first supported document formats are intended to include:

- Word;
- DOC;
- DOCX;
- PDF.

A typical use case is analysis of a conversation or correspondence.

The document layer should not independently produce a psychological conclusion.

Instead, the intended architecture is:

```text
Document
    ↓
Text extraction
    ↓
Conversation reconstruction / structuring
    ↓
Observations
    ↓
Memory Analyzer
    ↓
Memory Reasoner
    ↓
LLM reasoning
    ↓
ALMA validation
    ↓
Cognitive model update
```

The uploaded material becomes another source of evidence.

It is not automatically treated as psychological truth.

This distinction is important when analyzing conversations involving other people.

---

# 13. Product Levels and Progressive Capabilities

ALMA is intended to grow its capabilities as the user's cognitive model becomes more developed.

A simplified roadmap is:

```text
LEVEL 0
Onboarding
    ↓
Technical profile
    ↓
User goals
    ↓
Goal-specific assessment
    ↓
Initial Cognitive Profile
    ↓
Adaptive Dialogue
    ↓
LEVEL 1
Personal Cognitive Profile
    ↓
Conversation / Document Analysis
    ↓
LEVEL 2
Advanced relationship and compatibility capabilities
    ↓
LEVEL 3+
Further personalized capabilities
```

The exact boundaries between levels will evolve as the product is developed.

---

# 14. Future Level 2+ Capabilities

The product interface may expose future capabilities before they are active.

Examples include:

- Partner Compatibility;
- Relationship Analysis;
- Friend Compatibility;
- Find a Partner;
- Find Friends;
- additional personalized AI capabilities.

These functions may initially appear as inactive or locked features.

This serves two purposes:

1. it communicates the long-term product direction to users;
2. it makes the product roadmap visible to potential partners and investors.

The existence of a visible feature does not imply that the capability is already implemented.

---

# 15. Psychology and Domain Validation

The engineering architecture can be developed independently of a fully validated psychological assessment system.

However, a production-level psychological layer will require collaboration with qualified professionals.

Future expert collaboration is expected to contribute to:

- assessment design;
- psychological constructs;
- question selection;
- domain-specific assessment modules;
- interpretation frameworks;
- validation;
- safety boundaries;
- non-clinical / clinical distinctions;
- research methodology.

The current engineering prototype should therefore be understood as an AI reasoning and cognitive-modeling platform, not as a scientifically validated diagnostic system.

---

# 16. Current Prototype vs. Future Product

## Already implemented / validated

The current ALMA core includes working components for:

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

The adaptive dialogue prototype has also demonstrated the basic loop:

```text
Questionnaire
    ↓
Portrait #1
    ↓
Adaptive question
    ↓
User answer
    ↓
Observation
    ↓
ALMA reasoning
    ↓
Cognitive model
    ↓
Next adaptive question
```

## Currently being developed

The immediate prototype work focuses on:

- improving adaptive question quality;
- making the approximately 30-question dialogue genuinely adaptive;
- connecting the ALMA core to the existing website;
- implementing document upload and analysis;
- enabling Level 1 capabilities;
- preparing visible future-level features.

## Future development

Future work includes:

- goal-specific psychologically grounded assessment modules;
- deeper adaptive assessment;
- richer relationship analysis;
- compatibility capabilities;
- partner/friend discovery;
- advanced personalized functionality;
- professional psychological validation.

---

# 17. Prototype Development Strategy

The current strategy is deliberately staged.

### Stage 1 — Engineering foundation

Build and validate the ALMA cognitive architecture.

### Stage 2 — Working AI interaction

Connect the cognitive architecture to an adaptive user dialogue.

### Stage 3 — Product integration

Connect the ALMA core to the existing website.

### Stage 4 — Evidence expansion

Allow users to provide conversations and documents for analysis.

### Stage 5 — Deeper cognitive levels

Gradually unlock additional capabilities as the cognitive model becomes sufficiently developed.

### Stage 6 — Psychological validation

Work with qualified psychologists and domain experts to develop scientifically grounded assessment and interpretation layers.

---

# 18. ALMA's Core Product Principle

> **LLM provides reasoning.  
> ALMA provides cognitive continuity.**

The LLM may explore, interpret, question, challenge assumptions, identify patterns, and generate hypotheses with substantial freedom.

ALMA remains responsible for:

- maintaining the persistent cognitive model;
- evaluating whether reasoning is sufficient;
- preserving evidence;
- recognizing uncertainty;
- requesting missing information;
- determining when and how the model can change.

This separation is the foundation on which the product is being built.

---

# 19. Vision

The immediate goal is not to build every future feature at once.

The immediate goal is to build a working ALMA loop:

```text
User
  ↓
Goals
  ↓
Assessment
  ↓
Portrait #1
  ↓
Adaptive Dialogue
  ↓
Cognitive Model
  ↓
Free Conversation
  ↓
Document / Conversation Analysis
  ↓
Deeper Understanding
  ↓
Higher-Level Capabilities
```

The prototype is therefore not a collection of disconnected AI features.

It is the first implementation of a progressive cognitive system in which the user's relationship with ALMA becomes richer as ALMA's understanding becomes deeper.
