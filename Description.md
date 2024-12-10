# Final Assignment Guidelines


## Introduction

You will complete a final assignment that represents a significant implementation and/or application of Gen AI techniques. Here’s what to expect:

- You must work on this assignment alone.  There is NO group work.
- We will provide a notebook with some partially working systems
- We will provide a scenario for the system and its users
- We will provide a set of documents that you must use in the system
- You cannot add any additional documents
- We will provide a set of validation question/answer pairs

Overall, the goals of this assignment are for you to:


* Implement a RAG system using LangChain and the LLMs we specify. You can extend starter architecture that we provide a bit to address some of the common failure points in RAG deployments. (See Week 9 Lecture slides page 57, or “Seven Failure Points When Engineering a Retrieval Augmented Generation System”, [https://arxiv.org/pdf/2401.05856](https://arxiv.org/pdf/2401.05856); page 3)
* Please stay within the boundaries of LangChain, the LLMs, the embedding models, and the vector database we specify, and do not do original research. (The focus of a PoC, which this assignment aims to emulate, would be to test established approaches, not to try new ones.)
* Be able to quantitatively evaluate the performance of your model
* Be able to formulate metric(s) - that you choose! - as you evaluate to what degree your system replicates gold answers (labeled data) that we will provide.
* Try out various hyper-parameters and settings to see which configuration works the best (given your chosen metric(s)). Do NOT try a grid search. (It is much more important to develop an intuition as to which parameters matter in which way.)
* Write a comprehensive evaluation (‘the report’, see [ReportOutline.md](ReportOutline.md)), which also includes risks and limitations and a lot more. The audience of this evaluation/report are the stakeholders of the PoC, who would make the decision to go ahead with the RAG implementation or not. 



RULES:

* You can only use the language models specified here (Mistral and Cohere) as the LLM in your chain.  You may use Llama 3.1 or 3.2 or Qwen 2 or Gemma 2 in other capacities.
* You can only use the embedding models we specify
* You can only use the documents we provide. And they all must be retrievable from your vector store (which we will specify)
* IF you use less than the 75 gold answers we supply, you must justify your subset - how did you pick them? Apart from the provided specifications, some of the things you can freely experiment with include prompts, chunk sizes, LLM parameters, architecture, etc.
* You must however provide one run on all 75 examples for your best 3 models/model configuration (along with the corresponding metrics, of course.)


As context, the overall scenario for this assignment is as follows:

You work at a tech company that is looking for new ways to organize their search and question answering capabilities to accelerate both engineering activity and the marketing team. The company also wants to roll out new GenAI-based products, so a lot of the questions will center around Generative AI and LLM concepts. The company has about 300 engineers and a marketing staff of 40. Product releases are done quarterly.

Your role is to implement and conduct a (mini-)POC helping the company to evaluate RAG capabilities for the improvement of their document search (and corresponding question answering), supporting particularly the engineering and marketing organizations. You will receive a gold dataset with 'good' responses to questions from marketing and engineering teams. You need to develop a plan that helps you complete a RAG system within the constraints of the POC. Your answers must work for each of the two groups of users -- engineers and marketing managers. You will need to develop a plan to evaluate how well your RAG system performs relative to the gold data we provide. You will need to decide which metrics you want to combine to effectively measure how well your model is working.  You will need to experiment with the tunable hyperparameters of the setup (LLM, chunking, embeddings, ...) for your iterations.


You will need to write up your findings as a 4 page report following [the outline we provide](ReportOutline.md).

(Also see instructions throughout the notebook.)



NOTES:

* The Open Source Model is not trained for safety. So unsafe answers could be returned.

## Cohere

If you do not already have a Cohere account, you will need to create one in order to get an API key.  You will not be able to complete the assignment without it.  Go to [cohere.com](https://dashboard.cohere.com).  Sign up for an account using your personal email address **NOT** your @berkeley.edu email account. Once you have signed up, login to your account and go to the dashboard.  Over in the left hand nav bar is an item 'API Keys.' Click on it and you will see an area on screen called Trial Keys.  You will need to create a "new trial key" for yourself. When you have that trial key, copy it and store a copy somewhere you can retrieve it (never in the open in a notebook).  You'll need to enter that key as a secret in the Google notebook associated with `COHERE_API_KEY.`  (See the ‘Secrets’ icon in the colab again, **DO NOT PRINT IT OUT IN THE NOTEBOOK!**)

Cohere’s Trial Key is free.  However, be aware of the constraints and use the resource wisely.  Check the [limits on use of the API](https://docs.cohere.com/docs/rate-limits).  You are responsible for staying within those limits. For example, the Trial Key permits only 1,000 API calls per month. So you need to either plan for that,  or you can pay to upgrade your key.


## Assignment Grading
The final grade for this assignment consists of the following components:

- [20%] Implementation and Architecture of Model

- [15%] Poor Man’s Evaluation Strategy

- [20%] Experimentation

- [03%] Three Specific Queries Test

- [05%] Five Additional Questions

- [37%] POC Report


### Our Expectations of You

As a student in a graduate level course, you are responsible for seeking out help when your project is stuck.  There is significant support available if you seek it out.  Do not wait for us to provide feedback on deliverables to take action.  If you're looking for a formal way to seek this help, skip down to the Milestone section.


### Rubric Dimensions

Each of the following dimensions will be considered while grading.  An assignment significantly lacking in any dimension will receive a considerably lower grade.  Each dimension is illustrated by several bullet points.

Implementation and Architecture of Model (20%):
- A clearly functioning model that is able to address the problem you are trying to solve  (which should be the one we were giving...).


Poor Man’s Evaluation Strategy (15%):
- Suitability and thoughtfulness of your approach to the problem.
- "How will I know when my project is successful?", usually in the form of an evaluation metric.
- suitability of the metrics are you using, and how you combine them


Experimentation (20%):
- How many of the possible tuning parameters did you use?
- How meaningful were the various run comparisons?
- How much analysis did you do to drive your experimentation?


Three Specific Questions (03%):
- How well do your answers score against ours?
- More importantly, how reasonable are your assessments?


Five Additional Questions (05%):
- How thoughtful and incisive are your answers?


POC Report (37%):
- Primarily:
  - Succinct, interesting presentation explaining the above.
  - Is your paper well organized?
  - Suitability of the report to guide the organization to a decision
  - Suitability of the report to articulate the limitations and opportunities of the RAG approach
- Table stakes:
  - Did you run a spell check before submitting?
  - Did you proof read it?



## Final Submission

This will be a final report on your POC following the [outline we provide](ReportOutline.md). Aim for 4-5 pages in length with the following sections:

- **Executive Summary** (quick summary of your report)
- **Introduction** (overall system description)
- **Key Findings** (five key findings)
- **Methodology** (implementation and evaluation approach)
- **Results and Findings** (challenges and limitations)


Please submit your PDF report, your notebook (*complete with outputs of running*), and your answers file to your classroom GitHub repository using the submit.sh script.

**And remember: for many aspects there is no right or wrong answer! Most important are reasonable, clearly-thought-out approaches!**
