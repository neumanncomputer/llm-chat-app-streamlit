# Streamlit で LLM chat app をつくる

[Build a basic LLM chat app - Streamlit Docs](https://docs.streamlit.io/develop/tutorials/llms/build-conversational-apps)

# Requirement

- Python 3.11
- pyenv環境
- poetry 環境

```bash
pyenv local
poetry install
```

# Usage

- .streamlit/secrets.toml に OPENAI_API_KEY を定義

```bash
poetry shell
streamlit run app.py
```
