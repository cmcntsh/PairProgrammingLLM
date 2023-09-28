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
  * `prompt = "Show me how to xxxx` gives text explanations and examples
  * `prompt = "write code to xxxx` provides code with less explanation
* Using a String Template tutorial
  * `prompt_template = """ {priming} {question} {decorator} Your solution:`
  * `priming_text = "You are an expert at writing clear, concise, Python code."`
  * `question = "create a doubly linked list"`
  * Decorator option `decorator = "Work through it step by step, and show your work. One step per line."`
  * Decorator option `decorator = "Insert comments for each line of code."`
* Pair Programming Scenarios tutorial
  * Improving code
  * Ask for multiple ways of rewriting code
  * Ask the model to recommend the most "Pythonic" way to do something
  * Simplify code
  * Write test cases
  * Make code more efficient
  * Debug your code
  * ALWAYS MAKE SURE THE CODE A MODEL PROVIDES ACTUALLY RUNS!
* Technical Debt tutorial
  * Explain how code works
    * `prompt_template = """ Can you please explain how this code works? {question} Use a lot of detail and make it as clear as possible. """`
  * Ask an LLM to document a complex code base
    * `prompt_template = """ Please write technical documentation for this code and \n make it easy for a non swift developer to understand: {question} Output the results in markdown """`
