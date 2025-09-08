# Shared Utilities for Agentic AI Mentorship Program

This directory contains common utilities, base classes, and helper functions that are used across all levels of the Agentic AI Mentorship Program.

## Structure

```plaintext
shared_utils/
├── agents/
│   ├── base_agent.py          # Base agent class with common functionality
│   ├── persona_manager.py     # Persona management and switching
│   ├── agent_registry.py      # Agent discovery and management
│   ├── agent_factory.py       # Dynamic agent creation and lifecycle
│   ├── specialist_agents.py   # Domain-specific agent implementations
│   └── multi_agent_coordinator.py # Multi-agent coordination patterns
├── communication/
│   ├── message_protocol.py    # Standardized message formats
│   ├── routing.py             # Message routing and delivery
│   ├── coordination.py        # Agent coordination primitives
│   ├── event_system.py        # Event-driven communication
│   └── pub_sub.py            # Publish-subscribe messaging
├── memory/
│   ├── memory_base.py         # Base memory interface
│   ├── short_term_memory.py   # Session-based memory
│   ├── long_term_memory.py    # Persistent memory storage
│   ├── vector_memory.py       # Vector-based semantic memory
│   ├── episodic_memory.py     # Event and experience memory
│   ├── working_memory.py      # Active processing memory
│   └── memory_consolidation.py # Memory optimization and cleanup
├── tools/
│   ├── tool_interface.py      # Standard tool interface
│   ├── api_tools.py           # Common API integrations
│   ├── data_tools.py          # Data processing utilities
│   ├── validation_tools.py    # Input/output validation
│   ├── math_tools.py          # Mathematical computation tools
│   ├── text_processing_tools.py # Text analysis and manipulation
│   ├── datetime_tools.py      # Date, time, and scheduling tools
│   ├── conversion_tools.py    # Data format conversion utilities
│   ├── web_tools.py           # Web scraping and search tools
│   └── database_tools.py      # Database interaction utilities
├── workflows/
│   ├── workflow_base.py       # Base workflow patterns
│   ├── chain_executor.py      # Prompt chaining implementation
│   ├── parallel_executor.py   # Parallel execution framework
│   ├── state_manager.py       # Workflow state management
│   ├── routing_engine.py      # Intelligent task routing
│   ├── orchestrator.py        # Orchestrator-workers pattern
│   ├── feedback_loops.py      # Self-improving systems
│   └── workflow_validator.py  # Quality gates and validation
├── prompting/
│   ├── prompt_templates.py    # Reusable prompt templates
│   ├── cot_patterns.py        # Chain-of-thought implementations
│   ├── react_patterns.py      # ReAct (reason+act) patterns
│   ├── persona_prompts.py     # Role-based prompting utilities
│   ├── refinement_engine.py   # Prompt optimization and refinement
│   └── prompt_chains.py       # Multi-step prompt workflows
├── state_management/
│   ├── state_machine.py       # State machine implementation
│   ├── state_schemas.py       # Pydantic state definitions
│   ├── transition_engine.py   # State transition logic
│   ├── hierarchical_states.py # Nested and hierarchical states
│   ├── distributed_state.py   # Multi-agent state coordination
│   └── state_persistence.py   # State storage and recovery
├── rag/
│   ├── rag_base.py           # Base RAG implementation
│   ├── retrieval_strategies.py # Adaptive retrieval methods
│   ├── document_processor.py # Document chunking and preprocessing
│   ├── query_processor.py    # Query analysis and expansion
│   ├── vector_store.py       # Vector database abstractions
│   ├── reranker.py           # Result reranking and filtering
│   ├── synthesis_engine.py   # Multi-source result synthesis
│   └── agentic_rag.py        # Self-reflective RAG systems
├── api_integration/
│   ├── http_client.py        # Robust HTTP request handling
│   ├── api_key_manager.py    # Secure credential management
│   ├── rate_limiter.py       # API rate limiting and throttling
│   ├── retry_engine.py       # Resilient request retry logic
│   ├── response_parser.py    # API response parsing and validation
│   └── openai_integration.py # OpenAI API utilities and wrappers
├── evaluation/
│   ├── metrics.py             # Performance metrics
│   ├── evaluators.py          # Agent evaluation frameworks
│   ├── benchmarks.py          # Standard benchmarks
│   ├── quality_gates.py       # Automated quality assessment
│   ├── performance_monitor.py # Real-time performance tracking
│   └── test_frameworks.py     # Testing utilities for agents
├── security/
│   ├── authentication.py     # Agent identity and authentication
│   ├── authorization.py      # Access control and permissions
│   ├── encryption.py         # Data encryption and security
│   ├── audit_logger.py       # Security event logging
│   └── threat_detection.py   # Anomaly and threat detection
└── utils/
    ├── config.py              # Configuration management
    ├── logging.py             # Structured logging
    ├── error_handling.py      # Common error patterns
    ├── helpers.py             # General utility functions
    ├── async_utils.py         # Asynchronous programming utilities
    ├── serialization.py       # Data serialization and deserialization
    ├── caching.py             # Caching strategies and implementations
    └── monitoring.py          # System monitoring and observability
```

