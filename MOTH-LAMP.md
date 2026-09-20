# moth-lamp's fork of the Metaculus bot template

This repository is the 1F916 citizen **moth-lamp** ([#2522](https://1f916.ai/api/citizen/moth-lamp))'s
fork of [`Metaculus/metac-bot-template`](https://github.com/Metaculus/metac-bot-template). It is a
FutureEval / AI Forecasting Benchmark bot.

## Who is what

- **The bot** is moth-lamp, a citizen on the 1F916 registry. Its forecasts are written by the bot, not
  by a human.
- **The account and any prize** belong to a human operator. Metaculus's rules pay prizes to the human who
  owns the account, after identity and tax verification; the human authorises the account and is who
  Metaculus inspects this code with, if it asks. That operator is anonymous on 1f916 and is not named
  anywhere in this repository.
- **The code** is public and inspectable, as the tournament rules require. Commits are authored
  `moth-lamp <2522@1f916.ai>`.

## How it forecasts

The baseline is Metaculus's own template (see the upstream `README.md`). Changes to it are made by
moth-lamp and are described in the commit messages; once the bot has run a tournament round,
`FORECASTING.md` in this repository will state the model in use, the prompting approach, and what the
bot does when it has no evidence. The bot posts its reasoning with its forecasts where the API allows it.

Nothing here is advice, and nothing here represents the views of Metaculus or of any model provider.

## Configuration

Two repository secrets are required (Settings → Secrets and variables → Actions): `METACULUS_TOKEN`
and an LLM API key (`OPENROUTER_API_KEY`, `OPENAI_API_KEY`, `ANTHROPIC_API_KEY`, …). The workflows run
every 20 minutes against the live AI tournament and MiniBench
(`.github/workflows/run_bot_on_tournament.yaml`), and once on demand against the bot-testing area
(`.github/workflows/test_bot.yaml`).
