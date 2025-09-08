# L08: Applying Prompt Instruction Refinement with Python

This lesson provides hands-on practice iteratively refining a prompt to transform a generic recipe analyzer into a precise dietary consultant that produces structured JSON output. You'll learn systematic refinement techniques by modifying components like Role, Task, Context, Examples, and Output Format.

Below are **10 build-style exercises** that progress from basic prompt iteration to advanced refinement strategies. Each exercise builds upon the previous to create a sophisticated dietary consultation system.

---

## 1) Base recipe analyzer implementation

**Goal:** Create a basic recipe analyzer that provides simple nutritional feedback.

**Build steps:**
1. Create `recipe_analyzer.py` with a basic prompt that analyzes recipe healthiness.
2. Implement a function that takes recipe text and returns general health assessment.
3. Test with a simple recipe (e.g., chocolate chip cookies).
4. Document the initial prompt and its limitations.

**Acceptance criteria:**
- Script accepts recipe text input and returns basic health analysis.
- Response identifies obvious healthy/unhealthy ingredients.
- Code is modular with separate functions for prompting and parsing.
- Initial prompt baseline is documented for comparison.

---

## 2) Adding role-based refinement

**Goal:** Refine the prompt by adding a specific expert role persona.

**Build steps:**
1. Modify the prompt to include a "Certified Nutritionist" role.
2. Compare responses between generic and role-based prompts using the same recipe.
3. Document differences in tone, authority, and technical language.
4. Test with 3 different recipes to validate consistency.

**Acceptance criteria:**
- Role-based prompt produces more authoritative responses.
- Technical nutritional terminology appears in responses.
- Tone becomes more professional and expert-like.
- Consistent expert voice across different recipe inputs.

---

## 3) Task specification refinement

**Goal:** Make the task more specific with clear dietary consultation objectives.

**Build steps:**
1. Refine the task from "analyze recipe" to "provide dietary consultation for specific health goals".
2. Add specific consultation areas: macronutrient balance, allergen identification, meal timing.
3. Test with recipes for different dietary needs (weight loss, muscle gain, diabetic-friendly).
4. Compare task-refined responses to previous versions.

**Acceptance criteria:**
- Responses address specific dietary consultation areas.
- Different health goals produce appropriately tailored advice.
- Task clarity improves response relevance and actionability.
- Consultation covers macronutrients, allergens, and timing considerations.

---

## 4) Context enhancement with dietary frameworks

**Goal:** Add relevant nutritional context and dietary framework knowledge.

**Build steps:**
1. Enhance the prompt with context about common dietary frameworks (Mediterranean, DASH, ketogenic).
2. Include context about macronutrient ratios and daily value percentages.
3. Add context about common allergens and dietary restrictions.
4. Test how added context improves recipe analysis depth.

**Acceptance criteria:**
- Responses reference appropriate dietary frameworks.
- Macronutrient analysis includes specific ratios and DV percentages.
- Allergen identification is comprehensive and accurate.
- Context significantly improves analysis depth and relevance.

---

## 5) Example-driven refinement with few-shot learning

**Goal:** Use concrete examples to train the model's response style and format.

**Build steps:**
1. Create 2-3 high-quality example recipe analyses in your desired format.
2. Include examples in the prompt as few-shot demonstrations.
3. Ensure examples cover different recipe types (main dish, dessert, snack).
4. Test how examples influence response quality and consistency.

**Acceptance criteria:**
- Examples demonstrate desired analysis depth and structure.
- Model follows example format for new recipe inputs.
- Response quality becomes more consistent across different recipe types.
- Examples effectively guide the model's analytical approach.

---

## 6) Structured JSON output formatting

**Goal:** Transform text responses into structured JSON for programmatic use.

**Build steps:**
1. Define a JSON schema for dietary consultation responses.
2. Include fields: healthiness_score, macronutrients, allergens, recommendations.
3. Modify prompt to explicitly request JSON format with schema.
4. Implement JSON validation and error handling.

