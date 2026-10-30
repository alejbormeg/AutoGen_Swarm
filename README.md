# AutoGen Swarm: financial and news research

A small experiment with the AutoGen `Swarm` team pattern. Four agents
pass control to each other through handoffs to research a company and
write a Markdown report.

| Agent | Role | Tools |
| --- | --- | --- |
| `planner` | Splits the task and hands off to one agent at a time, or back to the user | — |
| `financial_analyst` | Fetches a stock quote and writes its findings | Alpha Vantage `GLOBAL_QUOTE`, `write_report` |
| `news_analyst` | Fetches recent news about the company and writes its findings | NewsAPI, `write_report` |
| `writer` | Compiles the final report | `write_report` |

All four agents use `gpt-4o`. Each one saves its Markdown output to
`reports/<agent_name>/`. The run stops when an agent hands off to the
user or someone says `TERMINATE`.

Everything lives in a single script, [`stock_web_search.py`](stock_web_search.py).

## Run it

You need API keys for OpenAI, [Alpha Vantage](https://www.alphavantage.co/)
and [NewsAPI](https://newsapi.org/).

```bash
git clone https://github.com/alejbormeg/AutoGen_Swarm.git
cd AutoGen_Swarm
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env_template .env   # then fill in the three keys
python stock_web_search.py
```

Type a task such as `Research Tesla stock` and follow the console. When
the swarm finishes, the reports are in `reports/`.

## Status

Experiment, not maintained. It uses the `autogen-agentchat` and
`autogen-ext` packages without pinned versions, so newer releases may
break it.
