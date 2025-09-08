# L05: Chain-of-Thought and ReAct Prompting

This lesson explains the conceptual frameworks for Chain-of-Thought (CoT) for guided reasoning and ReAct (Reason+Act) for enabling agents to plan and take actions. You'll learn to structure prompts that encourage systematic thinking and action-oriented behavior.

Below are **10 build-style exercises** that progress from basic CoT implementation to sophisticated ReAct agent behaviors.

---

## 1) Basic Chain-of-Thought implementation

**Goal:** Implement fundamental CoT prompting to encourage step-by-step reasoning.

**Build steps:**

1. Create `basic_cot.py` with standard CoT prompt templates.
2. Implement the classic "Let's think step by step" approach.
3. Test with mathematical word problems: "Sarah has 3 apples, buys 7 more, gives away 4. How many does she have?"
4. Compare responses with and without CoT prompting.

**Acceptance criteria:**

- CoT prompts consistently produce step-by-step reasoning.
- Mathematical problems show clear intermediate steps.
- Reasoning flows logically from one step to the next.
- Final answers are more accurate with CoT than without.

---

## 2) Few-shot CoT with exemplar reasoning

**Goal:** Use examples to teach the AI specific reasoning patterns.

**Build steps:**

1. Create `few_shot_cot.py` with curated reasoning examples.
2. Provide 2-3 examples of high-quality step-by-step reasoning for different problem types.
3. Include examples for: logical reasoning, mathematical calculation, and causal analysis.
4. Test with new problems of the same types to verify pattern transfer.

**Acceptance criteria:**

- AI follows the reasoning patterns demonstrated in examples.
- Response quality improves significantly with good examples.
- Reasoning structure matches the exemplar format.
- Pattern transfer works across similar problem types.

---

## 3) Self-consistency CoT with multiple reasoning paths

**Goal:** Generate multiple reasoning paths and select the most consistent answer.

**Build steps:**

1. Create `self_consistency_cot.py` that generates multiple reasoning chains.
2. Implement voting mechanism to select most frequent answer.
3. Test with ambiguous problems where multiple reasoning approaches are valid.
4. Track consistency metrics across different reasoning attempts.

**Acceptance criteria:**

- Multiple reasoning paths are genuinely different, not repetitive.
- Voting mechanism correctly identifies most supported answers.
- Consistency improves answer accuracy on ambiguous problems.
- System handles cases where no clear consensus emerges.

---

## 4) Basic ReAct framework implementation

**Goal:** Implement the fundamental Reason-Act cycle for agentic behavior.

**Build steps:**

1. Create `basic_react.py` with Thought-Action-Observation cycles.
2. Implement simple "actions": web search simulation, calculator, note-taking.
3. Use format: "Thought: [reasoning], Action: [action], Observation: [result]".
4. Test with information-gathering tasks requiring multiple steps.

**Acceptance criteria:**

- Agent consistently follows Thought-Action-Observation format.
- Reasoning (Thought) clearly connects to chosen actions.
- Observations inform subsequent reasoning and actions.
- Multi-step tasks are completed through iterative cycles.

---

## 5) Tool-augmented ReAct with external APIs

**Goal:** Extend ReAct to use real external tools and APIs.

**Build steps:**

1. Create `tool_react.py` with actual tool integration.
2. Implement tools: weather API, web search, unit converter, and text analyzer.
3. Create tool description templates that the agent can understand.
4. Test with tasks requiring multiple tool uses: "Plan a weekend in Seattle considering weather and local events."

**Acceptance criteria:**

- Agent successfully calls real external APIs.
- Tool selection matches task requirements appropriately.
- Error handling manages API failures gracefully.
- Complex tasks combine multiple tools effectively.

---

## 6) Verification and validation in reasoning chains

**Goal:** Implement self-checking mechanisms within CoT and ReAct processes.

**Build steps:**

