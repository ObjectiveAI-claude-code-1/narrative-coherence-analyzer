# Narrative Coherence Analyzer: Task Definitions

This document defines the tasks that comprise the Narrative Coherence Analyzer function. Each task evaluates the presence and quality of one of the seven canonical narrative elements in a startup pitch. The function outputs a 7-element vector that sums to 1.0, revealing the relative strength of each narrative element.

---

## Task Architecture Overview

The function uses 7 parallel evaluation tasks—one for each canonical narrative element. Each task produces a raw score from 0.0 to 1.0 representing the strength of that element. The final output normalizes these scores to sum to 1.0, creating a distribution that reveals relative emphasis.

Each task evaluates both **presence** (is this element addressed at all?) and **quality** (if present, how compelling is it?). Elements that are absent receive scores near 0.0. Elements that are present but weak receive modest scores. Elements that are strongly present and well-articulated receive high scores.

---

## Task 1: Problem Strength Evaluation

**Purpose**: Evaluate whether the pitch articulates a clear, compelling problem that creates narrative tension.

**Evaluation Criteria**:
- **Presence**: Is the problem explicitly stated, implied through context, or entirely absent? Pitches that leap directly to solutions without establishing the problem should score low.
- **Specificity**: Is the problem concrete and measurable ("Restaurants throw away 30% of inventory") or vague and abstract ("Businesses struggle with efficiency")?
- **Magnitude**: Does the problem represent significant pain—either widespread (affecting many) or acute (severe for those affected)?
- **Urgency**: Does the problem demand immediate attention, or is it a mild inconvenience people tolerate?
- **Credibility**: Are claims about the problem supported by data, research, or obvious observation? Inflated claims undermine trust.
- **Emotional Resonance**: Does the problem description create visceral understanding? Does the audience *feel* the pain?

**Response Options** (5-level scale):
1. Exceptional - Problem is explicit, specific, large in magnitude, urgent, credible, and emotionally resonant
2. Strong - Problem is clearly articulated with most quality dimensions present
3. Moderate - Problem is present but lacks specificity, magnitude, or credibility
4. Weak - Problem is vaguely implied or partially addressed
5. Absent - No problem articulation; pitch jumps to solution or other elements

---

## Task 2: Solution Strength Evaluation

**Purpose**: Evaluate whether the pitch presents a clear, credible solution that directly addresses the stated problem.

**Evaluation Criteria**:
- **Presence**: Is the solution explicitly described, merely implied through a demo or description, or unclear?
- **Clarity**: Can the audience understand what the solution actually does? Technical jargon and feature lists obscure rather than illuminate.
- **Problem-Solution Fit**: Does the solution directly address the core problem? Tangential solutions suggest misalignment.
- **Defensibility**: Is it clear why this solution is better than alternatives and difficult to replicate?
- **Elegance**: Does the solution feel like a natural response to the problem? Elegant solutions have an "of course" quality.
- **Feasibility**: Is the solution buildable with current technology and resources? Fantastical solutions undermine credibility.

**Response Options** (5-level scale):
1. Exceptional - Solution is crystal clear, directly addresses the problem, defensible, elegant, and feasible
2. Strong - Solution is well-articulated with clear problem-solution fit
3. Moderate - Solution is present but lacks clarity, defensibility, or clear connection to problem
4. Weak - Solution is vague, overly complex, or poorly connected to stated problem
5. Absent - No clear solution articulation

---

## Task 3: Market Strength Evaluation

**Purpose**: Evaluate whether the pitch establishes meaningful market stakes through sizing, segmentation, and accessibility analysis.

**Evaluation Criteria**:
- **Presence**: Is market size explicitly stated (TAM/SAM/SOM), implied through industry references, or absent?
- **Credibility**: Are market figures from credible sources? Bottoms-up calculations are more credible than top-down claims.
- **Specificity**: Is the target market clearly defined, or vaguely "everyone"? Well-defined markets suggest strategic clarity.
- **Accessibility**: Can this startup actually reach this market, or is it theoretically large but practically inaccessible?
- **Dynamics**: Does the pitch address market growth, trends, or timing considerations?
- **Segmentation**: Does the pitch demonstrate understanding of market heterogeneity and a clear entry wedge?

**Response Options** (5-level scale):
1. Exceptional - Market is precisely sized with credible methodology, clearly segmented, accessible, with favorable dynamics
2. Strong - Market is well-defined with reasonable sizing and clear target segment
3. Moderate - Market is mentioned but sizing is vague, top-down, or unsupported
4. Weak - Market is briefly implied without sizing or segmentation
5. Absent - No market information provided

---

## Task 4: Business Model Strength Evaluation

**Purpose**: Evaluate whether the pitch explains how value is captured and the business sustains itself.

**Evaluation Criteria**:
- **Presence**: Is the business model explicitly described, vaguely mentioned ("we'll monetize later"), or absent?
- **Clarity**: Is it immediately apparent how money flows—who pays whom, for what, and when?
- **Alignment**: Does the model align incentives between the startup and customers? Value-extracting models are fragile.
- **Scalability**: Can the model grow without proportional cost increases? Recurring revenue, network effects, and marketplace dynamics suggest scalability.
- **Defensibility**: Does the model create switching costs, data advantages, or other moats?
- **Credibility**: Are pricing assumptions realistic? Are comparisons to successful models apt?

**Response Options** (5-level scale):
1. Exceptional - Business model is crystal clear, scalable, defensible, and well-aligned with customer value
2. Strong - Business model is clearly articulated with reasonable unit economics
3. Moderate - Business model is mentioned but lacks detail on pricing, margins, or scalability
4. Weak - Business model is vaguely implied or deferred ("focused on growth first")
5. Absent - No business model information provided

