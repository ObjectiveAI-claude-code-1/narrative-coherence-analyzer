# Narrative Coherence Analyzer

A vector function with fixed output length of 7 that analyzes the narrative structure of a startup pitch.

## Input Schema

The input is an object with a single required field called `idea`.

The `idea` field can be:
- A string (text pitch)
- An image (image pitch)
- An audio clip (audio pitch)
- A video (video pitch)
- A composite array containing any mix of the above

Use this exact input schema:
```json
{
  "type": "object",
  "properties": {
    "idea": {
      "anyOf": [
        {"type": "string"},
        {"type": "image"},
        {"type": "audio"},
        {"type": "video"},
        {
          "type": "array",
          "minItems": 1,
          "items": {
            "anyOf": [
              {"type": "string"},
              {"type": "image"},
              {"type": "audio"},
              {"type": "video"}
            ]
          }
        }
      ]
    }
  },
  "required": ["idea"]
}
```

## Output

A vector of 7 scores (one per narrative element) summing to 1.

## Output Length

Always 7 (fixed) - one score for each canonical narrative element:
1. Problem
2. Solution
3. Market
4. Business Model
5. Traction/Proof
6. Team/Execution
7. Vision

## Evaluation Criteria

For each of the 7 elements:
1. **Presence**: Explicitly addressed, implied, or absent?
2. **Quality**: How compelling if present?
3. **Narrative Flow**: Elements connect logically?