# LLM Using Chainlit

This project is a Chainlit-based chat application that acts as a food recommendation assistant. It uses a system prompt to behave like a Zomato-style AI that suggests cuisines, dishes, price ranges, restaurants, and the best pick based on the user’s preferences.

The app keeps the conversation state in Chainlit session memory and sends each user message to a Groq-hosted LLM through the helper in `src/llm.py`.

## Requirements

- Python 3.12 or compatible
- A Groq API key set in the environment as `GROQ_API_KEY`

## Installation

1. Create and activate a virtual environment.
2. Install the project dependencies:

```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the project root and add your API key:

```env
GROQ_API_KEY=your_groq_api_key_here
```

## How to Run

Start the Chainlit app from the project root:

```bash
chainlit run app.py --watch
```

Then open the local URL shown in the terminal, usually `http://localhost:8000`.

## How It Works

- `app.py` initializes a Chainlit chat session.
- `src/prompt.py` defines the system instruction for the assistant.
- `src/llm.py` sends the message history to Groq using the `llama-3.1-8b-instant` model.
- The assistant responds with cuisine suggestions, dishes, estimated prices, restaurant recommendations, and a best pick.

## Example Prompt

You can ask something like:

```text
Suggest a dinner option for 2 people with a medium budget and veg preference.
```