## Installation

```bash
# Install shared utilities in development mode
pip install -e shared_utils/
```

## Usage Examples

### Basic Agent Implementation

```python
from shared_utils.agents import BaseAgent, PersonaManager
from shared_utils.memory import ShortTermMemory, WorkingMemory
from shared_utils.tools import APITools, MathTools

class MyAgent(BaseAgent):
    def __init__(self, name):
        super().__init__(name)
        self.persona = PersonaManager()
        self.short_memory = ShortTermMemory()
        self.working_memory = WorkingMemory()
        self.tools = APITools()
        self.math_tools = MathTools()
    
    def process_request(self, request):
        # Load appropriate persona
        self.persona.activate("professional_consultant")
        
        # Process using working memory
        context = self.working_memory.get_context()
        return self.generate_response(request, context)
```

### Multi-Agent Workflow Implementation

```python
from shared_utils.workflows import ChainExecutor, RoutingEngine, Orchestrator
from shared_utils.agents import AgentRegistry, SpecialistAgents
from shared_utils.communication import MessageProtocol

class MultiAgentWorkflow:
    def __init__(self):
        self.executor = ChainExecutor()
        self.router = RoutingEngine()
        self.orchestrator = Orchestrator()
        self.agents = AgentRegistry()
        self.communication = MessageProtocol()
    
    def execute_complex_task(self, task):
        # Route to appropriate specialist
        specialist = self.router.route_task(task)
        
        # Create execution chain
        chain = self.orchestrator.create_workflow(task, specialist)
        
        # Execute with coordination
        return self.executor.run(chain)
```

### Prompt Engineering Integration

```python
from shared_utils.prompting import PromptTemplates, CoTPatterns, ReActPatterns
from shared_utils.prompting import PersonaPrompts, RefinementEngine

class IntelligentPrompter:
    def __init__(self):
        self.templates = PromptTemplates()
        self.cot = CoTPatterns()
        self.react = ReActPatterns()
        self.personas = PersonaPrompts()
        self.refiner = RefinementEngine()
    
    def generate_optimized_prompt(self, task_type, persona, reasoning_type):
        # Get base template
        template = self.templates.get_template(task_type)
        
        # Apply persona
        persona_prompt = self.personas.apply_persona(template, persona)
        
        # Add reasoning pattern
        if reasoning_type == "chain_of_thought":
            structured_prompt = self.cot.apply_pattern(persona_prompt)
        elif reasoning_type == "react":
            structured_prompt = self.react.apply_pattern(persona_prompt)
        
        # Refine and optimize
        return self.refiner.optimize(structured_prompt)
```

### State Management Implementation

```python
from shared_utils.state_management import StateMachine, StateSchemas
from shared_utils.state_management import TransitionEngine, DistributedState

class StatefulAgent:
    def __init__(self):
        self.state_machine = StateMachine()
        self.schemas = StateSchemas()
        self.transitions = TransitionEngine()
        self.distributed_state = DistributedState()
    
    def setup_conversation_states(self):
        # Define states using schemas
        states = [
            self.schemas.create_state("greeting", properties=["user_name"]),
            self.schemas.create_state("information_gathering", properties=["collected_data"]),
            self.schemas.create_state("processing", properties=["analysis_results"]),
            self.schemas.create_state("response_generation", properties=["final_response"])
        ]
        
        # Configure transitions
        self.transitions.add_transition("greeting", "information_gathering", trigger="user_ready")
        self.transitions.add_transition("information_gathering", "processing", trigger="data_complete")
        
        # Initialize state machine
        self.state_machine.configure(states, self.transitions)
```

### RAG System Implementation

