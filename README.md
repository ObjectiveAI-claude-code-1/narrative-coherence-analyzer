# Narrative Coherence Analyzer

A vector function that analyzes the narrative structure of a startup pitch, producing a 7-element probability distribution over the canonical narrative elements.

## Overview

This function evaluates startup pitches across seven canonical narrative elements that comprise a compelling startup story:

1. **Problem** - What pain exists and why it matters
2. **Solution** - How the idea addresses the problem
3. **Market** - Who has this pain and how many
4. **Business Model** - How value is captured and monetized
5. **Traction** - Evidence that it works
6. **Team** - Why this team can execute
7. **Vision** - Where this goes long-term

## Output

The output is a 7-element probability distribution that sums to 1.0, representing the relative strength of each narrative element in the pitch. Higher scores indicate stronger presence and quality of that element.

For example, a pitch that only mentions the problem and solution might produce:
```json
[0.35, 0.30, 0.07, 0.07, 0.07, 0.07, 0.07]
```

While a comprehensive pitch with all elements might produce:
```json
[0.15, 0.14, 0.15, 0.14, 0.14, 0.14, 0.14]
```

## Input

The function accepts multimodal inputs:

- **Text**: Pitch scripts, executive summaries, elevator pitches
- **Images**: Pitch deck slides, infographics, one-pagers
- **Audio**: Recorded elevator pitches, podcast clips
- **Video**: Demo day recordings, pitch videos, product demos
- **Arrays**: Composite pitches with multiple elements (e.g., slides + founder video)

### Example Inputs

**Text pitch:**
```json
{
  "idea": "We're solving the $50B annual problem of restaurant food waste. Our AI-powered inventory system reduces spoilage by 40%. We have 50 restaurant customers, $200K ARR, growing 20% MoM. Founded by ex-Google engineers with 10 years in food tech. Vision: eliminate food waste globally."
}
```

**Image pitch (pitch deck slide):**
```json
{
  "idea": {"type": "image_url", "image_url": {"url": "https://example.com/pitch-deck-slide.png"}}
}
```

**Composite pitch (multiple slides + context):**
```json
{
  "idea": [
    {"type": "image_url", "image_url": {"url": "https://example.com/slide1.png"}},
    {"type": "image_url", "image_url": {"url": "https://example.com/slide2.png"}},
    "Additional context: We're targeting the B2B SaaS market with a freemium model."
  ]
}
```

## Evaluation Criteria

Each narrative element is evaluated on multiple dimensions:

### Problem
- Presence, specificity, magnitude, urgency, credibility, emotional resonance

### Solution
- Presence, clarity, problem-solution fit, defensibility, elegance, feasibility

### Market
- Presence, credibility, specificity, accessibility, dynamics, segmentation

### Business Model
- Presence, clarity, alignment, scalability, defensibility, credibility

### Traction
- Presence, relevance, magnitude, trajectory, quality, recency

### Team
- Presence, relevant experience, track record, founder-market fit, completeness, commitment

### Vision
- Presence, ambition, plausibility, specificity, differentiation, emotional resonance

## Use Cases

- **Investor Screening**: Quickly identify which narrative elements need work
- **Pitch Coaching**: Provide structured feedback on pitch completeness
- **Founder Self-Assessment**: Understand gaps in your startup story
- **Accelerator Applications**: Evaluate narrative quality at scale
- **Pitch Deck Analysis**: Assess deck coverage of key elements
