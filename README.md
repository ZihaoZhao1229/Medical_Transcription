Thinking Process:
Medical texts contain complex and diverse terminology and expressions, and traditional machine learning models may require a lot of task-specific tuning and feature selection to achieve the same results. The comprehension generation, large-scale data processing, and generalization capabilities of LLM are more advantageous for medical texts.

Model selection
The model chosen must have the coverage and applicability of medical knowledge, the Mistral-7B-Instruct-v0.1 model was chosen for its breadth of knowledge as well as its adaptive and flexible nature.
reference：
https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1
https://www.kaggle.com/models/mistral-ai/mistral

Prompt design process:
According to the data, it can be seen that the age information is distributed in different columns, so the recognition is to input the description and translation together into the model
Problems encountered during design:
1. The output of the model contains useless information which leads to redundancy of information, the solution is to use a fixed format to constrain the output of the model.
2treatment model usually outputs only one treatment plan, but the actual treatment information is diverse, the solution is to let the model list all the plans.
“TREATMENT: list the patient's treatments prescripted by a doctor”
In the end, two versions of Prompt were formed:
Version 1 Too many demands on the model result in the model not being able to fulfill all the requirements and some instructions will be ignored Less effective.
Version 2 Simplified dialog to fulfill the main requirements Better results.
