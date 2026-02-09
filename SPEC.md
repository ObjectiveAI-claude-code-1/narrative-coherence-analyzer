# Narrative Coherence Analyzer

A vector function with dynamic output length that analyzes the narrative structure of a startup pitch, identifying which elements of the canonical startup story are present and how strong each is.

## Input Schema

The input is an object with an `idea` field containing a single startup idea. The idea can be:
- A string (text pitch)
- An image, audio, or video (multimodal pitch)
- An array of the above (composite pitch)

```json
{
  "idea": "We're solving the $50B problem of food waste. Our AI-powered inventory system reduces spoilage by 40%. We have 50 restaurant customers, $200K ARR, growing 20% MoM. Founded by ex-Google engineers with 10 years in food tech. Vision: eliminate food waste globally."
}
```

## Output

A vector of scores over the 7 canonical narrative elements, representing the strength of each element. Scores sum to 1.0.

## Output Length

Always 7 (fixed) - one score for each narrative element. Elements that are absent or weak receive low/zero scores.

The 7 elements in order:
1. Problem - What pain exists
2. Solution - How the idea addresses it
3. Market - Who has this pain and how many
4. Business Model - How value is captured
5. Traction/Proof - Evidence that it works
6. Team/Execution - Why this team can do it
7. Vision - Where this goes long-term

## Evaluation Criteria

For each of the 7 narrative elements:

1. **Presence**: Is the element explicitly addressed, implied, or absent?

2. **Quality**: How compelling is the element if present? Is the problem clearly articulated? Is the solution believable? Is market data credible?

3. **Narrative Flow**: Do elements connect logically? Does the story build to a compelling conclusion?

Elements that are absent or very weak should receive near-zero scores. Strong elements should receive higher scores. The distribution reveals which parts of the startup story are strongest.