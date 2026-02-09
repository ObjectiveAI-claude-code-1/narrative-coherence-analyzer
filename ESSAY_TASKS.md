# Narrative Coherence Analyzer: Task Definitions

This document defines the tasks that the Narrative Coherence Analyzer function must perform to produce a 7-element probability distribution representing the relative narrative strength of each canonical element in a startup pitch.

## Architecture Overview

The function must evaluate each of the seven narrative elements across three dimensions (Presence, Quality, and Narrative Flow), then combine these assessments into a normalized probability distribution. The tasks are organized into three phases:

1. **Element Evaluation Tasks** (21 tasks): Assess presence, quality, and flow for each of the 7 elements
2. **Raw Score Computation Tasks** (7 tasks): Combine the three dimensions into a raw score per element
3. **Normalization Task** (1 task): Convert raw scores to a probability distribution summing to 1.0

---

## Phase 1: Element Evaluation Tasks

### Task 1.1: Problem Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits the PROBLEM being solved.

**Evaluation criteria:**
- Does the pitch explicitly describe a pain point, challenge, or unmet need?
- Is there quantification of the problem's scope or impact?
- Does the pitch demonstrate authentic understanding of who experiences this problem?
- Is the problem articulated with specificity (concrete examples) or abstractly?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 1.2: Problem Element - Quality Assessment

If the Problem is present, evaluate how compelling and well-articulated it is.

**Evaluation criteria:**
- **Specificity**: Is the problem concrete and tangible rather than vague?
- **Urgency**: Does the problem demand immediate attention?
- **Pain Intensity**: Is this a "hair on fire" problem or mild inconvenience?
- **Universality**: Does the problem resonate broadly enough to matter?
- **Authenticity**: Does the founder demonstrate genuine understanding, perhaps through personal experience?

**Output:** Quality score from 0 (poor articulation) to 1 (exceptional, conviction-creating articulation)

---

### Task 1.3: Problem Element - Narrative Flow Assessment

Evaluate how well the Problem connects to and sets up the other narrative elements.

**Evaluation criteria:**
- Does the Problem naturally lead to the Solution presented?
- Does the Problem's scope align with the Market opportunity claimed?
- Is the Problem framed in a way that makes the Team's involvement logical?
- Does the Problem set stakes that make the Vision meaningful?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

### Task 2.1: Solution Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits the SOLUTION being offered.

**Evaluation criteria:**
- Is there a clear description of what the product or service actually does?
- Are the key features or capabilities articulated?
- Is the solution's mechanism of action explained?
- Is there demonstration or evidence of the solution (demo, prototype, screenshots)?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 2.2: Solution Element - Quality Assessment

If the Solution is present, evaluate how compelling and well-articulated it is.

**Evaluation criteria:**
- **Clarity**: Can the solution be understood quickly and completely?
- **Elegance**: Does it feel like the *right* answer, creating an "aha" moment?
- **Differentiation**: What makes this fundamentally different from existing approaches?
- **Feasibility**: Does the solution seem achievable rather than science fiction?
- **Problem-Solution Fit**: Does it address the specific problem articulated?
- **Demonstrability**: Is the solution shown, not just told?

**Output:** Quality score from 0 (poor articulation) to 1 (exceptional, conviction-creating articulation)

---

### Task 2.3: Solution Element - Narrative Flow Assessment

Evaluate how well the Solution connects to and flows from/to other narrative elements.

**Evaluation criteria:**
- Does the Solution directly address the Problem stated?
- Does the Solution justify the Market opportunity claimed?
- Does the Solution's complexity match the Team's capabilities?
- Does the Solution serve as a credible path toward the Vision?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

### Task 3.1: Market Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits the MARKET opportunity.

**Evaluation criteria:**
- Is there discussion of market size (TAM, SAM, SOM)?
- Are target customer segments identified?
- Is market growth or dynamics mentioned?
- Is the competitive landscape addressed?
- Is timing discussed (why now)?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 3.2: Market Element - Quality Assessment

If the Market is present, evaluate how compelling and well-articulated it is.

**Evaluation criteria:**
- **Size**: Is the market large enough to support a significant outcome?
- **Growth**: Is the market expanding with tailwinds?
- **Accessibility**: Can this market actually be reached?
- **Segmentation**: Does the pitch demonstrate understanding of customer segments?
- **Timing**: Is there a compelling "why now" argument?
- **Competitive Landscape**: Is the competitive environment accurately characterized?

**Output:** Quality score from 0 (poor articulation) to 1 (exceptional, conviction-creating articulation)

---

### Task 3.3: Market Element - Narrative Flow Assessment

Evaluate how well the Market connects to and integrates with other narrative elements.

