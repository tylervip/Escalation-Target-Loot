# Escalation Target Loot

Daily The Division 2 Escalation scraper that pulls structured data from the event index JSON and posts a Discord embed.

## What it does

- Pulls Escalation data from https://hi-dep.github.io/division2/data/event/index.json.
- Sends Escalation-only output with:
	- Week of / Target Loot Date
	- Escalation Target Loot table
	- Escalation Requisition Vendor table
- Sends a structured Discord embed to your webhook.
- Runs automatically every day at 17:05 UTC via GitHub Actions.
- Supports manual runs from GitHub Actions.

## Files

- division2_daily.py: scraper and Discord webhook sender.
- requirements.txt: Python dependencies.
- .github/workflows/division2-daily.yml: scheduled workflow.

## Local usage

1. Install dependencies:

	pip install -r requirements.txt

2. Set your webhook:

	export DISCORD_WEBHOOK_URL="YOUR_WEBHOOK_HERE"

3. Run:

	python division2_daily.py

## GitHub setup

1. Push these files to your repository.
2. Open Settings -> Secrets and variables -> Actions.
3. Add repository secret DISCORD_WEBHOOK_URL.
4. Open Actions and run Division 2 Daily Reset once to verify.

## Security

Do not hardcode your webhook URL in source files. Keep it in the DISCORD_WEBHOOK_URL repository secret.
