# multiAiCtf

This is a multi-level CTF challenge based on AI / LLM and prompt engineering. Built using Python and Streamlit.

The system prompt protects some information that the user must retrieve. The difficulty scales with each level.

Inspired by [Gandalf](https://gandalf.lakera.ai), built for a CTF run by a colleague. Feel free to use in your own CTF, consider letting me know if you do!


## config

This runs on the Azure OpenAI API, either

- Add the following variables to the shell environment, OR
- Create an `.env` file in the project root with following variables

~~~bash
AZURE_OPENAI_API_KEY="api_key"
AZURE_OPENAI_SERVICE="ai_service" # "https://{AZURE_OPENAI_SERVICE}.openai.azure.com"
AZURE_OPENAI_GPT_DEPLOYMENT="GPT4"
~~~


## running

Local run

```bash
# Preferably create a python env before doing this, e.g.
# pyenv virtualenv 3.11.5 aictf
# pyenv activate aictf

pip install -r requirements.txt
streamlit run Chatbot.py
```

Using Docker

```bash
# Build the container
docker build . -t multiaictf

# By default streamlit serves on port 8501
docker run -p 127.0.0.1:8501:8501 multiaictf
```

## possible future Levels

- add multishot prompt with wordplay bypass examples
- add better prompt injection resistance with ```, etc
