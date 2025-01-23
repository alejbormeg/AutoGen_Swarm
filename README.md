🤖 Multi-Agent Financial & News Research Bot

Welcome to the Multi-Agent Financial & News Research Bot repository! This project demonstrates a coordinated multi-agent approach to researching stock market data and news articles, then compiling a final report — all through a conversation-based interface.

Below you’ll find:
	1.	Overview of the use case
	2.	Key features
	3.	Installation & setup
	4.	How to run
	5.	Contributing
	6.	License

🔎 Use Case Overview

In many research or financial analysis scenarios, you have multiple specialized tasks:
	1.	Fetching financial data (e.g., stock price, volume, etc.)
	2.	Gathering relevant news about a company
	3.	Synthesizing all findings into a cohesive report

This repo implements an autonomous team of agents — a Planner, a Financial Analyst, a News Analyst, and a Writer — each handling a specific role. They communicate via a conversation-driven workflow, coordinating tasks to produce a final Markdown report for users.
	•	Planner: Decides what to do and delegates tasks.
	•	Financial Analyst: Fetches stock data and writes partial reports.
	•	News Analyst: Fetches related news articles and writes partial reports.
	•	Writer: Compiles a final Markdown report from the gathered data.

All of this happens interactively using OpenAI’s GPT-based agents and the News/Alpha Vantage APIs!

✨ Key Features
	•	Agent Swarm: Multiple agents, each with a specialized role, communicate via handoffs.
	•	Real-Time Data: Fetches live stock data from Alpha Vantage and recent articles from the News API.
	•	Interactive Console Flow: Runs in a conversational style, prompting the user only when needed.
	•	Report Generation: Automatically writes Markdown reports with timestamps for traceability (saved in a reports directory).

⚙️ Installation & Setup
	1.	Clone the repository:

git clone https://github.com/your-username/your-repo.git
cd your-repo


	2.	Create and activate an isolated environment (recommended). You can use either:
	•	Python venv:

python3 -m venv venv
source venv/bin/activate


	•	Conda:

conda create -n multiagent-env python=3.9
conda activate multiagent-env


	3.	Install dependencies:

pip install -r requirements.txt


	4.	Set up environment variables:
Create a .env file in the same directory with the following variables:

ALPHA_VANTAGE_API_KEY=YOUR_ALPHA_VANTAGE_API_KEY
NEWS_API_KEY=YOUR_NEWS_API_KEY
OPENAI_API_KEY=YOUR_OPENAI_API_KEY

Make sure you sign up and obtain the keys for:
	•	Alpha Vantage for stock data
	•	NewsAPI for news articles
	•	OpenAI for GPT-based chat models

🚀 How to Run
	1.	Ensure your .env file is properly configured with valid API keys.
	2.	Run the script:

python stock_web_search.py


	3.	Enter an initial task when prompted (e.g., “Research Tesla stock”).
	4.	Follow the console prompts. The agents will coordinate, fetch data, and hand off control if they need additional user input.

When the process finishes, you should see a final Markdown report saved under reports/ for each agent’s results.

🤝 Contributing

Contributions are welcome! If you have ideas to improve agent logic, add more tools, or enhance the conversation flow, feel free to:
	1.	Fork this repository
	2.	Create a new branch (git checkout -b feature-your-feature)
	3.	Commit your changes (git commit -m 'Add your feature')
	4.	Push to the branch (git push origin feature-your-feature)
	5.	Open a Pull Request

📝 License

This project is licensed under the MIT License. Feel free to modify and reuse for your own projects.

Enjoy exploring autonomous multi-agent financial research!
If you have any questions, create an issue or submit a pull request.

Happy coding! 🎉
