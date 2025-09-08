# L04: Implementing Role-Based Prompting with Python

This lesson provides hands-on practice in iteratively developing role-based prompts to create believable personas. You'll learn to implement, test, and refine persona-driven AI systems using Python and the OpenAI API.

Below are **10 build-style exercises** that progress from basic implementation to advanced persona management systems.

---

## 1) Persona class architecture and basic implementation

**Goal:** Build a foundational class structure for managing AI personas.

**Build steps:**

1. Create `persona_system.py` with a `Persona` base class.
2. Include attributes: name, role, background, expertise_areas, communication_style, and constraints.
3. Implement methods: `generate_system_prompt()`, `process_query()`, and `validate_response()`.
4. Test with a simple "helpful teacher" persona.

**Acceptance criteria:**

- Class architecture supports extensible persona development.
- System prompts consistently reflect persona characteristics.
- Response validation ensures persona adherence.
- Basic persona produces appropriate, consistent responses.

---

## 2) Historical figure persona with authentic speech patterns

**Goal:** Implement a historically accurate persona with distinctive language patterns.

**Build steps:**

1. Create `historical_figure.py` extending the Persona class.
2. Choose Albert Einstein and research his documented speech patterns, favorite topics, and thinking style.
3. Implement language pattern matching: use of analogies, curiosity-driven questions, philosophical tangents.
4. Test with modern scientific questions to see authentic Einstein-style responses.

**Acceptance criteria:**

- Speech patterns match documented Einstein characteristics.
- Responses demonstrate appropriate scientific knowledge for his era.
- Personality quirks (curiosity, thought experiments) appear naturally.
- Modern questions receive Einstein-style analysis and analogies.

---

## 3) Professional consultant persona with industry expertise

**Goal:** Create a sophisticated business consultant persona with deep domain knowledge.

**Build steps:**