---

## Task 5: Traction/Proof Strength Evaluation

**Purpose**: Evaluate whether the pitch provides evidence that the solution works and the business is gaining momentum.

**Evaluation Criteria**:
- **Presence**: Is traction explicitly quantified (revenue, users, growth rates), implied through logos/testimonials, or absent?
- **Relevance**: Do the metrics cited actually matter for this business? Engagement and financial metrics are more compelling than vanity metrics.
- **Magnitude**: Are the numbers impressive for the stage? Context matters—$10K MRR may be exceptional or concerning depending on company age.
- **Trajectory**: What is the growth rate? A smaller base growing quickly may be more compelling than a larger base stagnating.
- **Quality**: What is the quality of customers/users? Enterprise logos and high-value contracts signal stronger traction.
- **Recency**: Is the traction current, or does the pitch rely on outdated metrics?

**Response Options** (5-level scale):
1. Exceptional - Strong, relevant metrics with impressive magnitude, clear growth trajectory, and quality customers
2. Strong - Clear traction with meaningful metrics and positive trajectory
3. Moderate - Some traction mentioned but metrics are limited, dated, or less relevant
4. Weak - Minimal proof points—waitlist signups, letters of intent, or pilot discussions
5. Absent - No traction or proof provided (pre-launch with no validation)

---

## Task 6: Team/Execution Strength Evaluation

**Purpose**: Evaluate whether the pitch establishes why this specific team can execute the vision.

**Evaluation Criteria**:
- **Presence**: Are team credentials explicitly listed, implied through execution quality, or absent?
- **Relevant Experience**: Does the team have experience directly relevant to the problem—domain expertise, prior startup experience, technical skills?
- **Track Record**: Have team members built and shipped products? Have they worked together? Have they demonstrated execution under uncertainty?
- **Founder-Market Fit**: Why is this team uniquely positioned? Personal connection to the problem, proprietary insights, or unique access?
- **Completeness**: Does the team have key capabilities (technical, commercial, operational), or are there obvious gaps?
- **Commitment**: Are founders full-time and all-in, or is this a side project?

**Response Options** (5-level scale):
1. Exceptional - Team has exceptional relevant experience, proven track record, strong founder-market fit, and complete capabilities
2. Strong - Team credentials are clear with relevant experience and demonstrated ability
3. Moderate - Team is mentioned but credentials are limited or relevance is unclear
4. Weak - Team is briefly referenced without meaningful credential information
5. Absent - No team information provided

---

## Task 7: Vision Strength Evaluation

**Purpose**: Evaluate whether the pitch articulates a compelling long-term vision that transforms the product into a world-changing possibility.

**Evaluation Criteria**:
- **Presence**: Is vision explicitly articulated ("We envision a world where..."), implied through logical extension, or absent?
- **Ambition**: Is the vision big enough to be exciting? Great visions inspire and energize.
- **Plausibility**: Is there a credible path from current state to the vision? Disconnected visions feel fantastical.
- **Specificity**: Is the vision concrete enough to be actionable, or so vague it provides no direction?
- **Differentiation**: Does this vision describe a future only this company can create, or a generic better world?
- **Emotional Resonance**: Does the vision create excitement and buy-in? Does it make people want to join this journey?

**Response Options** (5-level scale):
1. Exceptional - Vision is ambitious, plausible, specific, differentiated, and emotionally compelling
2. Strong - Vision is clearly articulated with meaningful ambition and plausible path
3. Moderate - Vision is present but generic, vague, or disconnected from current work
4. Weak - Vision is briefly implied without meaningful articulation
5. Absent - No vision provided; pitch is purely tactical/immediate

---

## Output Aggregation

Each task produces a raw score from its 5-level response scale:
- Exceptional = 1.0
- Strong = 0.75
- Moderate = 0.5
- Weak = 0.25
- Absent = 0.0

The seven raw scores are then normalized to sum to 1.0:

```
normalized_score[i] = raw_score[i] / sum(all_raw_scores)
```

If all raw scores are 0 (completely empty pitch), equal weights of 1/7 ≈ 0.143 are assigned to each element.

The output vector format is:
```
[problem, solution, market, business_model, traction, team, vision]
```

---

## Interpretation Guide

**Balanced Distribution** (each element ~0.14): The pitch addresses all canonical elements with roughly equal strength. This is rare but indicates comprehensive storytelling.

**Problem-Solution Heavy** (high scores in positions 0-1): The pitch focuses on what's wrong and how to fix it, potentially lacking business fundamentals or proof.

**Traction-Team Heavy** (high scores in positions 4-5): The pitch emphasizes execution and results over vision and market opportunity.

**Vision-Light** (near-zero in position 6): The pitch is tactical and immediate, lacking inspiring long-term destination.

**Business Model Absent** (near-zero in position 3): The pitch hasn't addressed monetization—common in early-stage but a gap for later fundraising.

---

## Edge Cases

**Empty or Minimal Pitches**: Pitches with very little content should have low raw scores across all elements. Normalization will still produce a distribution, but the absolute weakness is captured in the pre-normalization scores.

**Single-Element Pitches**: A pitch that only describes the problem (e.g., "Food waste is a $50B problem") should score highly on problem and near-zero on everything else.

**Multimodal Pitches**: For video or image inputs, the evaluator should consider visual and auditory evidence of each element—demo videos convey solution, customer logos convey traction, founder presence conveys team.

**Composite Pitches**: When input is an array of multiple media, consider all elements together as a unified pitch narrative.
