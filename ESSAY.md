# Narrative Coherence Analyzer: Philosophy and Design

## Introduction

The Narrative Coherence Analyzer is a vector function that deconstructs startup pitches into their canonical narrative elements, returning a probability distribution across seven fundamental components. Unlike scalar scorers that collapse complex phenomena into single numbers, this function produces a *profile*—a seven-dimensional fingerprint that reveals how a pitch allocates its narrative energy across the essential building blocks of entrepreneurial storytelling.

This is not merely a classifier. It is a diagnostic instrument for understanding how founders conceptualize and communicate their ventures. The output—a vector of seven scores summing to 1—represents the *relative narrative weight* devoted to each element, enabling comparisons across pitches of vastly different lengths, formats, and styles.

## The Seven Canonical Narrative Elements

Every compelling startup pitch, regardless of industry, stage, or medium, must address seven fundamental questions. These are not arbitrary categories but the irreducible elements that experienced investors listen for, consciously or unconsciously, when evaluating an opportunity.

### 1. Problem

*What pain exists in the world that demands a solution?*

The Problem element establishes the premise for the entire narrative. It answers why the venture should exist at all. Great problem articulations share several qualities:

**Specificity**: Vague problems ("communication is hard") fail to convince. Compelling problems are concrete, situated, and vivid. They paint a picture of real people experiencing real frustration.

**Magnitude**: The problem must be significant enough to warrant attention. This doesn't always mean massive scale—it can mean intense pain for a smaller group. But triviality is fatal.

**Urgency**: Why now? The best problems have a temporal dimension—they're getting worse, a new enabling technology has emerged, or regulatory changes have created an opening.

**Personal Connection**: The most compelling problems are ones the founders have experienced themselves. First-hand pain signals authenticity and deep understanding.

**Validation**: Is there evidence that others share this problem? Customer interviews, market research, and quantitative data transform personal anecdote into validated opportunity.

When evaluating Problem presence and quality, the function must distinguish between:
- Explicit, well-articulated problems with evidence and specificity
- Implicit problems that are alluded to but never fully developed
- Problems that are assumed rather than demonstrated
- Complete absence of problem framing (jumping straight to solution)

### 2. Solution

*How does this venture address the identified problem?*

The Solution element describes what is being built and how it creates value. It bridges the gap between pain and relief, between current state and desired future.

**Clarity**: Can the solution be explained simply? Complexity is not a virtue. The best solutions have an elegant core that can be grasped immediately.

**Differentiation**: How is this solution different from existing alternatives? What is the unique insight, approach, or capability that distinguishes it?

**Feasibility**: Is this technically and operationally achievable? Wild speculation without grounding in reality undermines credibility.

**Problem-Solution Fit**: Does the solution actually address the stated problem? Surprisingly often, pitches describe problems and solutions that don't align.

**Defensibility**: What prevents others from copying this solution? This connects to moats—network effects, proprietary technology, unique data, regulatory advantages.

The function must evaluate whether the solution is:
- Fully specified with clear mechanics and differentiation
- Partially described but missing key details
- Mentioned without explanation
- Entirely absent (problem without solution)

### 3. Market

*How large is the opportunity?*

The Market element quantifies the potential. It answers how big this could become if everything goes right.

**TAM/SAM/SOM Framework**: Does the pitch demonstrate understanding of Total Addressable Market, Serviceable Addressable Market, and Serviceable Obtainable Market? This shows analytical rigor.

**Bottom-Up vs Top-Down**: Bottom-up market sizing (starting from unit economics and realistic penetration) is more credible than top-down ("if we get 1% of a trillion-dollar market").

**Growth Dynamics**: Is the market expanding, stable, or contracting? What forces are driving change?

**Segmentation**: Does the pitch identify specific initial segments to target? Markets are not monolithic; sophisticated founders understand where to start.

**Competitive Landscape**: What alternatives exist? How does market share currently distribute?

Market elements may appear as:
- Rigorous, data-driven analysis with clear methodology
- High-level claims without supporting evidence
- Vague assertions of "huge opportunity"
- Complete absence of market discussion

### 4. Business Model

*How does this venture make money?*

The Business Model element explains the economic engine. It transforms a product idea into a sustainable enterprise.

**Revenue Mechanics**: What is the pricing model? Subscription, transactional, freemium, advertising, licensing? How does money flow?

**Unit Economics**: What is the customer acquisition cost (CAC), lifetime value (LTV), gross margin, and payback period? Even early-stage pitches should show understanding of these concepts.

**Scalability**: Does the business model allow for efficient scaling? Are there inherent limits? Does margin expand or compress with growth?

