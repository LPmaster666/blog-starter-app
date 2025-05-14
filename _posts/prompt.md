---
title: "How to Create High-Quality Prompts"
excerpt: "This guide helps you create high-quality prompts for large language models, using diagrams. It coveres prompt formats, cost control, few-shot and in-context learning skills, and more."
coverImage: "/assets/blog/prompt/cover.png"
date: "2025-05-13T09:00:00.000Z"
author:
  name: "Lipeng Wang"
  picture: "/assets/blog/authors/lp.jpg"
ogImage:
  url: "/assets/blog/prompt/cover.png"
---

## How Do Large Language Models Predict the Next Word?


* Dataset Examples: Using translation as an example, question-answer pairs forming conversations, and character-by-character reasoning training.
* Role of Prompt Words: To guide the large model to "spit out" the next word (token) with the "highest probability match" from the training data. Therefore, good prompt words can lead to good responses; ordinary prompt words can only lead to mediocre responses.

![How Do Large Language Models Predict the Next Word](/assets/blog/prompt/1.png)



## Finding "Golden Words" in Data

The golden words are embedded in the training data, which can guide the LLMs to achieve a higher level.

The golden words are not as good as more superimposed words, but should be considered for specific scenarios.

The main scenarios:

### Positive Guidance
"Excellent", "perfect".

Instead of "bad", "awful".

> This referemce comes from the [https://arxiv.org/pdf/2307.11760](https://arxiv.org/pdf/2307.11760)

![Positive Guidance](/assets/blog/prompt/2.png)
### Reduce negativity
"Keep it simple", "Keep it clear".

Instead of "less complex" and "less ambiguous".

![Reduce negativity](/assets/blog/prompt/3.png)

### Step-by-Step Thinking
"Think step by step"

> This referemce comes from the [https://arxiv.org/pdf/2205.11916](https://arxiv.org/pdf/2205.11916)

![Step-by-Step Thinking](/assets/blog/prompt/4.png)

### Emotional Stimulus
"I have no fingers..."
"If you can not finish..., I will die."

> This referemce comes from the [https://arxiv.org/pdf/2307.11760](https://arxiv.org/pdf/2307.11760)

![Emotional Stimulus](/assets/blog/prompt/5.png)

## Prompt Formats

The meaning of prompt formats is not about how easy they are for humans to understand, but about how easy they are for machines to process:

**Regular Format:**  
Natural text + pseudo code, for example, wrapping content with {} or triple backticks```.

**Dataset-Friendly Formats:**  
- GPT prefers: YAML, Markdown format  
- Claude prefers: XML format  
- Gemini prefers: JSON format  

> This referemce comes from the [https://arxiv.org/abs/2408.02442](https://arxiv.org/abs/2408.02442)

## Prompt Content

Creating a prompt is like explaining a knowledge point to a distracted middle school student. 

Three principles: Clarity (mutual understanding) + Constraints (boundaries) + Guidance (encourage innovation)


### ✨General Tips
- Use "User" instead of "I" to avoid confusion
- Present important information upfront (role, goal, context, constraints); reference info at the end (background, appointment, reference)
- Provide specific details, such as time, place, related people or events, to reduce ambiguity
- Avoid overly general content; copy the original text if needed
- For clear answers, specify the question type, e.g., "What is quantum entanglement?" For detailed analysis, specify, e.g., "Explain quantum entanglement"
- No need to use polite words like "please" and "thank you" 

### 👨‍🏫Simple and Understandable Roles
For example: You are a Stanford student, skilled at writing top-level academic papers in English, especially in social science and psychology.

- Avoid too many overlapping roles; if needed, use new model prompts

Tips: Sometimes giving the AI a personality is more effective
- You are Steve Jobs, with a spirit of perfectionism, passionate about product details, and persuasive in speech
- You are Musk, a creative thinker, who likes to challenge traditions and is keen on future technology

### 🎯Clear and Specific Goals
For example: Write an article about "how to improve employee productivity".
- Can include user intent: Write an article about "how to improve employee productivity" for publication in Nature or Science
- Can include audience: Write an article about "how to improve employee productivity" for business managers (or elementary students)

### 🔊Standardize LLM Cognition
- **Attentions:** Highlight key points. E.g.: "Pay special attention to the academic and professional aspects of the article"
- **Background:** Provide background and context. E.g.: "I don't know how to code in Python, you need to explain it to me"
- **Skills:** Specify required skills. E.g.: "You need to have experience writing sci-fi novels"
- **Constraints:** Specify rules and boundaries. E.g.: "The article must not exceed 5000 words"

### ☂️Guide LLM Behavior
- **Workflow:** Specify workflow and steps. E.g.: "First conduct market research, then formulate a plan, and finally evaluate feasibility"
- **Initialization:** Specify initial tasks and preparations. E.g.: "Please confirm the specific needs of the user"
- **Output Format:** Specify output format and requirements. E.g.: "Please use Markdown format and add appropriate headings"

## Token and Cost Control

"Tokenization" is not equal across languages:

For English, a single word is often treated as one token. However, in other languages, the same information may require more tokens to represent.

![Token and Cost Control](/assets/blog/prompt/6.png)
> The same meaning in different languages may require a different number of tokens, which affects cost and model performance.

## Two Key Skills: Few Shots Learning

Few shots is a prompting method that guides AI to understand tasks by providing a small number of examples.

By showing 2-3 specific input-output examples, you help the AI better understand the requirements and output format.

- Examples should be representative
- Example difficulty should progress from easy to hard
- Example format should be consistent and clear to enhance model understanding

> This referemce comes from the [https://arxiv.org/pdf/1904.05046](https://arxiv.org/pdf/1904.05046)

## Two Key Skills: In Context Learning

In Context Learning is a prompting method that guides AI to understand tasks by providing contextual information.

By showing a series of related input-output examples, you help the AI better understand the requirements and output format.

- Directly provide standard Q&A in the context
- Directly provide partial answers in the context

**Example 1: Direct Q&A**

Please answer the following math reasoning questions:

Q: If you have 12 candies and give 4 to your friend, how many do you have left?

A: The answer is 8.

Q: If a rectangle has a length of 6 meters and a width of 3 meters, what is its perimeter?

A: The answer is 18 meters.

**Example 2: Partial Answers in Context**

- Please use academic language to write a paragraph about the importance of system prompts in student diagram models.
- Note: In the process of creating text and diagrams on large language model platforms, system prompts are often added to ensure diversity.

> This referemce comes from the [https://arxiv.org/abs/2202.12837](https://arxiv.org/abs/2202.12837)





