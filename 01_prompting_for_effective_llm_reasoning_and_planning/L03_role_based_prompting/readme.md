# L03: Role-Based Prompting

This lesson explains the theory of using roles or personas to control the tone, style, and expertise of an LLM's output. You'll learn to create believable personas that consistently shape AI behavior and responses.

Below are **10 build-style exercises** that progress from basic role assignment to sophisticated persona development and management.

---

## 1) Basic role assignment and comparison

**Goal:** Understand how simple role instructions affect response style and content.

**Build steps:**

1. Create `basic_roles.py` that tests the same query with different role assignments.
2. Test roles: "helpful assistant", "expert consultant", "creative writer", "analytical researcher".
3. Use query: "Explain artificial intelligence" with each role.
4. Compare response length, tone, technical depth, and structure.

**Acceptance criteria:**

- Each role produces distinctly different response styles.
- Expert roles show appropriate technical depth.
- Creative roles demonstrate more engaging, accessible language.
- Analytical roles focus on structure and logical organization.

---

## 2) Professional persona development

**Goal:** Create detailed professional personas with specific expertise and communication styles.

**Build steps:**

1. Create `professional_personas.py` with detailed persona definitions.
2. Develop personas: Senior Software Architect, Marketing Director, Financial Analyst, UX Designer.
3. Include for each: background, expertise areas, communication style, typical concerns, and decision-making approach.
4. Test with cross-functional business scenarios requiring different expertise.

**Acceptance criteria:**

- Personas demonstrate appropriate professional knowledge and terminology.
- Communication styles reflect realistic professional behavior.
- Responses address concerns typical of each role.
- Decision-making approaches align with professional responsibilities.

---

## 3) Historical figure embodiment

**Goal:** Create personas based on historical figures with distinctive thinking patterns and knowledge.

**Build steps:**

1. Create `historical_personas.py` implementing famous historical figures.
2. Choose figures: Leonardo da Vinci (Renaissance polymath), Marie Curie (pioneering scientist), Winston Churchill (wartime leader), Maya Angelou (poet and activist).
3. Research each figure's documented thinking patterns, speech style, and key beliefs.
4. Test with modern problems to see how historical perspectives apply.

**Acceptance criteria:**

- Personas reflect documented historical speech patterns and beliefs.
- Responses demonstrate knowledge appropriate to each figure's era and expertise.
- Modern applications show creativity while maintaining historical authenticity.
- Each figure's unique perspective clearly differentiates their responses.

---

## 4) Domain expert specialization

**Goal:** Create highly specialized expert personas for technical and professional domains.

**Build steps:**

1. Create `domain_experts.py` with deep specialization in specific fields.
2. Develop experts: Cybersecurity Specialist, Climate Scientist, Blockchain Developer, Bioethicist.
3. Include recent developments, industry terminology, current challenges, and methodological approaches for each domain.
4. Test with complex, domain-specific problems requiring specialized knowledge.

**Acceptance criteria:**

- Experts demonstrate current, accurate domain knowledge.
- Technical terminology is used correctly and appropriately.
- Responses reflect real industry challenges and considerations.
- Methodological approaches align with professional standards.

---

## 5) Cultural perspective integration

**Goal:** Develop personas that reflect different cultural backgrounds and worldviews.

**Build steps:**

1. Create `cultural_personas.py` representing diverse cultural perspectives.
2. Develop personas from: East Asian (Confucian values), Scandinavian (social democratic), Indigenous (holistic worldview), Mediterranean (relationship-focused).
3. Research cultural values, communication patterns, and problem-solving approaches.
4. Test with ethical dilemmas and social problems to show different cultural approaches.

**Acceptance criteria:**

- Cultural perspectives are respectfully and accurately represented.
- Problem-solving approaches reflect documented cultural values.
- Communication styles align with cultural norms.
- Responses avoid stereotypes while showing genuine cultural insight.

---

## 6) Emotional intelligence and personality traits

**Goal:** Implement personas with distinct emotional intelligence and personality characteristics.

**Build steps:**

