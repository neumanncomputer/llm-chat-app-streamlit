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

# Azure　の App Serviceへデプロイ

```bash
poetry export -f requirements.txt -o requirements.txt --without-hashes
```
- equirements.txtを読んで pip でパッケージをインストールするセットアップをしてもらう必要があります。この動作は構成で行います。アプケーション設定に`SCM_DO_BUILD_DURING_DEPLOYMENT`というKEYを作り、値にtrueまたは1をセットします。
- 全般設定のスタートアップ コマンドに以下を設定
```bash
python -m streamlit run app.py --server.port 8000 --server.address 0.0.0.0
```
