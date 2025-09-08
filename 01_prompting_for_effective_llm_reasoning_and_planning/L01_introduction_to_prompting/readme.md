# L01: Introduction to Prompting for Effective LLM Reasoning and Planning

This lesson introduces the core concepts of Agentic AI, the course structure, prerequisites, and learning environment setup. You'll learn what makes AI agents different from simple chatbots and establish the foundation for building sophisticated AI systems.

Below are **10 build-style exercises** that progress from basic environment setup to foundational agent concepts. Each exercise includes step-by-step instructions and clear acceptance criteria.

---

## 1) Environment setup and OpenAI API connection

**Goal:** Establish a working Python environment with OpenAI API access.

**Build steps:**
1. Create a new directory `agentic_ai_exercises` and set up a virtual environment.
2. Install required packages: `openai`, `python-dotenv`, `pydantic`.
3. Create `.env` file with your OpenAI API key.
4. Write `test_connection.py` that makes a simple API call to verify connectivity.

**Acceptance criteria:**
- Virtual environment activates successfully.
- Script connects to OpenAI API and receives a response.
- Environment variables load correctly from `.env` file.
- No API key exposed in code.

---

## 2) Basic prompt structure and response handling

**Goal:** Learn fundamental prompt-response patterns and error handling.

**Build steps:**
1. Create `basic_prompting.py` with a function that sends prompts to GPT-3.5-turbo.
2. Implement basic error handling for API failures and rate limits.
3. Test with a simple prompt: "What is the capital of France?"
4. Display response with proper formatting.

**Acceptance criteria:**
- Function successfully sends prompts and receives responses.
- Handles common API errors gracefully (rate limits, invalid keys, network issues).
- Response text is cleanly formatted and displayed.
- Code follows basic Python best practices.

---

## 3) Understanding system vs user messages

**Goal:** Learn the difference between system and user message roles in chat completions.

**Build steps:**
1. Create `message_roles.py` that demonstrates system vs user messages.
2. Test with system message: "You are a helpful assistant that always responds in exactly 10 words."
3. Send user message: "Explain quantum computing."
4. Compare responses with and without the system message.

**Acceptance criteria:**
- Script demonstrates clear difference between system and user roles.
- System message effectively constrains the assistant's behavior.
- Code properly structures messages array for the API.
- Output shows the impact of system message on response style.

---

## 4) Temperature and creativity control

**Goal:** Understand how temperature affects response variability and creativity.

**Build steps:**
1. Create `temperature_test.py` that sends the same prompt with different temperatures (0.0, 0.5, 1.0, 1.5).
2. Use prompt: "Write a creative story about a robot learning to paint."
3. Generate 3 responses for each temperature setting.
4. Analyze and display the differences in creativity and consistency.

**Acceptance criteria:**
- Script tests at least 4 different temperature values.
- Lower temperatures produce more consistent outputs.
- Higher temperatures show increased creativity and variability.
- Results clearly demonstrate temperature's effect on response diversity.

---

## 5) Token counting and cost estimation

**Goal:** Learn to monitor token usage and estimate API costs.

**Build steps:**
1. Install `tiktoken` library for token counting.
2. Create `token_counter.py` that counts tokens in prompts before sending.
3. Implement cost calculation based on current OpenAI pricing.
4. Test with prompts of varying lengths and track actual vs estimated usage.

**Acceptance criteria:**
- Accurately counts tokens in input prompts using tiktoken.
- Calculates estimated costs before API calls.
- Compares estimated vs actual token usage from API response.
- Displays cost breakdown (input tokens, output tokens, total cost).

---

## 6) Simple conversation memory

**Goal:** Implement basic conversation context management.

**Build steps:**
1. Create `conversation_memory.py` that maintains chat history.
2. Implement a simple loop where users can have ongoing conversations.
3. Track conversation history and include it in subsequent API calls.
4. Add a command to clear conversation history.

**Acceptance criteria:**
- Maintains conversation context across multiple exchanges.
- User can ask follow-up questions that reference previous messages.
- Implements clear command to reset conversation.
- Handles conversation length limits gracefully.

---

## 7) Response validation and parsing

**Goal:** Learn to validate and parse structured responses from the LLM.

**Build steps:**
1. Create `response_parser.py` that requests JSON-formatted responses.
2. Ask the LLM to analyze sentiment and return: `{"sentiment": "positive/negative/neutral", "confidence": 0.8, "key_phrases": ["happy", "excited"]}`
3. Implement JSON parsing with error handling for malformed responses.
4. Test with various sentiment analysis examples.

**Acceptance criteria:**
- Successfully requests structured JSON responses from LLM.
- Parses valid JSON responses correctly.
- Handles malformed JSON gracefully with retry logic.
- Validates response structure matches expected schema.

---

## 8) Prompt templates and variable substitution

**Goal:** Create reusable prompt templates with dynamic content.

**Build steps:**
1. Create `prompt_templates.py` with template functions.
2. Implement templates for: email writing, code review, and text summarization.
3. Use Python string formatting or Jinja2 for variable substitution.
4. Test each template with different input parameters.

**Acceptance criteria:**
- Templates accept parameters and generate contextual prompts.
- Variable substitution works correctly for all templates.
- Templates produce relevant, high-quality responses.
- Code is reusable and follows DRY principles.

---

## 9) Basic prompt optimization

**Goal:** Learn iterative prompt improvement techniques.

**Build steps:**
1. Create `prompt_optimizer.py` that tests multiple prompt variations.
2. Start with a basic prompt for extracting key information from text.
3. Create 3-5 variations with different approaches (direct instruction, examples, role-playing).
4. Compare response quality and consistency across variations.

**Acceptance criteria:**
- Tests multiple prompt variations systematically.
- Measures response quality using consistent criteria.
- Documents which prompt variations perform best.
- Demonstrates measurable improvement through iteration.

---

## 10) Introduction to agentic behavior patterns

**Goal:** Understand what makes a prompt "agentic" vs simply generative.

**Build steps:**
1. Create `agentic_patterns.py` that demonstrates goal-oriented vs reactive prompting.
2. Implement examples of: planning ahead, breaking down complex tasks, and self-correction.
3. Compare "passive" prompts vs "agentic" prompts for the same task.
4. Document the key differences in approach and outcomes.

**Acceptance criteria:**
- Demonstrates clear difference between reactive and agentic prompting styles.
- Shows examples of forward-thinking and task decomposition.
- Agentic prompts produce more structured, goal-oriented responses.
- Code illustrates foundational concepts for later agent development.

---

## Notes for Students

- **Environment consistency**: Use the same virtual environment across all exercises.
- **API key security**: Never commit `.env` files or expose API keys in code.
- **Error handling**: Always implement proper error handling for API calls.
- **Documentation**: Keep notes on what works well for different prompt types.
- **Experimentation**: Try variations of the exercises to deepen understanding.

## Common Issues and Solutions

- **Rate limiting**: Implement exponential backoff for API retry logic.
- **Token limits**: Monitor context length and truncate when necessary.
- **Inconsistent responses**: Use lower temperature values for more consistent outputs.
- **Cost management**: Track token usage to avoid unexpected charges.

## Extension Challenges

- Implement automatic prompt optimization using response quality metrics.
- Create a command-line interface for interactive prompt testing.
- Build a prompt library with categorized, reusable templates.
- Add logging and analytics to track prompt performance over time.
