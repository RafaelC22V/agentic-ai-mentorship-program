# L02: The Role of Prompting in Agentic AI with Python and OpenAI

This lesson explores what AI Agents are, how they work, and the critical role prompting plays in guiding them to reason, plan, and act to achieve goals. You'll learn to distinguish between simple AI responses and true agentic behavior.

Below are **10 build-style exercises** that progress from understanding agent fundamentals to implementing basic agentic behaviors.

---

## 1) Comparing reactive vs agentic responses

**Goal:** Understand the fundamental difference between reactive AI and agentic AI behavior.

**Build steps:**

1. Create `reactive_vs_agentic.py` with two functions: `reactive_query()` and `agentic_query()`.
2. For reactive: Ask "What's the weather like?" and return the immediate response.
3. For agentic: Use a prompt that asks the AI to identify what information it needs, request clarification, and propose next steps.
4. Compare the responses and document the behavioral differences.

**Acceptance criteria:**

- Reactive function produces direct, immediate answers without context gathering.
- Agentic function demonstrates information-seeking and planning behavior.
- Clear documentation of differences in response patterns.
- Both functions handle the same input queries but with different approaches.

---

## 2) Goal-oriented prompting patterns

**Goal:** Learn to structure prompts that drive toward specific objectives.

**Build steps:**

1. Create `goal_oriented_prompts.py` with templates for different goal types.
2. Implement goal categories: information gathering, problem solving, task completion, and decision making.
3. Each template should include: objective statement, context requirements, success criteria, and next steps.
4. Test with a planning scenario: "Help me organize a conference for 100 people."

**Acceptance criteria:**

- Templates consistently produce goal-focused responses.
- Responses include clear action items and next steps.
- Success criteria are addressed in the AI's planning.
- Different goal types produce appropriately different response structures.

---

## 3) Implementing reasoning chains in prompts

**Goal:** Structure prompts to encourage step-by-step logical reasoning.

**Build steps:**

1. Create `reasoning_chains.py` that implements "thinking step by step" patterns.
2. Use explicit instruction: "Think through this step by step, showing your reasoning at each stage."
3. Test with logic problems: "If all roses are flowers, and some flowers are red, what can we conclude about roses?"
4. Implement validation to ensure reasoning steps are present in responses.

**Acceptance criteria:**

- Responses consistently show explicit reasoning steps.
- Logic flows clearly from premise to conclusion.
- Each step builds on the previous step logically.
- Validation correctly identifies presence/absence of reasoning chains.

---

## 4) Context management for agent memory

**Goal:** Implement systems for maintaining relevant context across interactions.

**Build steps:**

1. Create `context_manager.py` with a class that manages conversation context.
2. Implement methods: `add_context()`, `get_relevant_context()`, `summarize_context()`.
3. Test with a multi-turn problem-solving scenario requiring information from earlier exchanges.
4. Implement context pruning when approaching token limits.

**Acceptance criteria:**

- Context manager maintains relevant information across turns.
- Retrieves appropriate context for current queries.
- Summarization preserves essential information while reducing tokens.
- Gracefully handles context length limitations.

---

## 5) Planning and task decomposition prompts

**Goal:** Learn to prompt for breaking complex tasks into manageable steps.

**Build steps:**

1. Create `task_decomposer.py` that breaks complex requests into subtasks.
2. Use prompts that request: task analysis, dependency identification, sequencing, and resource requirements.
3. Test with: "Create a marketing strategy for a new mobile app."
4. Implement validation to ensure decomposition includes timing and dependencies.

**Acceptance criteria:**

- Complex tasks are broken into clear, actionable subtasks.
- Dependencies between tasks are identified and documented.
- Sequencing reflects logical order and constraints.
- Resource requirements are considered for each subtask.

---

## 6) Error handling and self-correction patterns

**Goal:** Implement prompts that enable AI to recognize and correct its own errors.

**Build steps:**