**Evaluation criteria:**
- Does the Market size align with the Problem's scope?
- Does the Market justify the Business Model's revenue potential?
- Does the Market timing align with the Solution's readiness?
- Does the Market opportunity warrant the Vision's ambition?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

### Task 4.1: Business Model Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits the BUSINESS MODEL.

**Evaluation criteria:**
- Is there a clear description of how the company makes money?
- Are pricing or monetization mechanisms specified?
- Is customer acquisition strategy mentioned?
- Are unit economics discussed?
- Is there a path to profitability or sustainability articulated?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 4.2: Business Model Element - Quality Assessment

If the Business Model is present, evaluate how compelling and well-articulated it is.

**Evaluation criteria:**
- **Clarity**: Is the monetization mechanism immediately understandable?
- **Alignment**: Does the model align incentives between startup and customers?
- **Defensibility**: Does the model create switching costs or network effects?
- **Scalability**: Can the model scale without proportional cost increases?
- **Proven Patterns**: Does it follow established patterns (SaaS, marketplace, etc.)?
- **Path to Profitability**: Is there a clear trajectory to sustainable economics?

**Output:** Quality score from 0 (poor articulation) to 1 (exceptional, conviction-creating articulation)

---

### Task 4.3: Business Model Element - Narrative Flow Assessment

Evaluate how well the Business Model connects to and integrates with other narrative elements.

**Evaluation criteria:**
- Does the Business Model logically monetize the Solution?
- Does the Business Model's scale potential match the Market size?
- Does the Business Model align with Traction evidence?
- Is the Business Model consistent with the Vision's scope?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

### Task 5.1: Traction Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits TRACTION and proof points.

**Evaluation criteria:**
- Are there quantitative metrics (revenue, users, growth rates)?
- Are customer testimonials or case studies included?
- Are partnerships or notable customers mentioned?
- Are milestones achieved listed?
- Is there social proof (investors, press, awards)?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 5.2: Traction Element - Quality Assessment

If Traction is present, evaluate how compelling and meaningful the evidence is.

**Evaluation criteria:**
- **Quantitative Evidence**: Are there specific, credible numbers?
- **Quality of Metrics**: Are metrics meaningful (revenue, retention) vs. vanity (downloads)?
- **Trend Direction**: Is traction accelerating, stable, or concerning?
- **Social Proof**: Are validators notable and credible?
- **Milestones**: Are achieved milestones meaningful inflection points?
- **Customer Testimonials**: Do real customers express genuine enthusiasm?

**Output:** Quality score from 0 (poor/unconvincing evidence) to 1 (exceptional, compelling proof)

---

### Task 5.3: Traction Element - Narrative Flow Assessment

Evaluate how well Traction connects to and validates other narrative elements.

**Evaluation criteria:**
- Does Traction validate that the Problem is real and Solution works?
- Does Traction support the Market opportunity claimed?
- Does Traction demonstrate the Business Model is viable?
- Does Traction build credibility for the Team's execution ability?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

### Task 6.1: Team Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits the TEAM and execution capability.

**Evaluation criteria:**
- Are founders and key team members introduced?
- Are relevant backgrounds and experiences shared?
- Are roles and responsibilities clarified?
- Are advisors or notable supporters mentioned?
- Is team commitment level addressed?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 6.2: Team Element - Quality Assessment

If Team is present, evaluate how compelling and credible the team presentation is.

**Evaluation criteria:**
- **Relevant Experience**: Does the team have domain expertise?
- **Complementary Skills**: Does the team cover essential functions?
- **Track Record**: Have team members built or scaled companies before?
- **Unfair Advantages**: Does the team have unique access or insights?
- **Cohesion**: Does the team seem like a functioning unit?
- **Commitment**: Is the team fully committed?
- **Self-Awareness**: Does the team acknowledge gaps honestly?

**Output:** Quality score from 0 (poor/unconvincing) to 1 (exceptional, conviction-creating credibility)

---

### Task 6.3: Team Element - Narrative Flow Assessment

Evaluate how well the Team connects to and enables other narrative elements.

**Evaluation criteria:**
- Is the Team's expertise aligned with the Problem domain?
- Does the Team have the skills to build the Solution?
- Does the Team's network support the Market access claimed?
- Does the Traction validate the Team's execution ability?
- Is the Team capable of achieving the Vision?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

### Task 7.1: Vision Element - Presence Assessment

Evaluate whether the startup pitch explicitly addresses, implies, or omits the VISION for the future.

**Evaluation criteria:**
- Is there a description of the future state if successful?
- Are long-term ambitions articulated?
- Is the company's potential impact described?
- Is there a sense of where the journey leads?
- Is the ultimate destination inspiring?

**Output:** Presence score from 0 (absent) to 1 (explicitly and thoroughly addressed)

---

### Task 7.2: Vision Element - Quality Assessment

