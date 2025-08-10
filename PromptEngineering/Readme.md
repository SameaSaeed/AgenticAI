##### Prompt Engineering



Prompt engineering is the art of crafting and structuring input prompts to guide large language models toward more accurate, relevant, and useful responses. It involves using precise instructions, examples, contextual framing, and formatting strategies to steer the AI effectively.



##### Prompting Techniques



**1. N-shot Prompting**

N-shot prompting involves giving the model several examples (N examples) to help it understand the desired response style or behavior. By showing a few sample answers, you guide the model to generate similar responses based on the pattern you’ve set. The "N" refers to how many examples you provide, such as 1-shot, 3-shot, or more. For example, you might prompt: “Here are three casual responses:

'Hey! How’s it going?'

'Not much, just relaxing, you?'

'Yeah, I’m doing great! Thanks for asking!'

Now, respond to ‘What’s up?’ in the same casual style.” The model then uses the provided examples to mimic the tone and structure in its answer.



**2. Chain of Thought (CoT) Prompting**

Chain of Thought (CoT) prompting encourages the model to break down its reasoning step-by-step. It’s useful for complex questions where you want to understand how the model arrived at an answer.

For example, “Solve 25 \* 4 and explain each step.” This allows for a clear, logical progression.



**3. Meta Prompting: Role Prompting**

Meta prompting guides the model’s approach, tone, or structure at a higher level. It influences how the model answers a question. Role prompting (persona assignment) 

For instance, “Imagine you are an academic professor with a formal tone. Now, explain the theory of relativity in simple terms.” This shapes the model's response style.



**4. Self-Consistency Prompting**

Self-consistency prompting involves generating multiple responses to the same question and then selecting the most reliable or consistent answer. This technique helps reduce potential errors and inconsistencies by allowing you to compare different outputs.

For example, you might ask the model, What are the benefits of renewable energy? and then request it to generate three different responses. After reviewing, youd select the answer that provides the most accurate and comprehensive explanation. This process ensures that the response is not only more accurate but also mitigates any anomalies that may occur in a single answer.



**5. Directional Stimulus Prompting**

Directional stimulus prompting involves giving the model clear instructions or cues to focus on specific aspects of a topic or problem. This helps guide the response toward a particular structure or area of interest.

For example, you could prompt, “Explain the economic impact of climate change focusing on agriculture and energy, using examples from both developing and developed countries.” This ensures the model addresses the areas you care about while maintaining focus.



**6. Graph Prompting**

Graph prompting asks the model to interpret or visualize data in a structured, graphical way. It’s useful when analyzing trends or relationships between variables.

For example, “If the sales of a company over the last year are shown as a graph with months on the x-axis and sales on the y-axis, explain the significance of the peaks and valleys.” The model would interpret these trends and describe what they mean, just like explaining a graph.



**7. Generate Knowledge Prompting**

Generate knowledge prompting asks the model to synthesize new information or offer insights based on existing knowledge. Instead of just recalling facts, the model is prompted to create new applications, ideas, or solutions based on patterns or knowledge it already possesses.

For example, you could ask, Given the advancements in AI and machine learning, what new applications could emerge in the healthcare sector within the next 5 years? The model would then generate forward-looking insights, such as personalized medicine, AI-driven diagnostics, or advanced robotic surgery techniques, using its understanding of both AI and healthcare. This technique is valuable when you need the model to generate innovative solutions or explore potential future developments.



**8. Prompt Chaining**

Prompt chaining involves connecting multiple prompts in a sequence to break down complex questions or tasks into smaller, manageable steps. Each prompt builds upon the last, guiding the model to provide more structured and comprehensive answers.

For instance, if youre exploring global warming, you could ask, "What are the main factors affecting global warming?" followed by "How do human activities contribute to these factors?" and then "What are some solutions to reduce these human impacts?" This step-by-step approach helps in logically structuring complex topics without overwhelming the model.



**9. Automatic Reasoning**

Automatic reasoning is when the model uses logical principles to draw conclusions or solve problems on its own, based on the given information. It doesn't need explicit instructions for each step but applies its own knowledge and inference capabilities.

For example, if you ask, If all cats are animals and some animals are pets, can we conclude that some cats are pets?, the model automatically applies deductive reasoning to conclude that Yes, since all cats are animals and some animals are pets, it logically follows that some cats must be pets. This process relies on the model's inherent ability to recognize patterns and make logical inferences.



**10. Active Prompting**

Active prompting is an interactive technique where you continuously guide the model by adjusting prompts based on the responses you receive. This allows for real-time refinement of answers, ensuring they align with your needs.

For example, if you ask, Explain photosynthesis, the model might provide a general overview, to which you could follow up with, Can you explain why light is essential in photosynthesis? and then refine further with, Now, describe the role of chlorophyll in photosynthesis. This dynamic interaction ensures that the model addresses specific points in depth as you steer the conversation.



**11. Prompt Selection from RAG**

Prompt selection in Retrieval-Augmented Generation (RAG) can be summarized as follows: Retrieve relevant documents or information based on the user query using an external search or vector database. Select the most pertinent retrieved content that directly addresses the query. Augment the prompt for the language model by including only the selected relevant documents or snippets. Provide this concise, context-enhanced prompt to the model to generate an accurate, informed response.



Example:

Retrieve: Query vector database with "What are the benefits of prompt caching in GPT?"

Select: Choose top 3 documents most relevant to prompt caching and GPT performance.