1. Create `self_correction.py` with error detection and correction mechanisms.
2. Implement a review phase: after generating a response, prompt the AI to check for errors.
3. Use validation prompts: "Review your answer for accuracy, completeness, and logical consistency."
4. Test with intentionally problematic queries to trigger self-correction.

**Acceptance criteria:**

- AI consistently reviews its own outputs for errors.
- Self-correction improves response quality measurably.
- Error detection covers accuracy, completeness, and logic.
- Correction process is systematic and reliable.

---

## 7) Multi-perspective analysis prompts

**Goal:** Structure prompts to analyze problems from multiple viewpoints.

**Build steps:**

1. Create `multi_perspective.py` that analyzes issues from different stakeholder perspectives.
2. For each analysis, include: stakeholder identification, perspective definition, concerns and priorities, and impact assessment.
3. Test with: "Analyze the impact of remote work policies on a company."
4. Synthesize perspectives into balanced recommendations.

**Acceptance criteria:**

- Identifies relevant stakeholders accurately.
- Perspectives reflect realistic concerns and priorities.
- Analysis shows understanding of conflicting viewpoints.
- Synthesis balances different perspectives fairly.

---

## 8) Adaptive prompting based on response quality

**Goal:** Implement dynamic prompt adjustment based on response effectiveness.

**Build steps:**

1. Create `adaptive_prompting.py` with quality assessment and prompt modification.
2. Implement response quality metrics: completeness, relevance, specificity, and actionability.
3. Automatically adjust prompts when quality thresholds aren't met.
4. Test with queries that initially produce poor responses, then improve through adaptation.

**Acceptance criteria:**

- Quality metrics accurately assess response effectiveness.
- Prompt adjustments improve subsequent response quality.
- Adaptation process converges on better prompts over time.
- System handles edge cases where adaptation doesn't help.

---

## 9) Tool-use preparation prompts

**Goal:** Structure prompts that prepare AI for using external tools and APIs.

**Build steps:**

1. Create `tool_preparation.py` that describes available tools and their usage patterns.
2. Implement tool description templates: purpose, inputs, outputs, and usage examples.
3. Create prompts that help AI decide when and how to use tools.
4. Test with scenarios requiring calculator, web search, and data analysis tools.

**Acceptance criteria:**

- AI correctly identifies when tools are needed.
- Tool selection matches the requirements of the task.
- Usage patterns follow the specified interfaces.
- Fallback behavior handles unavailable tools gracefully.

---

## 10) Agent persona and behavior configuration

**Goal:** Learn to configure consistent agent personalities and behavioral patterns.

**Build steps:**

1. Create `agent_persona.py` with configurable personality and behavior traits.
2. Implement persona dimensions: expertise level, communication style, risk tolerance, and decision-making approach.
3. Test with the same queries using different personas (conservative analyst vs creative strategist).
4. Ensure persona consistency across multiple interactions.

**Acceptance criteria:**

- Personas produce distinctly different response styles.
- Behavior remains consistent within each persona across interactions.
- Expertise level appropriately affects depth and complexity of responses.
- Communication style reflects the configured personality traits.

---

## Notes for Students

- **Behavioral patterns**: Focus on how prompts shape AI behavior, not just content.
- **Consistency**: Test prompts multiple times to ensure reliable behavior patterns.
- **Documentation**: Keep notes on which prompt structures produce desired agentic behaviors.
- **Experimentation**: Try variations to understand the boundaries of agentic prompting.

## Common Issues and Solutions

- **Inconsistent agency**: Use explicit instructions about reasoning and planning requirements.
- **Context loss**: Implement robust context management from the beginning.
- **Shallow responses**: Include depth requirements and examples in prompts.
- **Goal drift**: Regularly reinforce objectives throughout longer interactions.

## Extension Challenges

- Create a prompt library for different types of agentic behaviors.
- Implement automatic persona switching based on task requirements.
- Build a response quality assessment system with multiple metrics.
- Develop adaptive prompting that learns from interaction history.