**Acceptance criteria:**
- All responses return valid JSON matching the defined schema.
- JSON includes quantitative scores and structured data.
- Error handling gracefully manages malformed JSON responses.
- Schema supports both human readability and programmatic processing.

**Notes:**
```json
{
  "healthiness_score": 7,
  "macronutrients": {
    "protein_percent": 15,
    "carbs_percent": 45,
    "fat_percent": 40
  },
  "allergens": ["gluten", "dairy"],
  "recommendations": ["Reduce sodium", "Add vegetables"]
}
```

---

## 7) Iterative refinement with feedback loops

**Goal:** Implement a system for testing and refining prompts based on output quality.

**Build steps:**
1. Create a test suite with 10 diverse recipes and expected analysis criteria.
2. Implement scoring system for response quality (accuracy, completeness, usefulness).
3. Create iterative refinement function that adjusts prompt based on scores.
4. Run multiple refinement cycles and track improvement metrics.

**Acceptance criteria:**
- Test suite covers diverse recipe types and dietary scenarios.
- Scoring system provides quantitative feedback on response quality.
- Iterative process shows measurable improvement in scores.
- Final prompt significantly outperforms initial baseline.

---

## 8) Advanced refinement with chain-of-thought reasoning

**Goal:** Enhance the prompt to include explicit reasoning steps for dietary analysis.

**Build steps:**
1. Modify prompt to request step-by-step nutritional reasoning.
2. Include steps: ingredient analysis, macronutrient calculation, health impact assessment.
3. Test how explicit reasoning improves analysis accuracy and transparency.
4. Compare reasoning-enhanced responses to previous versions.

**Acceptance criteria:**
- Responses include clear step-by-step reasoning process.
- Each reasoning step is logical and nutritionally sound.
- Reasoning transparency allows verification of conclusions.
- Analysis accuracy improves with explicit reasoning framework.

---

## 9) Personalization refinement with user profiles

**Goal:** Adapt the dietary consultant to specific user health profiles and goals.

**Build steps:**
1. Define user profile schema (age, activity level, health conditions, goals).
2. Modify prompt to incorporate user profile data in analysis.
3. Create profiles for different user types (athlete, diabetic, weight loss, etc.).
4. Test how personalization affects recipe recommendations.

**Acceptance criteria:**
- User profiles significantly influence dietary recommendations.
- Same recipe produces different advice for different user profiles.
- Recommendations are appropriate for specified health conditions and goals.
- Personalization maintains nutritional accuracy while adding relevance.

---

## 10) Production-ready refinement with edge case handling

**Goal:** Create a robust dietary consultant ready for real-world use with comprehensive error handling.

**Build steps:**
1. Add edge case handling for incomplete recipes, unusual ingredients, invalid inputs.
2. Implement fallback strategies for ambiguous or missing nutritional information.
3. Add confidence scoring for recommendations and uncertainty acknowledgment.
4. Create comprehensive test suite covering normal and edge cases.

**Acceptance criteria:**
- System gracefully handles incomplete or unusual recipe inputs.
- Confidence scores accurately reflect recommendation reliability.
- Edge cases produce helpful responses rather than failures.
- Production deployment readiness with robust error handling.

**Notes:**
- Consider implementing retry logic for API failures.
- Add logging for monitoring prompt performance in production.
- Include user feedback collection for continuous refinement.

---

## Chapter Summary

This lesson demonstrated systematic prompt refinement through:
- **Role refinement** for expert authority and technical accuracy
- **Task specification** for clear objectives and focused outcomes  
- **Context enhancement** with domain knowledge and frameworks
- **Example-driven learning** for consistent quality and format
- **Structured output** for programmatic integration and processing
- **Iterative improvement** based on quantitative feedback
- **Chain-of-thought reasoning** for transparency and accuracy
- **Personalization** for user-specific relevance and value
- **Production readiness** with robust edge case handling

The refined dietary consultant demonstrates how systematic prompt engineering transforms basic queries into sophisticated, reliable AI tools ready for real-world deployment.
