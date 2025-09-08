# L06: Applying CoT and ReAct Prompting with Python

This lesson provides hands-on practice implementing both CoT and ReAct prompts to solve complex problems. You'll build working systems that demonstrate the power of structured reasoning and action-taking in AI agents.

Below are **10 build-style exercises** that progress from basic implementations to sophisticated reasoning and action systems.

---

## 1) Retail analytics problem solver with CoT

**Goal:** Build a CoT system for analyzing retail business problems with step-by-step reasoning.

**Build steps:**

1. Create `retail_analytics_cot.py` with structured retail analysis capabilities.
2. Implement analysis framework: data understanding, trend identification, root cause analysis, recommendation generation.
3. Use sample retail scenario: "Sales dropped 15% last quarter, inventory turnover decreased, customer complaints increased."
4. Generate comprehensive analysis with clear reasoning steps.

**Acceptance criteria:**

- Analysis follows logical progression from data to insights to recommendations.
- Each reasoning step builds clearly on previous steps.
- Retail-specific knowledge is appropriately applied.
- Recommendations are actionable and well-justified.

---

## 2) Financial planning ReAct agent

**Goal:** Create a ReAct agent that can gather information and provide financial planning advice.

**Build steps:**

1. Create `financial_planning_react.py` with financial analysis and planning tools.
2. Implement tools: budget calculator, investment analyzer, risk assessor, goal tracker.
3. Use scenario: "Help me plan for retirement in 25 years with current savings of $50,000."
4. Agent should gather additional information and provide comprehensive planning.

**Acceptance criteria:**

- Agent gathers necessary information through structured questioning.
- Financial calculations are accurate and appropriate.
- Recommendations consider risk tolerance and time horizon.
- Plan includes specific, actionable steps.

---

## 3) Debugging assistant with verification CoT

**Goal:** Build a debugging assistant that uses CoT with verification steps to diagnose code problems.

**Build steps:**

1. Create `debugging_assistant_cot.py` with systematic debugging methodology.
2. Implement debugging steps: problem identification, hypothesis formation, evidence gathering, solution verification.
3. Include code analysis tools and verification mechanisms.
4. Test with realistic programming bugs in different languages.

**Acceptance criteria:**

- Debugging follows systematic methodology with clear reasoning.
- Hypotheses are well-formed and testable.
- Solutions are verified before being recommended.
- Approach works across different programming languages and bug types.

---

## 4) Medical diagnosis support with multi-path reasoning

**Goal:** Create a diagnostic reasoning system that explores multiple diagnostic pathways.

**Build steps:**

1. Create `medical_diagnosis_cot.py` with differential diagnosis capabilities.
2. Implement multiple reasoning paths for symptom analysis.
3. Use medical knowledge bases and diagnostic criteria.
4. Test with complex cases requiring consideration of multiple conditions.

**Acceptance criteria:**

- Multiple diagnostic pathways are explored systematically.
- Differential diagnosis considers appropriate conditions.
- Reasoning incorporates medical knowledge appropriately.
- Recommendations include appropriate caveats about medical consultation.

---

## 5) Project management ReAct agent

**Goal:** Build a ReAct agent for project management that can plan, track, and optimize project execution.

**Build steps:**

1. Create `project_management_react.py` with comprehensive project management tools.
2. Implement tools: timeline creator, resource allocator, risk assessor, progress tracker, stakeholder communicator.
3. Use scenario: "Manage the development of a mobile app with a team of 8 people and 6-month deadline."
4. Agent should create comprehensive project plans and adapt to changing conditions.

**Acceptance criteria:**

- Project plans are realistic and well-structured.
- Resource allocation considers team capabilities and constraints.
- Risk assessment identifies and mitigates potential issues.
- Plans adapt appropriately to changing requirements or delays.

---

## 6) Research assistant with source verification

**Goal:** Create a research assistant that uses ReAct to gather and verify information from multiple sources.

**Build steps:**