**Network Effects and Lock-In**: Does the model create increasing returns? Are there switching costs that protect revenue once acquired?

**Path to Profitability**: When and how will the venture become self-sustaining? What milestones mark the journey?

Business model presence ranges from:
- Detailed economic model with validated assumptions
- Clear revenue mechanism without unit economics
- Vague monetization ideas ("we'll figure it out later")
- No mention of how the venture will sustain itself

### 5. Traction/Proof

*What evidence exists that this is working?*

The Traction element provides validation. It transforms hypothesis into demonstrated reality.

**Quantitative Metrics**: Revenue, users, growth rate, retention, engagement. Numbers with context are powerful.

**Qualitative Validation**: Customer testimonials, case studies, design partners, letters of intent. Social proof from credible sources.

**Milestones Achieved**: Product launches, partnerships secured, regulatory approvals, key hires made.

**Velocity**: Not just where things are, but how fast they're moving. Trajectory often matters more than absolute numbers.

**Quality of Traction**: Not all metrics are equal. Vanity metrics (downloads, signups) matter less than engagement and revenue.

Traction elements vary from:
- Compelling metrics with clear evidence of product-market fit
- Early signs of validation without conclusive proof
- Plans and hypotheses without execution
- No evidence of market engagement

### 6. Team/Execution

*Why is this team the one to win?*

The Team element establishes credibility. It answers why these specific people will succeed where others have failed.

**Relevant Experience**: Have team members worked in this domain? Built companies before? Operated at scale?

**Complementary Skills**: Does the team cover product, technology, sales, operations? Are there dangerous gaps?

**Track Record**: What have they accomplished? What obstacles have they overcome?

**Unfair Advantages**: What gives this team asymmetric access—relationships, knowledge, reputation?

**Commitment**: Is this a side project or an all-in effort? What have founders sacrificed to pursue this?

**Culture and Values**: How does the team work together? What principles guide decision-making?

Team presence manifests as:
- Detailed backgrounds establishing clear relevance and capability
- Brief mentions without depth
- Assumption that team credibility is self-evident
- Complete absence of team discussion

### 7. Vision

*What future does this venture create?*

The Vision element provides meaning. It answers why this matters beyond financial returns.

**Ambition**: How big does this dream? Vision should inspire and stretch imagination.

**Coherence**: Does the vision connect logically to current activities? Grand visions disconnected from present reality feel hollow.

**Impact**: How does the world change if this succeeds? What problems are solved at scale?

**Authenticity**: Does the vision feel genuine to these founders? Or is it grafted on to seem more impressive?

**Milestone Connection**: How do near-term activities ladder to long-term vision? Is there a credible path?

Vision ranges from:
- Compelling, authentic articulation of transformative change
- Reasonable ambition without inspirational depth
- Grandiose claims without grounding
- Purely tactical focus without larger purpose

## The Nature of the Output

The function returns a vector of seven scores summing to 1. This design choice has profound implications:

**Relative, Not Absolute**: The scores represent how narrative emphasis is *distributed*, not how "good" each element is. A pitch might score 0.3 on Problem not because the problem is well-articulated, but because 30% of the narrative weight is devoted to problem discussion.

**Zero-Sum Dynamics**: More emphasis on one element necessarily means less on others. This reflects the reality of attention and time constraints in pitching.

**Profile Shape Matters**: Two pitches with identical average element quality could have very different profiles. A technical founder might over-index on Solution; a repeat entrepreneur might emphasize Team.

**No "Correct" Distribution**: Context determines optimal balance. A pre-product pitch should emphasize Problem, Solution, and Team. A Series B pitch should show more Traction and Business Model.

## Evaluation Methodology

For each of the seven elements, the function must assess three interrelated qualities:

### Presence

Is the element explicitly addressed, merely implied, or entirely absent?

**Explicit**: The pitch directly discusses this element with clear, identifiable content. "The problem we're solving is..." or "Our business model works as follows..."

**Implied**: The element can be inferred but is not directly stated. A Solution discussion might imply a Problem without articulating it. Market size might be implicit in customer numbers.

**Absent**: The element receives no attention, direct or indirect.

### Quality

If present, how compelling is the treatment?

**Compelling**: The element is handled with clarity, evidence, and persuasive power. It would satisfy a skeptical investor.

**Adequate**: The element is addressed but could be stronger. It passes a basic threshold without excelling.

**Weak**: The element is present but unconvincing. It raises more questions than it answers.

### Narrative Flow

How do elements connect to each other?

**Seamless**: Elements build on each other logically. Problem leads to Solution; Solution enables Business Model; Traction validates Solution.

**Functional**: Elements are present and reasonably connected, but transitions could be smoother.