1. Create `personality_traits.py` using established personality frameworks (Big Five, MBTI-inspired).
2. Develop personas with different combinations: high empathy/low assertiveness, analytical/detail-oriented, creative/spontaneous, pragmatic/results-focused.
3. Include emotional response patterns and interpersonal styles.
4. Test with scenarios requiring emotional intelligence and people management.

**Acceptance criteria:**

- Personality traits consistently influence response style and content.
- Emotional intelligence levels appropriately affect interpersonal advice.
- Responses reflect realistic personality-driven behavior patterns.
- Different personalities provide valuable, distinct perspectives on human situations.

---

## 7) Expertise level calibration

**Goal:** Create personas with calibrated expertise levels from novice to world-class expert.

**Build steps:**

1. Create `expertise_levels.py` with the same domain at different competency levels.
2. Use software development as the domain: Beginner (6 months), Intermediate (3 years), Senior (8 years), Architect (15+ years).
3. Calibrate knowledge depth, terminology usage, problem complexity handling, and strategic thinking.
4. Test with technical problems of varying difficulty.

**Acceptance criteria:**

- Novice personas appropriately limit scope and seek clarification.
- Intermediate personas show growing confidence with clear knowledge boundaries.
- Senior personas demonstrate deep practical experience and pattern recognition.
- Expert personas think strategically and consider long-term implications.

---

## 8) Dynamic persona switching

**Goal:** Implement systems that can switch personas based on context and requirements.

**Build steps:**

1. Create `persona_switcher.py` with context-aware persona selection.
2. Implement decision logic for when to switch personas during conversations.
3. Create transition protocols that maintain conversation coherence.
4. Test with complex scenarios requiring multiple types of expertise.

**Acceptance criteria:**

- System correctly identifies when persona switches are beneficial.
- Transitions are smooth and explained to maintain user trust.
- Multiple personas contribute meaningfully to complex problems.
- Conversation coherence is maintained across persona changes.

---

## 9) Persona consistency validation

**Goal:** Develop systems to ensure personas maintain consistency across interactions.

**Build steps:**

1. Create `consistency_validator.py` that checks persona adherence.
2. Implement validation metrics: terminology consistency, knowledge level appropriateness, behavioral pattern maintenance, and contradiction detection.
3. Create feedback loops for persona refinement.
4. Test with extended conversations to identify consistency drift.

**Acceptance criteria:**

- Validation accurately identifies persona inconsistencies.
- Metrics provide actionable feedback for persona improvement.
- Feedback loops successfully reduce consistency drift over time.
- Extended conversations maintain believable persona coherence.

---

## 10) Adaptive persona learning

**Goal:** Create personas that can evolve and improve based on interaction feedback.

**Build steps:**

1. Create `adaptive_personas.py` with learning and refinement capabilities.
2. Implement feedback collection: user satisfaction, response effectiveness, knowledge gap identification.
3. Create persona updating mechanisms that maintain core identity while improving performance.
4. Test with scenarios where initial persona responses are suboptimal.

**Acceptance criteria:**

- Personas improve performance while maintaining core characteristics.
- Learning focuses on knowledge gaps and communication effectiveness.
- Adaptation preserves persona authenticity and user trust.
- System handles conflicting feedback appropriately.

---

## Notes for Students

- **Authenticity**: Research real characteristics when creating personas based on actual people or cultures.
- **Consistency**: Maintain persona characteristics throughout entire conversations.
- **Boundaries**: Clearly define what each persona knows and doesn't know.
- **Respect**: Ensure cultural and professional personas are respectful and accurate.

## Common Issues and Solutions

- **Persona bleeding**: Use clear persona boundaries and validation checks.
- **Inconsistent expertise**: Calibrate knowledge levels carefully and maintain them.
- **Cultural stereotypes**: Research authentic cultural perspectives rather than assumptions.
- **Flat characters**: Include personality quirks and individual thinking patterns.

## Extension Challenges

- Create a persona marketplace with ratings and reviews.
- Implement persona ensemble systems for collaborative problem-solving.
- Build persona evolution tracking to show learning over time.
- Develop persona recommendation systems based on task requirements.