If Vision is present, evaluate how compelling and inspiring the articulation is.

**Evaluation criteria:**
- **Ambition**: Is the vision big enough to inspire?
- **Clarity**: Can the future state be visualized?
- **Believability**: Is the vision achievable from current starting point?
- **Inspiration**: Does the vision stir emotion?
- **Coherence**: Does the vision connect to problem, solution, and traction?
- **Uniqueness**: Is this a vision only this team could articulate?

**Output:** Quality score from 0 (poor/uninspiring) to 1 (exceptional, movement-inspiring vision)

---

### Task 7.3: Vision Element - Narrative Flow Assessment

Evaluate how well the Vision connects to and elevates other narrative elements.

**Evaluation criteria:**
- Does the Vision represent the ultimate resolution of the Problem?
- Does the Vision show where the Solution leads at full potential?
- Does the Vision justify the Market opportunity's importance?
- Does the Vision explain why this Team is on this mission?
- Does the Vision make the current Traction feel like the beginning of something larger?

**Output:** Flow score from 0 (fragmented/contradictory) to 1 (seamless narrative integration)

---

## Phase 2: Raw Score Computation Tasks

### Task 8.1: Compute Problem Raw Score

Combine the Problem element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40% (an absent element cannot score well)
- Weight Quality at 35% (execution matters)
- Weight Flow at 25% (integration matters)
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Problem score (0 to 1)

---

### Task 8.2: Compute Solution Raw Score

Combine the Solution element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40%
- Weight Quality at 35%
- Weight Flow at 25%
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Solution score (0 to 1)

---

### Task 8.3: Compute Market Raw Score

Combine the Market element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40%
- Weight Quality at 35%
- Weight Flow at 25%
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Market score (0 to 1)

---

### Task 8.4: Compute Business Model Raw Score

Combine the Business Model element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40%
- Weight Quality at 35%
- Weight Flow at 25%
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Business Model score (0 to 1)

---

### Task 8.5: Compute Traction Raw Score

Combine the Traction element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40%
- Weight Quality at 35%
- Weight Flow at 25%
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Traction score (0 to 1)

---

### Task 8.6: Compute Team Raw Score

Combine the Team element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40%
- Weight Quality at 35%
- Weight Flow at 25%
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Team score (0 to 1)

---

### Task 8.7: Compute Vision Raw Score

Combine the Vision element's Presence, Quality, and Flow scores into a single raw score.

**Computation:**
- Weight Presence at 40%
- Weight Quality at 35%
- Weight Flow at 25%
- Apply multiplier: if Presence < 0.3, cap total score at Presence level

**Output:** Raw Vision score (0 to 1)

---

## Phase 3: Normalization Task

### Task 9.1: Normalize to Probability Distribution

Convert the 7 raw scores into a probability distribution that sums to 1.0.

**Computation:**
- Sum all 7 raw scores
- Divide each raw score by the sum
- Handle edge case: if sum is 0 or near-zero, output uniform distribution [0.143, 0.143, 0.143, 0.143, 0.143, 0.143, 0.143]

**Output:** Vector of 7 values summing to 1.0:
- [0]: Problem score
- [1]: Solution score
- [2]: Market score
- [3]: Business Model score
- [4]: Traction score
- [5]: Team score
- [6]: Vision score

---

## Implementation Notes

### Multi-Modal Handling

All Phase 1 evaluation tasks must be capable of processing:
- **Text**: Analyze language, claims, and structure
- **Images**: Interpret visual hierarchy, design choices, and implicit messaging
- **Audio**: Evaluate delivery, emphasis, and vocal confidence alongside content
- **Video**: Assess charisma, body language, visual aids, and theatrical elements
- **Composite arrays**: Synthesize information distributed across multiple modalities

### Scoring Granularity

For Phase 1 tasks, use 5-level ordinal scales that map to scores:
- **Presence**: Absent (0.0), Barely implied (0.25), Implied (0.5), Addressed (0.75), Thoroughly addressed (1.0)
- **Quality**: Poor (0.0), Weak (0.25), Adequate (0.5), Strong (0.75), Exceptional (1.0)
- **Flow**: Contradictory (0.0), Fragmented (0.33), Connected (0.67), Seamless (1.0)

### Task Dependencies

- Phase 2 tasks depend on Phase 1 outputs
- Phase 3 task depends on Phase 2 outputs
- All Phase 1 tasks are independent and can run in parallel
- All Phase 2 tasks are independent and can run in parallel (given Phase 1 completion)

### Edge Cases

- **Empty or minimal pitches**: Should produce low raw scores, normalizing to roughly uniform distribution
- **Single-element pitches**: Should heavily weight present element, minimal weight to absent ones
- **Contradictory pitches**: Flow scores should be low, reducing overall element scores
