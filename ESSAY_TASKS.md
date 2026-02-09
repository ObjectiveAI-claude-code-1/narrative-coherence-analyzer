# Narrative Coherence Analyzer: Task Definitions

This document defines the tasks that comprise the Narrative Coherence Analyzer function. The function produces a 7-dimensional vector representing the relative narrative weight distributed across seven canonical pitch elements. Each task evaluates one element's presence, quality, and contribution to the overall narrative.

---

## Task Architecture Overview

The function requires **seven parallel evaluation tasks**, one for each canonical narrative element. Each task must:

1. Assess the **presence** of the element (explicit, implied, or absent)
2. Evaluate the **quality** of the element if present
3. Consider how the element **integrates** with the broader narrative
4. Output a **relative weight score** that, when combined with other tasks, produces a probability distribution summing to 1

The tasks use `vector.completion` with carefully calibrated response options that capture gradations from "dominant and compelling" to "completely absent."

---

## Task 1: Problem Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to articulating the problem being solved.

**What to Detect**:
- Explicit problem statements ("The problem is...", "Users struggle with...", "The pain point we address...")
- Implicit problems suggested by solution descriptions
- Evidence of problem validation (customer quotes, research data, personal experience)
- Specificity and concreteness of problem articulation
- Magnitude and urgency framing ("$X billion lost annually", "affecting Y million people")
- "Why now" timing arguments that contextualize problem urgency

**Evaluation Criteria**:
- Is the problem explicitly stated or merely assumed?
- Is it specific and concrete, or vague and abstract?
- Is there evidence that others share this problem?
- Does the problem feel significant enough to warrant a venture?
- Is there a temporal dimension (why this problem, now)?

**Response Gradient**:
- Dominant: Problem articulation is the centerpiece of the pitch with extensive evidence, specificity, and emotional resonance
- Strong: Problem is clearly and compellingly stated with supporting validation
- Moderate: Problem is present and understandable but could be more specific or validated
- Light: Problem is mentioned briefly or implied rather than developed
- Absent: No discernible problem framing; pitch jumps directly to solution or other elements

---

## Task 2: Solution Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to describing the proposed solution.

**What to Detect**:
- Product or service descriptions ("We're building...", "Our platform does...", "The product enables...")
- Feature explanations and capability descriptions
- Technical architecture or methodology explanations
- Differentiation from alternatives ("Unlike competitors...", "What makes us different...")
- Demonstrations, screenshots, mockups, or product walkthroughs
- Problem-solution fit arguments connecting solution back to stated problem

**Evaluation Criteria**:
- Is the solution clearly explained in understandable terms?
- Is it differentiated from existing alternatives?
- Does it plausibly address the stated problem?
- Is the level of detail appropriate (enough to understand, not overwhelming)?
- Are there defensibility arguments (why this solution is hard to copy)?

**Response Gradient**:
- Dominant: Solution description dominates the pitch with detailed mechanics, differentiation, and demonstrations
- Strong: Solution is thoroughly explained with clear value proposition and differentiation
- Moderate: Solution is described adequately but missing depth on mechanics or differentiation
- Light: Solution is mentioned but not fully explained; raises more questions than it answers
- Absent: No clear solution described; pitch focuses on problem, market, or other elements without explaining what is being built

---

## Task 3: Market Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to quantifying the market opportunity.

**What to Detect**:
- Market size claims (TAM, SAM, SOM, or equivalent framings)
- Market growth projections and trend analysis
- Segmentation discussions (initial target segments, expansion paths)
- Competitive landscape analysis (existing players, market share)
- Industry statistics and third-party research citations
- Bottom-up vs. top-down sizing methodology discussions

**Evaluation Criteria**:
- Are market size claims present and quantified?
- Is the methodology credible (bottom-up preferred over "1% of huge market")?
- Is market growth or dynamics discussed?
- Is the competitive landscape acknowledged?
- Are initial segments identified for go-to-market focus?

**Response Gradient**:
- Dominant: Extensive market analysis with rigorous sizing, segmentation, competitive mapping, and growth projections
- Strong: Clear market quantification with reasonable methodology and competitive awareness
- Moderate: Market size mentioned with some supporting data but limited depth
- Light: Vague market references ("huge opportunity", "massive market") without quantification
- Absent: No market sizing or opportunity quantification; focus entirely on product or other elements

---

## Task 4: Business Model Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to explaining how the venture makes money.

**What to Detect**:
- Pricing model descriptions (subscription, transactional, freemium, advertising, licensing)
- Revenue mechanics and monetization strategy
- Unit economics discussions (CAC, LTV, margins, payback period)
- Pricing data or pricing tier structures
- Scalability and margin dynamics
- Path to profitability or break-even analysis
- Network effects, lock-in, or switching cost discussions

**Evaluation Criteria**:
- Is the revenue model clearly explained?
- Are pricing specifics provided or at least pricing logic?
- Is there awareness of unit economics, even if early-stage?
- Does the model appear scalable?
- Is there a path to sustainability?

