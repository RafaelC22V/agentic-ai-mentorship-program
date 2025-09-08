# Agentic AI Mentorship Program

Welcome to the **Agentic AI Mentorship Program**! This repository is designed to help students and developers systematically evolve their AI agent development skills from foundational prompting techniques to advanced multi-agent systems through hands-on, build-style exercises and real-world scenarios.

## Purpose

This program provides a structured, progressive learning path for Agentic AI development. It covers advanced prompting techniques, agentic workflow patterns, agent building with tools and memory, and sophisticated multi-agent system orchestration. Each module contains step-by-step rubrics, acceptance criteria, and recommended best practices, making it ideal for self-study, bootcamps, or guided mentorship.

## Structure

The repository is organized into four main levels corresponding to the Agentic AI Nanodegree curriculum:

### **01_prompting_for_effective_llm_reasoning_and_planning/** (Base Level - 14 Lessons)
Foundational prompting techniques that power modern AI agents. Master Chain-of-Thought, ReAct, and feedback loops to build systems that can reason, plan, and solve complex problems.

**Key Topics:**
- Introduction to Agentic AI concepts and environment setup
- Role-based prompting for persona control
- Chain-of-Thought (CoT) and ReAct prompting frameworks
- Prompt instruction refinement techniques
- Prompt chaining for multi-step workflows
- LLM feedback loops for self-improving systems
- **Project:** Trip Planner - A Multi-Agent Travel Assistant System

### **02_agentic_workflows/** (Mid Level - 16 Lessons) 
Architect intelligent systems using core agentic workflow patterns. Learn to design and build teams of AI agents using Prompt Chaining, Routing, Parallelization, and advanced orchestration patterns.

**Key Topics:**
- Agentic workflow fundamentals and modeling
- Prompt Chaining workflows for sequential task decomposition
- Routing patterns for task classification and delegation
- Parallelization for concurrent agent execution
- Evaluator-Optimizer workflows for iterative refinement
- Orchestrator-Workers patterns for dynamic planning
- **Project:** AI-Powered Agentic Workflow for Project Management

### **03_building_agents/** (Advanced Level - 23 Lessons)
Build robust AI agents with tool integration, structured outputs, state management, and memory systems. Create data-driven agents that interact with external APIs, databases, and perform advanced retrieval tasks.

**Key Topics:**
- Tool integration via function calling
- Structured outputs with Pydantic validation
- Agent state management and transitions
- Short-term and long-term memory systems
- External API and database integration
- Web search and agentic RAG implementation
- Agent evaluation and performance metrics
- **Project:** GamerPlay - An AI Research Agent for the Video Game Industry

### **04_multi_agent_systems/** (Master Level - 15 Lessons)
Master coordinated teams of AI agents. Learn to orchestrate complex workflows, manage distributed state, implement advanced routing, and build production-ready multi-agent systems.

**Key Topics:**
- Multi-agent architecture design and implementation
- Agent orchestration and activity coordination
- Advanced routing and data flow management
- Distributed state management and coordination
- Multi-agent RAG for specialized retrieval
- Production deployment and monitoring
- **Project:** The Woody Paper Company Sales Team

## How to Use

1. **Prerequisites**: Ensure you have OpenAI API access, basic Python knowledge, and familiarity with generative AI concepts.

2. **Start at your level**: Begin with the appropriate level based on your experience:
   - **New to AI agents?** Start with 01_prompting_for_effective_llm_reasoning_and_planning
   - **Know basic prompting?** Jump to 02_agentic_workflows
   - **Understand workflows?** Begin with 03_building_agents
   - **Want advanced systems?** Start with 04_multi_agent_systems

3. **Follow the progression**: Each lesson within a level builds on the previous. Complete exercises in order for the smoothest learning experience.

4. **Practice hands-on**: Each exercise requires implementing working code. Don't just read - build and test!

5. **Meet acceptance criteria**: Each exercise has specific, verifiable outcomes. Ensure you meet all criteria before proceeding.

6. **Complete projects**: End-of-level projects synthesize all lesson concepts into comprehensive, portfolio-worthy applications.

## Environment Setup

### Required Dependencies
```bash
# Create virtual environment
python -m venv agentic_ai_env
source agentic_ai_env/bin/activate  # On Windows: agentic_ai_env\Scripts\activate

# Install core dependencies
pip install openai python-dotenv pydantic requests

# Optional but recommended
pip install jupyter pytest chromadb sqlalchemy tavily-python
```

### API Keys Setup
Create a `.env` file in the root directory:
```
OPENAI_API_KEY=your_openai_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here  # For web search exercises
```

### Project Structure
```
agentic_ai_mentorship_program/
├── 01_prompting_for_effective_llm_reasoning_and_planning/
│   ├── L01_introduction_to_prompting/
│   ├── L02_role_of_prompting_in_agentic_ai/
│   ├── ...
│   └── project_agentsville_trip_planner/
├── 02_agentic_workflows/
├── 03_building_agents/
├── 04_multi_agent_systems/
├── shared_utils/          # Common utilities across all levels
├── examples/              # Reference implementations
└── tests/                 # Automated test suites
```

## Assessment and Progress Tracking

Each exercise includes:
- **Objective**: Clear learning goal
- **Build Steps**: Detailed implementation guidance
- **Acceptance Criteria**: Specific, testable outcomes
- **Extension Challenges**: Optional advanced features

### Progress Indicators
- ✅ **Basic**: Meets all acceptance criteria
- 🚀 **Advanced**: Completes extension challenges
- 🏆 **Mastery**: Creates innovative variations

## Who Is This For?

- **AI Engineers** seeking structured agent development skills
- **Software Developers** transitioning to AI agent systems
- **Product Managers** wanting hands-on AI agent experience
- **Researchers** exploring practical agent implementations
- **Students** in AI/ML programs focusing on agent technologies

## Learning Outcomes

By completing this program, you will:

1. **Master Prompting Techniques**: Chain-of-Thought, ReAct, role-based prompting, and feedback loops
2. **Design Agentic Workflows**: Implement routing, parallelization, and orchestration patterns
3. **Build Production Agents**: Tool integration, state management, memory systems, and evaluation
4. **Orchestrate Multi-Agent Systems**: Coordinate teams of specialized agents for complex tasks
5. **Deploy Real Applications**: Create portfolio-worthy projects demonstrating agent capabilities

## Community and Support

- 📚 **Documentation**: Comprehensive guides and API references
- 💬 **Discussions**: Share solutions and get help from peers
- 🐛 **Issues**: Report bugs or suggest improvements
- 🔗 **Resources**: Curated links to papers, tools, and frameworks

## License

This educational content is provided under the MIT License. See LICENSE file for details.

---

*Start your journey into the future of AI agent development. Build intelligent systems that can reason, plan, and act autonomously to solve real-world problems.*
