# L09: Chaining Prompts for Agentic Reasoning

This lesson explains the conceptual framework for building multi-step AI workflows by linking the output of one prompt to the input of the next. You'll learn about validation checkpoints, error handling, and designing robust prompt chains that enable sophisticated agentic reasoning patterns.

Below are **10 build-style exercises** that progress from simple prompt sequences to complex multi-stage validation workflows. Each exercise builds toward creating reliable, production-ready prompt chains.

---

## 1) Basic sequential prompt chaining

**Goal:** Create a simple two-step prompt chain where the output of one prompt feeds into the next.

**Build steps:**

1. Create `basic_chain.py` with a function that takes customer feedback and first extracts sentiment.
2. Use the sentiment analysis output as input to a second prompt that generates appropriate responses.
3. Test with positive, negative, and neutral customer feedback examples.
4. Log intermediate outputs to understand data flow between prompts.

**Acceptance criteria:**

- First prompt accurately extracts sentiment from customer feedback.
- Second prompt uses sentiment to generate contextually appropriate responses.
- Chain handles different sentiment types effectively.
- Intermediate outputs are logged for debugging and verification.

---

## 2) Adding validation gates between chain steps

**Goal:** Implement validation checkpoints that ensure quality before proceeding to the next step.

**Build steps:**

1. Add validation function that checks if sentiment analysis output is valid (positive/negative/neutral).
2. Implement error handling for invalid sentiment outputs.
3. Create retry logic that attempts sentiment analysis again if validation fails.
4. Test with intentionally ambiguous feedback to trigger validation.

**Acceptance criteria:**

- Validation gates catch invalid or ambiguous sentiment outputs.
- Retry logic successfully recovers from initial failures.
- Invalid outputs don't propagate to subsequent chain steps.
- Error handling provides meaningful feedback about validation failures.

---

## 3) Multi-branch conditional chaining

**Goal:** Create prompt chains that follow different paths based on intermediate results.

**Build steps:**

1. Extend the customer feedback chain with different response strategies for each sentiment.
2. Implement branching logic: positive feedback → thank you + upsell, negative → apology + resolution.
3. Add a neutral path that requests more specific feedback.
4. Test all branches with appropriate customer feedback examples.

**Acceptance criteria:**

- Chain correctly branches based on sentiment analysis results.
- Each branch produces responses appropriate to the detected sentiment.
- Branching logic is clean and maintainable.
- All possible paths through the chain are tested and functional.

---

## 4) Implementing chain state management

**Goal:** Build a system to track and manage state throughout complex prompt chains.

**Build steps:**

1. Create a `ChainState` class that stores intermediate results and metadata.
2. Implement state persistence across chain steps (sentiment, confidence scores, branch taken).
3. Add state validation at each step to ensure required data is present.
4. Create state rollback capability for error recovery.

**Acceptance criteria:**

- State management preserves all intermediate results and metadata.
- State validation prevents invalid transitions between chain steps.
- Rollback capability allows recovery from errors without restarting the entire chain.
- State is easily inspectable for debugging and audit purposes.

---

## 5) Error recovery and fallback strategies

**Goal:** Design robust error handling that keeps chains functional even when individual steps fail.

**Build steps:**

1. Implement multiple fallback strategies for each chain step.
2. Add confidence scoring to determine when to use fallbacks vs primary responses.
3. Create escalation paths for persistent failures (human handoff, default responses).
4. Test error recovery with artificially induced failures.

**Acceptance criteria:**

- Fallback strategies activate appropriately when primary steps fail.
- Confidence scoring accurately triggers fallback decisions.
- Escalation paths gracefully handle unrecoverable errors.
- Error recovery maintains chain functionality without compromising quality.

---

## 6) Parallel processing in prompt chains

**Goal:** Implement parallel execution for independent chain steps to improve performance.

**Build steps:**

1. Identify independent steps in your chain that can run concurrently.
2. Implement async/await pattern for parallel prompt execution.
3. Add synchronization points where parallel results must be combined.
4. Measure performance improvement compared to sequential execution.