```python
from shared_utils.rag import RAGBase, RetrievalStrategies, DocumentProcessor
from shared_utils.rag import QueryProcessor, SynthesisEngine, AgenticRAG

class IntelligentRAGSystem:
    def __init__(self):
        self.rag_base = RAGBase()
        self.retrieval = RetrievalStrategies()
        self.doc_processor = DocumentProcessor()
        self.query_processor = QueryProcessor()
        self.synthesizer = SynthesisEngine()
        self.agentic_rag = AgenticRAG()
    
    def process_complex_query(self, query, documents):
        # Process documents
        processed_docs = self.doc_processor.chunk_and_embed(documents)
        
        # Analyze and expand query
        enhanced_query = self.query_processor.expand_query(query)
        
        # Use adaptive retrieval
        strategy = self.retrieval.select_strategy(enhanced_query)
        retrieved_docs = self.retrieval.retrieve(enhanced_query, processed_docs, strategy)
        
        # Synthesize with self-reflection
        return self.agentic_rag.synthesize_with_reflection(query, retrieved_docs)
```

### API Integration Implementation

```python
from shared_utils.api_integration import HTTPClient, APIKeyManager, RateLimiter
from shared_utils.api_integration import RetryEngine, ResponseParser, OpenAIIntegration

class RobustAPIAgent:
    def __init__(self):
        self.http_client = HTTPClient()
        self.key_manager = APIKeyManager()
        self.rate_limiter = RateLimiter()
        self.retry_engine = RetryEngine()
        self.parser = ResponseParser()
        self.openai = OpenAIIntegration()
    
    def call_external_api(self, service, endpoint, data):
        # Get secure credentials
        credentials = self.key_manager.get_credentials(service)
        
        # Apply rate limiting
        self.rate_limiter.acquire(service)
        
        # Make resilient request
        response = self.retry_engine.execute_with_retry(
            lambda: self.http_client.post(endpoint, data, credentials)
        )
        
        # Parse and validate response
        return self.parser.parse_and_validate(response)
```

## Key Features

- **Consistent Interfaces**: All utilities follow consistent design patterns and API conventions
- **Type Safety**: Full Pydantic integration for data validation and type checking
- **Error Handling**: Comprehensive error handling and recovery mechanisms
- **Logging**: Structured logging with context tracking and performance monitoring
- **Testing**: Built-in testing utilities and fixtures for all components
- **Documentation**: Comprehensive API documentation with examples and best practices
- **Async Support**: Full asynchronous programming support for scalable implementations
- **Security**: Built-in security features including encryption and access control
- **Monitoring**: Real-time performance monitoring and observability features
- **Caching**: Intelligent caching strategies for improved performance
- **Multi-Agent Coordination**: Advanced patterns for agent collaboration and orchestration

## Advanced Patterns

### Chain-of-Thought Implementation

```python
from shared_utils.prompting import CoTPatterns, PromptChains

# Implement structured reasoning
cot = CoTPatterns()
reasoning_chain = cot.create_reasoning_chain([
    "problem_analysis",
    "hypothesis_generation", 
    "evidence_evaluation",
    "conclusion_synthesis"
])

result = reasoning_chain.execute(problem_statement)
```

### ReAct Pattern Implementation

```python
from shared_utils.prompting import ReActPatterns
from shared_utils.tools import ToolInterface

# Implement reason+act pattern
react = ReActPatterns()
react_agent = react.create_agent({
    "reasoning_tools": ["analysis", "planning"],
    "action_tools": ["web_search", "calculator", "database_query"],
    "reflection_tools": ["validation", "improvement"]
})

result = react_agent.solve_problem(complex_task)
```

### Multi-Agent Orchestration

```python
from shared_utils.workflows import Orchestrator
from shared_utils.agents import SpecialistAgents
from shared_utils.communication import EventSystem

# Implement orchestrator-workers pattern
orchestrator = Orchestrator()
specialists = SpecialistAgents()
events = EventSystem()

# Create coordinated workflow
workflow = orchestrator.create_workflow([
    specialists.get("data_analyst"),
    specialists.get("market_researcher"), 
    specialists.get("report_generator")
])

# Execute with event coordination
result = workflow.execute_with_events(task, events)
```

### Agentic RAG Implementation

```python
from shared_utils.rag import AgenticRAG, RetrievalStrategies

# Implement self-reflective RAG
agentic_rag = AgenticRAG()
strategies = RetrievalStrategies()

# Configure adaptive retrieval
agentic_rag.configure({
    "reflection_enabled": True,
    "query_expansion": True,
    "multi_hop_reasoning": True,
    "result_validation": True
})

# Execute with self-improvement
result = agentic_rag.query_with_reflection(
    query="Complex research question",
    max_iterations=3,
    confidence_threshold=0.8
)
```