1. Create `verified_reasoning.py` with built-in validation steps.
2. Add verification actions: "Check: [validation step]", "Verify: [cross-reference]".
3. Implement confidence scoring for reasoning steps.
4. Test with problems where initial reasoning might be incorrect.

**Acceptance criteria:**

- Verification steps catch and correct reasoning errors.
- Confidence scores accurately reflect reasoning certainty.
- Self-correction improves final answer accuracy.
- Validation processes are contextually appropriate.

---

## 7) Multi-step planning with ReAct

**Goal:** Use ReAct for complex planning tasks requiring strategic thinking.

**Build steps:**

1. Create `planning_react.py` with goal decomposition and strategic planning.
2. Implement planning actions: goal analysis, resource assessment, timeline creation, risk evaluation.
3. Use hierarchical planning: high-level strategy, mid-level tactics, detailed actions.
4. Test with business scenarios: "Develop a go-to-market strategy for a new SaaS product."

**Acceptance criteria:**

- Plans show clear goal decomposition and strategic thinking.
- Resource and timeline considerations are realistic.
- Risk assessment identifies and addresses potential issues.
- Plans are actionable and well-structured.

---

## 8) Error recovery and backtracking in ReAct

**Goal:** Implement robust error handling and backtracking capabilities.

**Build steps:**

1. Create `robust_react.py` with error detection and recovery mechanisms.
2. Implement backtracking when actions fail or reasoning proves incorrect.
3. Add alternative path exploration when primary approaches fail.
4. Test with scenarios designed to trigger failures and require recovery.

**Acceptance criteria:**

- System detects when reasoning or actions are failing.
- Backtracking restores valid previous states effectively.
- Alternative approaches are explored when primary methods fail.
- Recovery maintains task progress and avoids infinite loops.

---

## 9) Collaborative CoT with multiple reasoning perspectives

**Goal:** Implement multi-perspective reasoning within single reasoning chains.

**Build steps:**

1. Create `collaborative_cot.py` with multiple viewpoint integration.
2. Simulate different expert perspectives within the reasoning process.
3. Implement perspective synthesis and conflict resolution.
4. Test with complex ethical or strategic decisions requiring multiple viewpoints.

**Acceptance criteria:**

- Multiple perspectives contribute meaningfully to reasoning.
- Perspective conflicts are identified and addressed.
- Synthesis produces more comprehensive conclusions than single perspectives.
- Expert viewpoints are authentically represented.

---

## 10) Adaptive CoT/ReAct selection based on task complexity

**Goal:** Create systems that intelligently choose between CoT, ReAct, and hybrid approaches.

**Build steps:**

1. Create `adaptive_reasoning.py` with automatic approach selection.
2. Implement complexity assessment: task type, information requirements, action needs, uncertainty level.
3. Create decision logic for selecting optimal reasoning approach.
4. Test with diverse tasks to validate approach selection accuracy.

**Acceptance criteria:**

- System correctly identifies task characteristics affecting reasoning approach.
- Approach selection improves task completion effectiveness.
- Hybrid approaches are used appropriately for complex scenarios.
- Performance metrics validate approach selection decisions.

---

## Notes for Students

- **Prompt engineering**: Experiment with different formats for Thought-Action-Observation cycles.
- **Tool integration**: Start with simulated tools before adding real API calls.
- **Error handling**: Build robust error recovery from the beginning.
- **Performance tracking**: Monitor reasoning quality and task completion rates.

## Common Issues and Solutions

- **Reasoning loops**: Implement cycle detection and breaking mechanisms.
- **Action selection**: Provide clear tool descriptions and selection criteria.
- **Context management**: Maintain reasoning history without exceeding token limits.
- **Verification overhead**: Balance thoroughness with efficiency in validation steps.

## Extension Challenges

- Build a reasoning pattern library with reusable CoT templates.
- Create automated reasoning quality assessment systems.
- Implement learning mechanisms that improve reasoning patterns over time.
- Develop visualization tools for reasoning chains and ReAct cycles.