**Acceptance criteria:**

- Independent chain steps execute in parallel without conflicts.
- Synchronization correctly combines parallel results before dependent steps.
- Performance metrics show meaningful improvement over sequential processing.
- Parallel execution maintains same output quality as sequential chains.

---

## 7) Chain composition and reusability

**Goal:** Create modular chain components that can be composed into different workflows.

**Build steps:**

1. Extract common chain patterns into reusable components (validation, sentiment analysis, response generation).
2. Create a composition framework that allows mixing and matching components.
3. Build 2-3 different customer service workflows using the same components.
4. Test component reusability across different business contexts.

**Acceptance criteria:**

- Chain components are truly modular and context-independent.
- Composition framework allows flexible workflow creation.
- Same components work effectively in different business scenarios.
- Code reuse significantly reduces duplication across workflows.

---

## 8) Advanced validation with Pydantic models

**Goal:** Implement structured validation using Pydantic models for type safety and data validation.

**Build steps:**

1. Define Pydantic models for each chain step's input and output.
2. Replace manual validation with Pydantic validation throughout the chain.
3. Add custom validators for business logic (sentiment confidence thresholds, response quality).
4. Test validation with edge cases and invalid data.

**Acceptance criteria:**

- Pydantic models provide comprehensive type safety for all chain data.
- Custom validators enforce business rules and quality standards.
- Validation errors are informative and actionable.
- Type safety prevents runtime errors and improves code reliability.

**Notes:**

```python
from pydantic import BaseModel, validator

class SentimentAnalysis(BaseModel):
    sentiment: str
    confidence: float
    reasoning: str
    
    @validator('sentiment')
    def sentiment_must_be_valid(cls, v):
        if v not in ['positive', 'negative', 'neutral']:
            raise ValueError('Invalid sentiment value')
        return v
```

---

## 9) Chain monitoring and observability

**Goal:** Implement comprehensive monitoring to track chain performance and identify issues.

**Build steps:**

1. Add structured logging throughout the chain with correlation IDs.
2. Implement metrics collection (step duration, success rates, error types).
3. Create dashboard visualization for chain health monitoring.
4. Add alerting for chain failures and performance degradation.

**Acceptance criteria:**

- Structured logging provides complete audit trail for each chain execution.
- Metrics accurately track chain performance and reliability.
- Dashboard visualizations make chain health immediately apparent.
- Alerting enables proactive response to issues before user impact.

---

## 10) Production-ready chain orchestration

**Goal:** Build a complete chain orchestration system ready for production deployment.

**Build steps:**

1. Implement rate limiting and backoff strategies for API calls.
2. Add circuit breaker pattern for external service dependencies.
3. Create comprehensive integration tests covering all chain scenarios.
4. Deploy chain to staging environment with full monitoring.

**Acceptance criteria:**

- Rate limiting prevents API quota exhaustion and service degradation.
- Circuit breakers provide resilience against external service failures.
- Integration tests verify end-to-end chain functionality.
- Staging deployment demonstrates production readiness with full observability.

**Notes:**

- Consider using tools like Celery for distributed chain execution.
- Implement chain versioning for safe deployment updates.
- Add feature flags for controlled rollout of chain modifications.

---

## Chapter Summary

This lesson established fundamental patterns for prompt chaining:

- **Sequential chaining** for multi-step workflows and complex reasoning
- **Validation gates** for quality assurance and error prevention
- **Conditional branching** for context-aware response strategies
- **State management** for complex workflow orchestration
- **Error recovery** for robust production operation
- **Parallel processing** for performance optimization
- **Modular composition** for reusable and maintainable chains
- **Structured validation** with Pydantic for type safety
- **Comprehensive monitoring** for operational visibility
- **Production orchestration** for reliable deployment

These chaining patterns form the foundation for building sophisticated agentic systems that can reason through complex, multi-step problems while maintaining reliability and observability.