1. Create `research_assistant_react.py` with information gathering and verification capabilities.
2. Implement tools: web search, source evaluation, fact checking, citation management.
3. Include verification steps for information accuracy and reliability.
4. Test with research questions requiring multiple sources and fact verification.

**Acceptance criteria:**

- Information gathering is systematic and comprehensive.
- Sources are evaluated for credibility and relevance.
- Facts are cross-referenced and verified.
- Research outputs include proper citations and reliability assessments.

---

## 7) Customer service optimization with CoT analysis

**Goal:** Build a system that analyzes customer service scenarios using structured CoT reasoning.

**Build steps:**

1. Create `customer_service_cot.py` with customer issue analysis and resolution planning.
2. Implement analysis framework: issue categorization, root cause analysis, solution evaluation, satisfaction prediction.
3. Use complex customer scenarios with multiple issues and stakeholders.
4. Generate comprehensive resolution strategies with reasoning justification.

**Acceptance criteria:**

- Issue analysis is thorough and considers multiple perspectives.
- Root cause analysis goes beyond surface symptoms.
- Solutions are evaluated for effectiveness and feasibility.
- Strategies consider long-term customer relationship impact.

---

## 8) Scientific experiment design with ReAct planning

**Goal:** Create a ReAct agent that can design and plan scientific experiments.

**Build steps:**

1. Create `experiment_design_react.py` with experimental design and validation tools.
2. Implement tools: hypothesis formulation, methodology design, statistical planning, ethical review.
3. Use scenario: "Design an experiment to test the effectiveness of a new learning technique."
4. Agent should create comprehensive experimental protocols.

**Acceptance criteria:**

- Experimental designs are scientifically sound and well-structured.
- Hypotheses are clear, testable, and appropriately scoped.
- Methodology addresses potential confounding variables.
- Statistical planning ensures adequate power and appropriate analysis.

---

## 9) Legal case analysis with multi-perspective CoT

**Goal:** Build a legal analysis system that examines cases from multiple legal perspectives.

**Build steps:**

1. Create `legal_analysis_cot.py` with multi-perspective legal reasoning.
2. Implement perspectives: plaintiff, defendant, judge, jury, regulatory body.
3. Include legal research, precedent analysis, and argument construction.
4. Test with complex legal scenarios involving multiple areas of law.

**Acceptance criteria:**

- Legal analysis considers multiple stakeholder perspectives.
- Precedent research is appropriate and well-integrated.
- Arguments are logically structured and legally sound.
- Analysis identifies potential strengths and weaknesses of different positions.

---

## 10) Crisis management coordinator with adaptive ReAct

**Goal:** Create an emergency response coordinator that adapts its approach based on crisis evolution.

**Build steps:**

1. Create `crisis_management_react.py` with emergency response and adaptation capabilities.
2. Implement tools: situation assessment, resource coordination, communication management, plan adaptation.
3. Include real-time adaptation based on changing crisis conditions.
4. Test with evolving crisis scenarios requiring dynamic response adjustment.

**Acceptance criteria:**

- Crisis response is rapid, systematic, and well-coordinated.
- Plans adapt appropriately to changing crisis conditions.
- Resource allocation is optimized for current priorities.
- Communication management keeps all stakeholders informed appropriately.

---

## Notes for Students

- **Domain expertise**: Research domain-specific knowledge for realistic problem-solving.
- **Tool integration**: Build robust tools that provide reliable information for reasoning.
- **Error handling**: Implement comprehensive error handling for real-world robustness.
- **Performance measurement**: Track accuracy and effectiveness of reasoning and actions.

## Common Issues and Solutions

- **Domain knowledge gaps**: Supplement AI knowledge with domain-specific information sources.
- **Tool reliability**: Implement fallbacks and error handling for unreliable tools.
- **Reasoning complexity**: Balance thoroughness with computational efficiency.
- **Context management**: Maintain relevant context while managing token limitations.

## Extension Challenges

- Build domain-specific reasoning pattern libraries.
- Create automated evaluation systems for reasoning quality.
- Implement learning mechanisms that improve domain expertise over time.
- Develop collaborative reasoning systems with multiple specialized agents.