**Response Gradient**:
- Dominant: Comprehensive business model with detailed unit economics, validated pricing, and clear path to profitability
- Strong: Clear revenue mechanics with pricing structure and basic economic logic
- Moderate: Business model is explained at high level but missing unit economics or validation
- Light: Monetization mentioned vaguely ("we'll charge subscriptions", "advertising model") without detail
- Absent: No discussion of how the venture makes or will make money

---

## Task 5: Traction/Proof Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to demonstrating validation and progress.

**What to Detect**:
- Quantitative metrics (revenue, users, growth rate, retention, engagement)
- Customer logos, testimonials, or case studies
- Partnership announcements or letters of intent
- Product milestones (launches, versions, key features shipped)
- Funding or grant announcements
- Press coverage or recognition
- Wait lists, signups, or pre-orders
- Pilot results or beta feedback

**Evaluation Criteria**:
- Are concrete metrics provided with context?
- Is growth trajectory or velocity shown?
- Is the quality of traction meaningful (revenue > signups > downloads)?
- Are there third-party validations (customers, partners, investors)?
- Does traction demonstrate product-market fit signals?

**Response Gradient**:
- Dominant: Extensive traction evidence with compelling metrics, growth curves, customer proof, and validation milestones
- Strong: Clear quantitative traction with meaningful metrics and supporting evidence
- Moderate: Some traction shown but early-stage or limited in scope
- Light: Minimal traction mentioned (early signups, initial interest) or only future projections
- Absent: No traction evidence; pitch is entirely forward-looking or pre-execution

---

## Task 6: Team/Execution Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to establishing team credibility.

**What to Detect**:
- Founder backgrounds and biographies
- Relevant domain experience ("10 years in fintech", "former VP at...")
- Prior startup experience or exits
- Educational credentials
- Advisor or investor introductions
- Team composition and complementary skills
- Personal connection to the problem ("I experienced this pain when...")
- Commitment signals (full-time, skin in the game)

**Evaluation Criteria**:
- Are team backgrounds explicitly presented?
- Is domain expertise demonstrated?
- Are there track record signals (prior successes, relevant accomplishments)?
- Does the team cover key functions (product, tech, sales, operations)?
- Is there a "why us" argument for unique positioning?

**Response Gradient**:
- Dominant: Extensive team focus with detailed backgrounds, clear domain expertise, track record evidence, and "why us" argumentation
- Strong: Team credentials clearly established with relevant experience and complementary skills
- Moderate: Team mentioned with some background but limited depth or differentiation
- Light: Team briefly referenced without meaningful credentialing
- Absent: No team discussion; focus entirely on product, market, or other elements

---

## Task 7: Vision Element Analyzer

**Purpose**: Evaluate how much of the pitch's narrative energy is devoted to articulating long-term ambition and impact.

**What to Detect**:
- Long-term vision statements ("Our mission is...", "We're building toward a world where...")
- Impact narratives (how the world changes if this succeeds)
- Multi-phase roadmaps connecting near-term to long-term
- Expansion visions (new markets, products, geographies)
- Purpose statements beyond financial returns
- Industry transformation narratives
- "10 years from now" framing

**Evaluation Criteria**:
- Is there an articulated vision beyond immediate product?
- Does the vision feel authentic to these founders?
- Is it ambitious enough to inspire?
- Is it grounded enough to be credible?
- Does it connect logically to current activities?

**Response Gradient**:
- Dominant: Compelling, expansive vision that anchors the entire narrative with clear long-term ambition and impact framing
- Strong: Clear vision articulated with authentic ambition and logical connection to current work
- Moderate: Some vision present but either limited in scope or disconnected from execution
- Light: Brief aspirational statements without developed vision narrative
- Absent: Purely tactical focus; no long-term vision or purpose articulation

---

## Output Aggregation

The seven task outputs must be normalized to produce a probability distribution summing to 1. Each task produces a raw score (0-4 scale based on response selection), and the final output divides each score by the sum of all scores.

This ensures:
- Pitches heavily focused on one element show high weight there and lower elsewhere
- Balanced pitches show relatively even distribution
- Completely absent elements score near zero
- The profile shape reveals narrative strategy and emphasis patterns

---

## Cross-Task Considerations

While each task evaluates its element independently, the function implicitly captures narrative coherence through the distribution:

- **Problem-Solution Alignment**: If Problem is strong but Solution is weak (or vice versa), the profile reveals this imbalance
- **Stage Appropriateness**: Pre-revenue pitches should show higher Problem/Solution/Team and lower Traction; the profile reveals whether the narrative matches the stage
- **Completeness**: A pitch missing multiple elements will show concentrated weight in whatever remains
- **Founder Tendencies**: Technical founders often over-index on Solution; repeat entrepreneurs on Team; the profile reveals these patterns

---

## Multimodal Handling

Each task must handle the input consistently regardless of format:

- **Text**: Parse natural language for element-specific signals
- **Image**: Extract text from slides, interpret charts/graphs, read visual hierarchy
- **Audio**: Analyze transcribed content plus tone/emphasis signals
- **Video**: Combine visual and audio understanding
- **Composite**: Aggregate signals across all provided materials

The tasks should normalize for format—a well-designed slide communicating Problem is equivalent to a well-written paragraph doing the same, even though surface manifestations differ.
