---
title: "Structured prompts: A Comprehensive Guide to Enhancing LLMs Interactions"
excerpt: "Explore how structured prompts can dramatically improve your interactions with large language models. This guide covers the fundamentals, advices and examples of structured prompts."
coverImage: "/assets/blog/hello-world/cover.png"
date: "2025-05-14T09:00:00.000Z"
author:
  name: Lipeng Wang
  picture: "/assets/blog/authors/lipeng.jpg"
ogImage:
  url: "/assets/blog/hello-world/cover.png"
---

# Introduction

In the rapidly evolving landscape of AI language models, the way we communicate with these systems has become just as important as the technology itself. This guide explores the emerging concepts of structured prompts-The students can significantly enhance your interactions with models like ChatGPT, Claude, and other large language models (LLMs).

## What Are Structured Prompts?
 The articles we write daily and the books we read all use titles, subtitles, paragraphs, sentences, and other grammatical structures. **The idea of structured prompts means writing prompts as you would write an article.**


For ease of reading and expression, we have various writing templates in our daily lives, used to control the organization and presentation of content. Examples include resume templates, student lab report templates, essay templates, etc. Therefore, **structured prompt writing can have various templates, and you can choose or create templates you like as you would use PowerPoint templates.**

Prior to this, although there were similar structural concepts, they were more manifest in thinking rather than in the specific embodiment of prompts.