### Distributed State Management

```python
from shared_utils.state_management import DistributedState, StateMachine
from shared_utils.communication import MessageProtocol

# Implement distributed state coordination
distributed_state = DistributedState()
state_machine = StateMachine()
messaging = MessageProtocol()

# Configure multi-agent state coordination
coordinator = distributed_state.create_coordinator({
    "agents": ["agent1", "agent2", "agent3"],
    "consistency_model": "eventual_consistency",
    "conflict_resolution": "last_writer_wins",
    "sync_interval": 1.0
})

# Coordinate state across agents
coordinator.start_coordination(state_machine, messaging)
```

### Feedback Loop Implementation

```python
from shared_utils.workflows import FeedbackLoops
from shared_utils.evaluation import QualityGates

# Implement self-improving system
feedback = FeedbackLoops()
quality = QualityGates()

# Create improvement loop
improvement_loop = feedback.create_loop({
    "generate": lambda x: generate_solution(x),
    "evaluate": lambda x: quality.assess(x),
    "improve": lambda x, feedback: refine_solution(x, feedback),
    "max_iterations": 5,
    "improvement_threshold": 0.1
})

# Execute with continuous improvement
result = improvement_loop.execute_with_improvement(task)
```

## Common Patterns

### Agent Communication

```python
from shared_utils.communication import MessageProtocol, EventSystem

# Send message between agents
protocol = MessageProtocol()
message = protocol.create_message(
    sender="agent1",
    receiver="agent2", 
    content={"action": "process", "data": data}
)
protocol.send_message(message)

# Event-driven coordination
events = EventSystem()
events.subscribe("task_completed", callback=handle_completion)
events.publish("task_started", {"task_id": "12345"})
```

### Memory Management

```python
from shared_utils.memory import LongTermMemory, WorkingMemory, EpisodicMemory

# Store and retrieve memories
long_term = LongTermMemory()
working = WorkingMemory()
episodic = EpisodicMemory()

# Different memory types
long_term.store("user_preferences", {"style": "formal"})
working.update_context("current_task", task_details)
episodic.record_experience("user_interaction", interaction_data)

# Retrieve with context
preferences = long_term.retrieve("user_preferences")
context = working.get_active_context()
experiences = episodic.get_similar_experiences(current_situation)
```

### Performance Evaluation

```python
from shared_utils.evaluation import Metrics, Evaluators, PerformanceMonitor

# Evaluate agent performance
metrics = Metrics()
evaluator = Evaluators.get_evaluator("response_quality")
monitor = PerformanceMonitor()

# Real-time monitoring
monitor.start_monitoring(agent)
score = evaluator.evaluate(agent_response, ground_truth)
metrics.record("quality_score", score)

# Performance analytics
analytics = monitor.get_analytics()
trends = analytics.get_performance_trends()
```

## Version Compatibility

- Python 3.8+
- OpenAI API v1.0+
- Pydantic v2.0+
- Compatible with all course levels and exercises

## Contributing

When adding new utilities:

1. Follow the established interface patterns
2. Include comprehensive type hints
3. Add unit tests for all functionality
4. Update documentation and examples
5. Consider backward compatibility

## Getting Started

To start using shared utilities in your exercises:

1. Check the documentation and examples
2. Import the required modules
3. Initialize components with proper configuration
4. Implement error handling and logging
5. Add tests for your implementations

## Implementation Roadmap

### Phase 1: Core Infrastructure (Priority 1)

- Base agent classes and interfaces
- Communication protocols and messaging
- Basic workflow orchestration
- Essential memory management
- Core prompting utilities

### Phase 2: Advanced Features (Priority 2)

- State machines and distributed coordination
- RAG implementations and vector stores
- Tool integration frameworks
- Security and authentication
- Performance monitoring

### Phase 3: Specialized Components (Priority 3)

- Advanced evaluation metrics
- Multi-modal capabilities
- Integration adapters
- Deployment utilities
- Testing frameworks

### Phase 4: Enterprise Features (Priority 4)

- Production monitoring and alerting
- Compliance and governance
- Advanced security features
- Scalability optimizations
- Enterprise integrations

## Support

For issues with shared utilities:

1. Check the documentation and examples
2. Review existing issues in the repository
3. Create detailed issue reports with reproducible examples
4. Contribute fixes and improvements via pull requests

For detailed implementation guides and API documentation, see the individual module documentation in each directory.