**Disjointed**: Elements exist in isolation without clear relationship. The pitch feels like a checklist rather than a story.

## Input Handling: Multimodal Considerations

The function accepts diverse input formats, reflecting the reality that startup pitches come in many forms:

**Text Pitches**: Written decks, email pitches, application essays. These require parsing of natural language, identification of rhetorical structures, and extraction of claims and evidence.

**Image Pitches**: Slide decks, infographics, visual summaries. These require visual understanding—reading text from slides, interpreting charts and diagrams, understanding visual hierarchy.

**Audio Pitches**: Podcast appearances, phone pitches, voice memos. These require transcription and analysis of spoken content, including tone and emphasis.

**Video Pitches**: Demo days, pitch competitions, product walkthroughs. These combine visual and audio understanding, plus potential analysis of presentation style.

**Composite Pitches**: Combinations of the above—a deck with voiceover, a product demo with slides, a written summary with embedded video.

Each format presents unique challenges. Video may convey Team credibility through presence and confidence in ways text cannot. Written pitches allow more precise language analysis. Images can convey complex information density.

The function must normalize across formats, recognizing that a confident video presenter and a well-written deck are both conveying Team credibility, even though the surface manifestations differ entirely.

## Use Cases

### Investor Screening

Venture investors receive hundreds or thousands of pitches. The Narrative Coherence Analyzer provides rapid structural assessment:

- Does this pitch cover the basics?
- What's missing that I should probe on?
- How does the emphasis pattern compare to successful investments?

### Founder Coaching

Founders preparing for fundraising can use the analyzer to identify gaps:

- Am I spending too much time on Solution and not enough on Problem?
- Is my Traction section actually demonstrating traction or just describing plans?
- Have I established why our Team is uniquely positioned?

### Pitch Optimization

By comparing profiles across iterations, founders can track whether revisions are achieving intended effects:

- Did adding customer testimonials increase the Traction score?
- Is the Vision section now appropriately prominent?
- Has the Business Model become clearer?

### Competitive Analysis

Comparing profiles across pitches in a batch (Y Combinator applications, accelerator cohorts) reveals patterns:

- What narrative strategies are competitors using?
- Which elements are crowded? Which are differentiation opportunities?
- How does our profile compare to funded companies in our space?

### Educational Feedback

For pitch competitions, accelerators, and entrepreneurship courses, the analyzer provides structured feedback:

- Here's your narrative profile
- Here's how it compares to strong pitches
- Here's what's missing and why it matters

## The Philosophy of Narrative Structure

This function embeds a specific theory of entrepreneurial communication: that successful startup pitches are *stories* with recurring structural elements, and that understanding this structure reveals both the quality of the pitch and the maturity of the venture.

The seven elements are not arbitrary. They emerge from decades of investment practice, codified in frameworks like the "Pitch Deck Template" and the "Sequoia Pitch Format." They reflect what experienced investors have learned to listen for, often unconsciously.

But the function goes beyond checklist compliance. By producing a continuous distribution rather than binary present/absent judgments, it captures nuance:

- The pitch that over-explains the Problem at the expense of Solution
- The pitch with impressive Traction but no coherent Business Model
- The pitch with grand Vision but weak Team credibility

These patterns tell stories themselves—about founder priorities, venture maturity, and strategic choices.

## Challenges and Considerations

### Cultural and Contextual Variation

Pitch norms vary across geographies, industries, and stages. A deep tech pitch to DARPA differs from a consumer app pitch to a seed fund. The function must be robust across these variations while still producing comparable outputs.

### Subjective Boundaries

Where does Problem end and Solution begin? When does Team discussion become Vision? The seven elements are conceptually distinct but practically intertwined. The function must make judgment calls at boundaries.

### Quality vs. Quantity

A brief, brilliant Problem statement might deserve more weight than a lengthy, weak one. The function must balance time/attention spent against persuasive impact.

### Intentional Omissions

Sometimes elements are absent by design. A stealth-mode pitch might omit Solution details. A pre-revenue venture has no Traction by definition. The function should analyze what's present without assuming absence is always a flaw.

## Conclusion

The Narrative Coherence Analyzer transforms the intuitive, holistic assessment that experienced investors perform instantly into an explicit, structured, reproducible evaluation. It does not replace human judgment—it augments it.

By producing a seven-dimensional profile rather than a single score, it preserves the complexity of startup narrative while enabling comparison, tracking, and optimization. It answers not "is this pitch good?" but "how is this pitch constructed, and what does that construction reveal?"

This is the foundation upon which the function will be built: a deep understanding of what makes startup narratives work, translated into evaluative criteria that respect both the art and science of entrepreneurial storytelling.