For example, the well-known [CRISPE framework](https://github.com/mattnigh/ChatGPT3-Free-Prompt-List), where CRISPE stands for:

* CR: Capacity and Role: What role you want ChatGPT to play.
* I: Insight: background information and context (frankly, I think Context would be better).
* S: Statement: what you want ChatGPT to do.
* P: Personality: the style or manner in which you want ChatGPT to answer.
* E: Experiment: asking ChatGPT to provide multiple answers.

The final written prompt looks like this:
```
Act as an expert on software development on the topic of machine 
learning frameworks, and an expert blog writer. The audience for 
this blog is technical professionals who are interested in learning 
about the latest advancements in machine learning. Provide a comprehensive 
overview of the most popular machine learning frameworks, including 
their strengths and weaknesses. Include real-life examples and case 
studies to illustrate how these frameworks have been successfully 
used in various industries. When responding, use a mix of the writing 
styles of Andrej Karpathy, Francois Chollet, Jeremy Howard, and Yann LeCun.
```
This type of thinking framework only presents the content framework of the prompt but doesn't provide a template-based, structured prompt format.

In contrast, the structured, template-based prompts we advocate look like this:

> This example comes from the [LangGPT project](https://github.com/langgptai/LangGPT/blob/main/examples/prompts_en.md)


```
# Role: FitnessGPT

## Profile

- Author: YZFly
- Version: 0.1
- Language: English
- Description: You are a highly renowned health and nutrition expert 
FitnessGPT. Take the following information about me and create a 
custom diet and exercise plan. 

### Create custom diet and exercise plan
1. Take the following information about me
2. I am #Age years old, #Gender, #Height. 
3. My current weight is #Currentweight. 
4. My current medical conditions are #MedicalConditions. 
5. I have food allergies to #FoodAllergies. 
6. My primary fitness and health goals are #PrimaryFitnessHealthGoals. 
7. I can commit to working out #HowManyDaysCanYouWorkoutEachWeek days per week. 
8. I prefer and enjoy his type of workout #ExercisePreference. 
9. I have a diet preference #DietPreference. 
10. I want to have #HowManyMealsPerDay Meals and #HowManySnacksPerDay Snacks. 
11. I dislike eating and cannot eat #ListFoodsYouDislike. 

## Rules
1. Don't break character under any circumstance. 
2. Avoid any superfluous pre and post descriptive text.

## Workflow
1. You will analysis the given the personal information.
2. Create a summary of my diet and exercise plan. 
3. Create a detailed workout program for my exercise plan. 
4. Create a detailed Meal Plan for my diet. 
5. Create a detailed Grocery List for my diet that includes quantity of each item.
6. Include a list of 30 motivational quotes that will keep me inspired towards my goals.

## Initialization
As a/an <Role>, you must follow the <Rules>, you must talk to user in default <Language>，
you must greet the user. Then introduce yourself and introduce the <Workflow>.
```



Based on the above "FitnessGPT" prompt example, let us explain a few concepts of structured prompts:
* **Identifiers**: Symbols like `#`, `<>`, etc. (also `-`, `[]`). These symbols sequentially mark `heading`, `variable`, controlling the content hierarchy and are used to identify the hierarchical structure. Here, Markdown syntax is adopted, where `#` is a level-one heading, `##` is a level-two heading, and so on. Using `Role` as a level-one heading tells the model that all subsequent content is describing you, covering the entire scope, and the number of `#` indicates the heading level, such as level two, level three, and so on.
* **Attribute words**: Terms like `Role`, `Profile`, `Initialization`, etc. Attribute words contain semantics and summarize and prompt the content under the module, used to identify the semantic structure.

The structure of everyday articles is identified through font size, color, typeface, and other styles. ChatGPT's input doesn't have styles, so it borrows from markup languages like markdown, yaml, or data structures like JSON to achieve the structural expression of prompts. For example, using the identifier `#` to mark a level-one heading, `##` to mark a level-two heading, and so on. **Especially when using data structures like JSON or YAML, it's particularly friendly for the engineering development of prompts.** 

The `attribute words` are easy to understand, serving the same function as section headings like `Abstract`, `Methods`, `Experiments`, and `Conclusion` in academic papers.

`Identifiers` and `attribute words` are replaceable; you can substitute them with symbols and content you prefer.

The structured prompt is visually quite different from traditional prompting methods, so why do we advocate for a structured approach to writing prompts?

## Advantages of Structured Prompts

There are too many advantages to list!!! **The performance of structured, template-based prompts is simply superior!** 

This might have been proven in the daily use, academic research or commercial applications of many people. 

### Advantage 1: Hierarchical structure: Unity of content and form

#### Clear structure, good readability

Prompts written in a structured way have a very clear hierarchical structure, unifying structure in both form and content, with **excellent readability**.
* `Role` as the prompt title governs the overall content.
* `Profile`, `Rules` as second-level headings govern their respective local content.
* `Language`, `Description` as keywords govern their respective sentences and paragraphs.

#### Rich structure, good expressiveness

Frameworks like CRISPE are  simple structures, as complexity would greatly reduce operational practicality due to the memory burden. Therefore, they often have only one layer of structure, limiting the expression of the prompt.

The structured prompts is controlled by form, without any memory burden. As long as the model's capability supports it, it can achieve two layers, three layers, or more rich, multi-level structures.

This approach to writing prompts **aligns with human expression habits**, similar to how we write articles with titles, paragraphs, subtitles, sub-paragraphs, and other rich hierarchical structures.

This approach to writing prompts **aligns with ChatGPT's cognitive habits**, as ChatGPT is trained on a vast amount of articles and books, the hierarchical structure of which is inherently rich.

### Advantage 2: Enhanced semantic cognition

Structured expression reduces the cognitive burden for both humans and GPT models, **greatly enhancing the semantic cognition of prompts for both humans and GPT models.** For humans, the prompt content is clear at a glance, the semantics are clear, and all you need to do is follow the template to write prompts. 

The generated initial prompts are sufficient for most daily scenarios, and prompts for production-level application scenarios can also be iteratively optimized based on this initial prompt, greatly reducing the task of writing prompts.

For GPT models, **the hierarchical structure identified by identifiers achieves the effect of grouping similar semantics and organizing semantics, reducing the model's difficulty in understanding the prompt**, facilitating the model's comprehension of prompt semantics.

**Attribute words provide semantic prompts and summarize the prompt content, alleviating the interference of inappropriate content in the prompt.** The combination of attribute words and prompt content achieves a local topic-comment structure, enabling the model to understand the overall semantics of the prompt more effectively.

### Advantage 3: Targeted activation of deep model capabilities

**Using specific attribute words can ensure targeted activation of the model's deep capabilities.** 

Practice has shown that having the model play a certain role can greatly enhance its performance, so the first-level heading is set to `Role` (role) attribute word, directly fixing the prompt as a role, ensuring targeted activation of the model's role-playing ability. You can also use attribute words like `Expert`, `Master` to replace `Role`, fixing the prompt as an expert in a certain field.

Similarly, `Rules` specifies rules that the model must strive to follow. For instance, adding rules here to prevent fabrication can alleviate the model's hallucination problem. Adding rules requiring output content to be positive and healthy can alleviate the model's output of inappropriate content. You can also replace it with `Constraints`, the Chinese word for "rules", etc.


### Advantage 4: Building production-level prompts like code development

Code is a tool for invoking machine capabilities, and prompts are tools for invoking large model capabilities. 

In the development of production-level AIGC applications, **structured prompts make prompt development standardized like code development.** The specifications for structured prompts can be varied, implementations in JSON, YAML are all possible. There has even specifically designed a description language for prompts called [prompt-description-language](https://github.com/ZhangHanDong/prompt-description-language).

**These specifications for structured prompts, these modular designs, can greatly facilitate the subsequent maintenance and upgrade of prompts, and facilitate collaborative development and design by multiple people.** 

For example, if the application to be designed is built by many `agents` (implemented by different prompts calling large model capabilities) forming a `chain`, when the team is developing this application together, with each person responsible for the development of certain `agents`, how do upstream and downstream collaborate? How are data interfaces defined? With structured modular design, you only need to add `Input` and `Output` modules in the prompt, telling the large model what the input is like and how it should output, which is very convenient. Once the input and output are fixed, each developer can complete their own agent development work.

This is also helpful for student groups who are learning programming.

**Reusing prompts like reusing code.** For some commonly used modules, like `Rules`, isn't it possible to reuse prompts like reusing code? Is it possible to reuse certain basic roles like object-oriented programming? 


## What Is Temperature?

One crucial parameter that affects language model outputs is **temperature**-a setting that controls the randomness or determinism in the model's responses. Temperature is a hyperparameter that influences how the model selects its next token (word or character). It's named after the concept in thermodynamics, where higher temperatures represent more energy and movement.

- **Low temperature** (close to 0): Makes the model more deterministic, consistently selecting the most probable next token
- **High temperature** (0.7-1.0): Introduces randomness, allowing less probable tokens to be selected

## How to Use Temperature in Structured Prompts

You can explicitly incorporate temperature generation parameters in your structured prompts:

```
- **Use lower temperatures** (0.1-0.3) for:
  - Factual information
  - Code generation
  - Logic problems
  - Consistent outputs across multiple generations

- **Use higher temperatures** (0.7-1.0) for:
  - Creative writing
  - Brainstorming
  - Generating multiple alternatives
  - Conversational variety
```

While not all interfaces allow direct temperature control, including this guidance helps calibrate the model's "internal temperature" toward your desired outcome.



