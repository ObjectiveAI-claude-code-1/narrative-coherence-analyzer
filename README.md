# Narrative Coherence Analyzer

A vector function that analyzes the narrative structure of startup pitches, producing a probability distribution across seven canonical narrative elements.

## Overview

This function evaluates startup pitches against seven foundational narrative elements that answer the essential questions stakeholders ask:

1. **Problem** - "Why should anyone care?"
2. **Solution** - "What is the answer?"
3. **Market** - "How big is the opportunity?"
4. **Business Model** - "How will value be captured?"
5. **Traction** - "Is this working?"
6. **Team** - "Who will make this happen?"
7. **Vision** - "Where is this going?"

## Input

The function accepts pitches in multiple modalities:

- **Text**: Written pitch decks, executive summaries, or pitch scripts
- **Image**: Visual pitch materials like slides or infographics
- **Audio**: Recorded verbal pitches or demo day recordings
- **Video**: Full audiovisual presentations
- **Composite**: Arrays combining any of the above

## Output

Returns a vector of 7 scores (one per element) that sum to 1.0, representing the relative narrative strength distribution across elements.

Example output: `[0.15, 0.18, 0.12, 0.10, 0.20, 0.13, 0.12]`

A well-balanced pitch produces roughly equal scores. An unbalanced pitch shows higher weights on emphasized elements and lower weights on neglected ones.

## Evaluation Criteria

For each element, the function assesses:

1. **Presence**: Is the element explicitly addressed, implied, or absent?
2. **Quality**: How compelling is the articulation if present?
3. **Narrative Flow**: Does the element connect logically to the overall story?

## Use Cases

- **Investor Screening**: Quickly identify structural strengths and weaknesses in pitches
- **Founder Coaching**: Identify narrative gaps before high-stakes presentations
- **Accelerator Assessment**: Benchmark cohort pitches and identify common weaknesses
- **Competitive Analysis**: Understand competitor narrative positioning
- **Longitudinal Tracking**: Measure narrative improvement across fundraising rounds
