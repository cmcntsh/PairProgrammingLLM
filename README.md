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