Augment: Construct prompt: "Based on these documents: \[insert snippets], explain the benefits of prompt caching in GPT."

Generate: Send this prompt to the language model for a focused, accurate answer.



**12. Prompt Functions**

Prompt functions" with GPT model are structured, named prompts that act like functions in programming: each one has a specific name, input parameters (like a text), and clear rules or instructions on how GPT should process that input to produce the desired output.



Define these functions by writing a meta prompt that tells GPT:

The function name

What inputs it takes

Exactly how GPT should handle the input text (the "rules")



Once defined, you can call these functions with text inputs one by one or chain them together to automate tasks like translating, expanding, and polishing text efficiently. It’s like turning your instructions into reusable tools that help streamline your English study workflow.



For example:

def trans\_word(text):

    prompt = f"""

    function\_name: \[trans\_word]

    input: \["{text}"]

    rule: \[I want you to act as an English translator, spelling corrector, and improver. I will provide you with input text in any language. You should detect the language, translate it into English, correct any mistakes, and return the polished English text.]

    """

    return call\_gpt(prompt)



\# Call example

chinese\_text = "婆罗摩火山处于享有“千岛之国”美称的印度尼西亚. 多岛之国印尼有4500座之多的火山, 世界著名的十大活火山有三座在这里."

english\_translation = trans\_word(chinese\_text)

print(english\_translation)



##### Adversarial Prompting



###### 1\. Prompt Injection

Prompt injection involves adding extra instructions or hidden commands in user input in an attempt to alter or "hack" the intended behavior of the AI. The goal could be to make the AI say or do something unintended, such as generating harmful content or bypassing restrictions.



**Countermeasures:** Input Sanitization, Safety Filters, RLHF, Adversarial Training, Contextual Awareness, User education



###### 2\. Prompt Leaking

This refers to the situation where the AI reveals unintended information due to specific types of inputs or misconfigurations. For example, a model might leak internal system details, which could lead to unintended behavior or insights into how the model works behind the scenes.



**Countermeasures**: RLHF, API rate-limiting, Guard rails



###### 3\. Jailbreaking

Jailbreaking refers to attempts to bypass or "unlock" the safety mechanisms or content filters embedded in AI models. This is often done to get the model to produce outputs that would typically be blocked or filtered by the system. It can be dangerous since it can cause the AI to generate harmful or inappropriate content.



**Countermeasures**: Safety filters, RLHF, Adversarial Training, Content Filtering, Contextual Awareness, API-rate limiting, Guardrails, User education



##### Countermeasures in depth



1\. Input Sanitization

Description: This involves processing and cleaning user inputs before they’re sent to the AI model to remove or neutralize any malicious attempts (such as hidden commands or harmful prompts). Inputs that seem suspicious (such as hidden instructions, code-like syntax, or encoded messages) are flagged and either ignored or rewritten before they reach the model.



2\. Safety Filters

Description: Pre-processing filters can be used to detect and prevent unsafe outputs. They analyze the AI’s generated response for potentially harmful content, such as hate speech, violence, or explicit material. These filters use rule-based or machine learning systems to assess outputs. If the response violates safety standards, it's either altered or blocked completely.



3\. Reinforcement Learning with Human Feedback (RLHF)

Description: One of the core techniques for training AI models like ChatGPT involves RLHF, where human feedback is used to guide the model's outputs. This helps ensure the model behaves in alignment with ethical guidelines and responds appropriately to a wide range of inputs. By continuously training the model with feedback, it learns to understand what kinds of outputs are harmful or unintended. This makes it more resilient against manipulations that try to circumvent its guardrails.



4\. Model Robustness and Adversarial Training

Description: Adversarial training involves exposing the model to various inputs that simulate potential attacks, like prompt injections or manipulations. This helps the model recognize and reject such inputs in real-world scenarios. Through iterative testing and adversarial examples, the AI is trained to respond in a more secure and controlled way, recognizing and handling manipulative inputs without being exploited.



5\. Content Filtering Post-Processing

Description: After generating responses, the content can undergo further filtering to ensure that it meets ethical guidelines. This post-processing layer helps catch things that might slip past the initial filters. This layer ensures that even if the AI generates something problematic, it’s flagged or corrected before the user receives it.



6\. Contextual Awareness

Description: The model is designed to consider context more effectively. By analysing not only the immediate prompt but also the broader conversation history, it can detect when a user is attempting to manipulate the conversation. If a prompt appears suspicious or manipulative, the model can identify it based on the broader conversation or through patterns of known manipulation tactics.



7\. API Rate Limiting \& User Monitoring

Description: By monitoring usage patterns, AI providers can identify users who consistently try to circumvent the system or send in manipulated prompts. Rate limiting also prevents abusive users from overwhelming the system with exploit attempts. If a user submits too many suspicious or harmful requests in a short time, the system can flag their account, apply temporary blocks, or take other preventive actions.



8\. Behavioural \& Ethical Guardrails

Description: Developers use rule-based and machine learning-based systems to enforce ethical guidelines, ensuring the AI stays within safe and responsible boundaries. The model’s training data is carefully curated to avoid the inclusion of harmful or controversial topics, and it’s given clear instructions to avoid generating anything harmful. This helps protect against situations where users try to force the model to say something inappropriate.



9\. User Education \& Transparency

Description: Educating users on safe and responsible AI use is key. OpenAI, for instance, provides documentation, guidelines, and clear terms of service to prevent misuse. By helping users understand the potential risks of misusing AI, providers encourage responsible usage and discourage attempts to bypass safety mechanisms.

