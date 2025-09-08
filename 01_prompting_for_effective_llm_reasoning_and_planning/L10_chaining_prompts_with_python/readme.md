# L10: Chaining Prompts with Python

This lesson provides hands-on practice implementing a three-stage prompt chain with Pydantic-based gate checks to automate an insurance claim triage process. You'll build a production-ready system that demonstrates advanced chaining patterns, validation, and error handling.

Below are **10 build-style exercises** that progressively build a sophisticated insurance claim processing system using prompt chaining techniques. Each exercise adds complexity while maintaining reliability and observability.

---

## 1) Basic insurance claim intake chain

**Goal:** Create a three-step chain that processes raw claim descriptions into structured data.

**Build steps:**

1. Create `claim_processor.py` with three sequential prompts: extraction, classification, and priority assignment.
2. Implement extraction prompt that pulls key details (incident type, date, location, damage amount).
3. Add classification prompt that categorizes claims (auto, home, health, liability).
4. Create priority prompt that assigns urgency levels (low, medium, high, critical).

**Acceptance criteria:**

- Chain processes raw claim text through all three stages successfully.
- Each stage produces structured output that feeds cleanly into the next.
- Extraction captures all relevant claim details accurately.
- Classification and priority assignment are logically consistent.

---

## 2) Pydantic models for chain validation

**Goal:** Implement comprehensive data validation using Pydantic models at each chain stage.

**Build steps:**

1. Define `ClaimExtraction`, `ClaimClassification`, and `ClaimPriority` Pydantic models.
2. Add field validation for dates, amounts, categories, and priority levels.
3. Implement custom validators for business rules (damage amounts, valid incident types).
4. Integrate models into chain with validation error handling.

**Acceptance criteria:**

- Pydantic models enforce strict data validation at each chain stage.
- Custom validators catch business logic violations (invalid dates, unrealistic amounts).
- Validation errors provide clear feedback for debugging and correction.
- Invalid data cannot propagate to subsequent chain stages.

**Notes:**

```python
from pydantic import BaseModel, validator
from datetime import datetime
from typing import Optional

class ClaimExtraction(BaseModel):
    incident_type: str
    incident_date: datetime
    location: str
    damage_amount: Optional[float]
    description: str
    
    @validator('damage_amount')
    def validate_damage_amount(cls, v):
        if v is not None and v < 0:
            raise ValueError('Damage amount cannot be negative')
        return v
```

---

## 3) Implementing gate checks with confidence scoring

**Goal:** Add confidence scoring and gate checks that prevent low-quality outputs from proceeding.

**Build steps:**

1. Modify each prompt to include confidence scores (0-10) for their outputs.
2. Implement gate check functions that evaluate confidence thresholds.
3. Add retry logic for outputs that fail confidence gates.
4. Create escalation paths for persistently low-confidence results.

**Acceptance criteria:**

- Each chain stage produces confidence scores along with main outputs.
- Gate checks successfully filter out low-confidence results.
- Retry logic improves output quality through multiple attempts.
- Escalation handles cases where retry attempts fail to meet thresholds.

---

## 4) Error handling and recovery strategies

**Goal:** Build robust error handling that maintains chain functionality under various failure conditions.

**Build steps:**

1. Implement try-catch blocks with specific error handling for each failure type.
2. Add fallback prompts that use simpler approaches when primary prompts fail.
3. Create partial processing capability that completes available stages when others fail.
4. Test error handling with malformed inputs and API failures.

**Acceptance criteria:**

- Error handling gracefully manages API failures, timeout errors, and malformed responses.
- Fallback prompts maintain functionality when primary approaches fail.
- Partial processing allows useful results even when some stages fail.
- Error recovery maintains chain stability without user intervention.

---

## 5) Parallel processing for independent validation

**Goal:** Implement parallel validation checks that run independently of the main processing chain.

**Build steps:**

1. Create parallel validation prompts that verify extraction accuracy and classification consistency.
2. Implement async execution for validation checks that don't block main processing.
3. Add validation result aggregation that flags potential issues.
4. Create feedback mechanism that improves future processing based on validation results.

**Acceptance criteria:**

