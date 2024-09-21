# {Untitled.AI}

{Untitled.AI} is an open-source conversational chatbot designed to learn from user interactions. Unlike traditional chatbots with pre-programmed responses, {Untitled.AI} evolves with each conversation, dynamically adjusting its responses based on previous conversations.

## Features
- **Dynamic Learning**: No hardcoded responses; {Untitled.AI} builds its knowledge based on interactions.
- **Mesh-based Response Matching**: Uses a "mesh" system to link patterns in prompts to responses, enhancing flexibility.
- **Tokenization & Lemmatization**: Text is cleaned, tokenized, and lemmatized for better accuracy and consistency.
- **Context-Aware Responses**: {Untitled.AI} considers previous prompts to offer more contextually appropriate answers.
- **Random Response Selection**: Prevents predictability by randomly selecting from valid responses.

## How It Works

### 1. Data Storage
Responses are stored in a `.json` file as a dictionary. Each key is a unique UUID, and the value is the tokenized response.

### 2. Tokenizing and Stop Words
Before processing, text is normalized:
- Lowercased
- Expanded contractions
- Removed punctuation

Prompts are split into:
- **Stop Words**: Common words (e.g., "the", "is").
- **Key Words**: Important, lemmatized words.

### 3. The Mesh System
Instead of directly mapping prompts to responses, {Untitled.AI} uses a "mesh" to associate word patterns with potential responses. Each mesh entry contains:
- Stop words and key words from the prompt.
- Responses linked by UUID.

### 4. Querying Responses
When a prompt is received, the mesh is queried and scored based on shared stop and key words. The chatbot discards low-scoring matches and randomly selects from the remaining responses.

### 5. Contextual Precision
{Untitled.AI} improves response accuracy by factoring in the last prompt and response to provide more contextually relevant answers.

## Example Interaction

```plaintext
{Untitled.AI}: 
User:
