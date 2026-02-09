# Narrative Coherence Analyzer

A vector function with fixed output length of 7 that analyzes the narrative structure of a startup pitch.

## Input Schema

The input is an object with an `idea` field. The `idea` field uses anyOf to accept:
- A string (text pitch)
- An image (type: image)
- An audio (type: audio)
- A video (type: video)
- An array of strings and/or multimodal elements (composite pitch)

Example input schema structure:
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
        {"type": "array", "items": {"anyOf": [{"type": "string"}, {"type": "image"}, {"type": "audio"}, {"type": "video"}]}}
      ]
    }
  },
  "required": ["idea"]
}
```

## Output

A vector of 7 scores (one per narrative element) summing to 1.

## Output Length

Always 7 - one score for each canonical narrative element:
1. Problem
2. Solution
3. Market
4. Business Model
5. Traction/Proof
6. Team/Execution
7. Vision

## Evaluation Criteria

For each of the 7 elements:
1. **Presence**: Is it explicitly addressed, implied, or absent?
2. **Quality**: How compelling is it if present?
3. **Narrative Flow**: Do elements connect logically?