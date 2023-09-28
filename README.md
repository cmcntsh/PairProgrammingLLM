# Pair Programming with LLM

This is a tutorial at https://learn.deeplearning.ai/pair-programming-llm/lesson/1/introduction .

## Get an API Key

* Go to https://developers.generativeai.google/
* Sign in with Google ID
* Scroll to bottom of page and click on Explore the API button under Meet the PaLM API heading.
* Click on Get Your API Key button.
* Agree to the Terms of Service.
* Click Create API key in new project button.
* Copy the key to somewhere secure. (You usually can't get the key again later. DON'T PUBLISH IT ANYWHERE PUBLIC!)
* How to use the API key in Google Colab https://stackoverflow.com/questions/67087130/setting-an-api-key-in-google-colab
* Another option for API keys for Jupyter Notebooks (including Google Colab) https://towardsdatascience.com/store-api-credentials-easily-and-securely-in-jupyter-notebooks-50411e98e81c

## Notes

* The code `from utils import get_api_key` will give you an error on Google Colab. The utils mentioned in that code block was something supplied for the tutorial and contains functions not available in the regular Python utils package. You can get your own API key as noted above, then you need to insert that key directly in the `palm.configure()` code. Where it says `api_key=get_api_key()`, you need to replace `get_api_key()` with the API key you obtain from https://developers.generativeai.google/.

## Useful Prompt Suggestions in the Tutorials

* Getting Started tutorial
  * `prompt = "Show me how to xxxx"` gives text explanations and examples
  * `prompt = "write code to xxxx"` provides code with less explanation
* Using a String Template tutorial
  * `prompt_template = """ {priming} {question} {decorator} Your solution: """`
  * `priming_text = "You are an expert at writing clear, concise, Python code."`
  * `question = "create a doubly linked list"`
  * Decorator option `decorator = "Work through it step by step, and show your work. One step per line."`
  * Decorator option `decorator = "Insert comments for each line of code."`
* Pair Programming Scenarios tutorial
  * Improving code
    * `prompt_template = """ I don't think this code is the best way to do it in Python, can you help me? {question} Please explain, in detail, what you did to improve it. """`
  * Ask for multiple ways of rewriting code
    * `prompt_template = """ I don't think this code is the best way to do it in Python, can you help me? {question} Please explore multiple ways of solving the problem, and explain each. """`
  * Ask the model to recommend the most "Pythonic" way to do something
    * `prompt_template = """ I don't think this code is the best way to do it in Python, can you help me? {question} Please explore multiple ways of solving the problem, and tell me which is the most Pythonic """`
  * Simplify code
    * `prompt_template = """ Can you please simplify this code for a linked list in Python? {question} Explain in detail what you did to modify it, and why. """`
    * `prompt_template = """ Can you please simplify this code for a linked list in Python? \n You are an expert in Pythonic code. {question} Please comment each line in detail, \n and explain in detail what you did to modify it, and why. """`
  * Write test cases
    * `prompt_template = """ Can you please create test cases in code for this Python code? {question} Explain in detail what these test cases are designed to achieve. """`
  * Make code more efficient
    * `prompt_template = """ Can you please make this code more efficient? {question} Explain in detail what you changed and why. """`
  * Debug your code
    * `prompt_template = """ Can you please help me to debug this code? {question} Explain in detail what you found and why it was a bug. """`
  * ALWAYS MAKE SURE THE CODE A MODEL PROVIDES ACTUALLY RUNS!
* Technical Debt tutorial
  * Explain how code works
    * `prompt_template = """ Can you please explain how this code works? {question} Use a lot of detail and make it as clear as possible. """`
  * Ask an LLM to document a complex code base
    * `prompt_template = """ Please write technical documentation for this code and \n make it easy for a non swift developer to understand: {question} Output the results in markdown """`
