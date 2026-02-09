# Narrative Coherence Analyzer

A vector function that analyzes the narrative structure of startup pitches, returning a 7-dimensional probability distribution across canonical narrative elements.

## Overview

This function examines startup pitches (in text, image, audio, video, or composite formats) and evaluates how strongly each of seven fundamental narrative elements is present. The output is a probability distribution where each value represents the relative strength of that narrative element within the pitch.

## Narrative Elements

The function analyzes the following seven canonical elements:

| Index | Element | Description |
|-------|---------|-------------|
| 0 | **Problem** | Clear articulation of pain point or market gap |
| 1 | **Solution** | Proposed offering addressing the identified problem |
| 2 | **Market** | Target audience, size, and growth opportunity |
| 3 | **Business Model** | Revenue generation and value capture strategy |
| 4 | **Traction/Proof** | Evidence of progress, validation, or market fit |
| 5 | **Team/Execution** | Founder credibility and execution capability |
| 6 | **Vision** | Long-term ambition and transformative potential |

## Input

The function accepts a single `idea` field that can be:

- **String**: Plain text pitch description
- **Image**: Visual pitch deck slides or diagrams
- **Audio**: Recorded pitch audio
- **Video**: Video pitch presentation
- **Array**: Composite of multiple formats (minimum 1 element)

### Input Schema

```json
{
  "type": "object",
  "properties": {
    "idea": {
      "anyOf": [
        { "type": "string" },
        { "type": "object", "properties": { "type": { "const": "image_url" } } },
        { "type": "object", "properties": { "type": { "const": "input_audio" } } },
        { "type": "object", "properties": { "type": { "const": "video_url" } } },
        { "type": "array", "minItems": 1 }
      ]
    }
  },
  "required": ["idea"]
}
```

## Output

A 7-element vector of floating-point values that sum to approximately 1.0, representing a probability distribution across the narrative elements.

### Example Output

```json
[0.18, 0.22, 0.15, 0.12, 0.08, 0.10, 0.15]
```

This output indicates:
- Solution (22%) is the dominant narrative element
- Problem (18%) is strongly present
- Market and Vision (15% each) are moderate
- Business Model (12%) and Team (10%) are lighter
- Traction (8%) is the least emphasized

## Interpretation

- **Balanced Distribution**: A pitch with roughly equal values (~14% each) covers all elements evenly
- **Dominant Element**: A high value (>25%) indicates the pitch emphasizes that element heavily
- **Absent Element**: A low value (<5%) suggests that narrative component is missing or weak

## Execution Strategies

The function supports both default and `swiss_system` execution strategies:

- **Default**: Evaluates all 7 elements in a single pass
- **Swiss System**: Splits evaluation into parallel sub-tasks for optimized execution

## Use Cases

- **Pitch Deck Analysis**: Identify narrative gaps in investor presentations
- **Founder Coaching**: Guide entrepreneurs on strengthening weak narrative areas
- **Competitive Analysis**: Compare narrative emphasis across different startups
- **Due Diligence**: Quickly assess pitch completeness and balance
