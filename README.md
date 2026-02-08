# Streamlit で LLM chat app をつくる

[Build a basic LLM chat app - Streamlit Docs](https://docs.streamlit.io/develop/tutorials/llms/build-conversational-apps)を参考に作成

## Requirement

- [uv](https://docs.astral.sh/uv/)
- ([Ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff))

## Usage

1. .streamlit/secrets.toml に OPENAI_API_KEY を定義
2. 以下のコマンドを実行

   ```bash
   uv run streamlit run app.py
   ```

## Azure　の App Serviceへデプロイ

1. 以下のコマンドを実行

   ```bash
   uv run pip-audit # 脆弱性を確認
   uv pip compile pyproject.toml -o requirements.txt
   ```

2. 環境変数に`SCM_DO_BUILD_DURING_DEPLOYMENT`というKEYを作り、値にtrueまたは1をセット

3. 全般設定のスタートアップ コマンドに以下を設定

   ```bash
   python -m streamlit run app.py --server.port 8000 --server.address 0.0.0.0
   ```