1. Create `business_consultant.py` with specialized consulting expertise.
2. Implement knowledge areas: strategy, operations, change management, and market analysis.
3. Include consulting methodologies: frameworks (SWOT, Porter's Five Forces), structured problem-solving, and client interaction patterns.
4. Test with realistic business scenarios requiring strategic recommendations.

**Acceptance criteria:**

- Consultant demonstrates appropriate business frameworks and methodologies.
- Responses follow structured problem-solving approaches.
- Communication style reflects professional consulting standards.
- Recommendations are actionable and strategically sound.

---

## 4) Multi-persona conversation orchestration

**Goal:** Implement systems for managing conversations involving multiple personas.

**Build steps:**

1. Create `persona_orchestrator.py` that manages multi-persona interactions.
2. Implement conversation routing, turn management, and context sharing between personas.
3. Create a scenario: Technology CEO, Marketing Director, and Engineering Lead discussing product strategy.
4. Ensure each persona maintains their unique perspective while contributing to unified discussion.

**Acceptance criteria:**

- Multiple personas participate meaningfully in shared conversations.
- Each persona maintains distinct voice and perspective.
- Turn management creates natural, flowing discussions.
- Context sharing enables informed, collaborative responses.

---

## 5) Persona adaptation based on user interaction style

**Goal:** Create personas that adapt their communication style based on user preferences and expertise.

**Build steps:**

1. Create `adaptive_persona.py` with user style detection and adaptation.
2. Implement detection of user characteristics: technical expertise, communication preference (formal/casual), detail level preference, and learning style.
3. Adapt persona responses accordingly while maintaining core identity.
4. Test with users showing different interaction patterns and preferences.

**Acceptance criteria:**

- Persona correctly identifies user interaction patterns.
- Adaptations maintain persona authenticity while improving user experience.
- Technical depth adjusts appropriately to user expertise level.
- Communication style adapts without losing persona characteristics.

---

## 6) Expertise validation and knowledge boundary management

**Goal:** Implement systems to ensure personas stay within their knowledge boundaries.

**Build steps:**

1. Create `knowledge_validator.py` with expertise boundary checking.
2. Define knowledge domains, competency levels, and temporal boundaries for each persona.
3. Implement uncertainty expression: "I'm not certain about...", "This is outside my expertise...", "Based on my knowledge from [era]...".
4. Test with questions that push beyond persona knowledge boundaries.

**Acceptance criteria:**

- Personas appropriately acknowledge knowledge limitations.
- Uncertainty expression maintains character authenticity.
- Temporal boundaries are respected (historical figures don't know future events).
- Graceful referral to more appropriate expertise when needed.

---

## 7) Cultural sensitivity and bias mitigation

**Goal:** Implement safeguards to ensure cultural personas are respectful and accurate.

**Build steps:**

1. Create `cultural_persona_safe.py` with bias detection and cultural sensitivity checks.
2. Implement validation for stereotypes, cultural accuracy, and respectful representation.
3. Create feedback loops for cultural authenticity review.
4. Test with diverse cultural personas and potentially sensitive topics.

**Acceptance criteria:**

- Cultural representations avoid harmful stereotypes.
- Authenticity validation ensures accurate cultural perspectives.
- Sensitive topics are handled with appropriate cultural awareness.
- Feedback systems enable continuous improvement of cultural representation.

---

## 8) Persona performance analytics and optimization

**Goal:** Create systems to measure and improve persona effectiveness.

**Build steps:**

1. Create `persona_analytics.py` with performance measurement capabilities.
2. Implement metrics: response relevance, character consistency, user satisfaction, and task completion rates.
3. Create optimization recommendations based on performance data.
4. Test with multiple personas over extended interaction periods.

**Acceptance criteria:**

- Analytics accurately measure persona effectiveness across multiple dimensions.
- Performance data identifies specific improvement opportunities.
- Optimization recommendations are actionable and maintain persona authenticity.
- Long-term tracking shows measurable improvement over time.

---

## 9) Persona memory and relationship building

**Goal:** Implement persistent memory systems that enable personas to build relationships with users.

**Build steps:**

1. Create `persona_memory.py` with user relationship tracking and memory management.
2. Implement memory categories: personal preferences, conversation history, shared experiences, and relationship development.
3. Create relationship evolution patterns appropriate to each persona type.
4. Test with extended interactions to demonstrate relationship building.

**Acceptance criteria:**

- Personas remember and reference previous interactions appropriately.
- Relationship development feels natural and authentic to persona character.
- Memory management balances detail retention with computational efficiency.
- Personal preferences influence persona behavior in subsequent interactions.

---

## 10) Advanced persona marketplace and selection system

**Goal:** Create a comprehensive system for managing, rating, and selecting optimal personas for specific tasks.

**Build steps:**

1. Create `persona_marketplace.py` with persona catalog, rating system, and intelligent selection.
2. Implement persona categories, capability tags, user reviews, and performance metrics.
3. Create matching algorithms that recommend optimal personas for specific tasks or user types.
4. Include persona creation tools for custom persona development.

**Acceptance criteria:**

- Marketplace enables easy discovery and comparison of available personas.
- Selection algorithms successfully match personas to task requirements.
- Rating system reflects actual persona performance and user satisfaction.
- Custom persona creation tools enable sophisticated persona development.

---

## Notes for Students

- **Implementation quality**: Focus on clean, maintainable code architecture.
- **Testing rigor**: Test personas extensively with edge cases and boundary conditions.
- **Ethical considerations**: Always consider the implications of persona design choices.
- **Performance optimization**: Monitor token usage and response times for persona systems.

## Common Issues and Solutions

- **Memory leaks**: Implement proper context management for long conversations.
- **Persona drift**: Use validation systems to maintain character consistency.
- **Response latency**: Optimize persona prompt construction for speed.
- **Token management**: Implement efficient context summarization for complex personas.

## Extension Challenges

- Build a persona versioning system with rollback capabilities.
- Create automated persona testing suites with behavioral validation.
- Implement persona learning from interaction outcomes.
- Develop cross-platform persona portability standards.