- Parallel validation runs concurrently with main chain processing.
- Validation checks identify extraction errors and classification inconsistencies.
- Validation results are aggregated into actionable feedback.
- Feedback mechanism demonstrates learning from validation insights.

---

## 6) Claim routing and escalation logic

**Goal:** Extend the chain with intelligent routing based on claim characteristics and risk assessment.

**Build steps:**

1. Add risk assessment stage that evaluates fraud potential and complexity.
2. Implement routing logic that directs claims to appropriate processing paths.
3. Create escalation rules for high-value, complex, or suspicious claims.
4. Test routing with diverse claim scenarios to validate decision logic.

**Acceptance criteria:**

- Risk assessment accurately identifies high-risk and complex claims.
- Routing logic directs claims to appropriate processing workflows.
- Escalation rules properly flag claims requiring human review.
- Decision logic is transparent and auditable for compliance purposes.

---

## 7) Chain state persistence and recovery

**Goal:** Implement state persistence that allows chain recovery after interruptions.

**Build steps:**

1. Create `ChainState` storage system that persists intermediate results.
2. Implement checkpoint saves after each successful chain stage.
3. Add recovery logic that resumes chains from the last successful checkpoint.
4. Test recovery with simulated interruptions at various chain stages.

**Acceptance criteria:**

- Chain state persists reliably after each successful stage.
- Recovery logic successfully resumes processing from checkpoints.
- No data loss occurs during interruption and recovery cycles.
- Performance impact of state persistence is minimal and acceptable.

---

## 8) Integration with external systems

**Goal:** Connect the chain to external insurance systems for data validation and case management.

**Build steps:**

1. Create mock external API for customer database and policy validation.
2. Integrate policy lookup into the extraction stage for claim validation.
3. Add case management system integration for claim tracking and updates.
4. Implement data synchronization between chain processing and external systems.

**Acceptance criteria:**

- External API integration provides real-time policy and customer validation.
- Case management integration tracks claim progress throughout the chain.
- Data synchronization maintains consistency across all systems.
- Integration failures don't break the core chain functionality.

---

## 9) Performance optimization and monitoring

**Goal:** Optimize chain performance and implement comprehensive monitoring for production use.

**Build steps:**

1. Add performance metrics collection (stage duration, total processing time, success rates).
2. Implement caching for repeated validations and lookups.
3. Create performance dashboard with real-time metrics and alerts.
4. Optimize prompt calls with batching and connection pooling.

**Acceptance criteria:**

- Performance metrics provide detailed insights into chain efficiency.
- Caching significantly reduces redundant API calls and processing time.
- Dashboard provides real-time visibility into chain performance and health.
- Optimizations maintain output quality while improving speed and efficiency.

---

## 10) Production deployment with comprehensive testing

**Goal:** Deploy the complete insurance claim processing chain with full production readiness.

**Build steps:**

1. Create comprehensive test suite covering normal and edge cases.
2. Implement load testing to validate performance under production volumes.
3. Deploy to staging environment with full monitoring and alerting.
4. Create operational runbooks for common issues and maintenance procedures.

**Acceptance criteria:**

- Test suite provides high confidence in chain reliability and accuracy.
- Load testing validates performance under realistic production conditions.
- Staging deployment demonstrates full production readiness with monitoring.
- Operational documentation enables effective ongoing maintenance and support.

**Notes:**

- Consider using container orchestration for scalable deployment.
- Implement A/B testing framework for chain optimization experiments.
- Add compliance logging for regulatory requirements in insurance processing.
- Create automated backup and disaster recovery procedures.

---

## Chapter Summary

This lesson demonstrated advanced prompt chaining through practical insurance claim processing:

- **Structured data flow** using Pydantic models for reliable chain execution
- **Confidence-based gating** to maintain quality throughout the processing pipeline
- **Robust error handling** with fallbacks and recovery strategies
- **Parallel validation** for quality assurance without blocking main processing
- **Intelligent routing** based on risk assessment and claim characteristics
- **State persistence** for reliable recovery from interruptions
- **External integration** with existing business systems and databases
- **Performance optimization** with caching, batching, and monitoring
- **Production deployment** with comprehensive testing and operational readiness

The insurance claim processor demonstrates how prompt chains can automate complex business processes while maintaining the reliability, observability, and integration capabilities required for production systems.
