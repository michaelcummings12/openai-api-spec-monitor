# OpenAI API Spec Monitor

A GitHub Action that monitors the [OpenAI API Specification](https://app.stainless.com/api/spec/documented/openai/openapi.documented.yml) for changes. When a change is detected, the diff is analyzed using AI and a PR is created. The PR is automatically merged.

## Community

Join our [Discord Server](https://discord.gg/CcbtSc25) to stay updated! The bot sends notifications to the [#openai-ai-spec-monitor](https://discord.com/channels/1463555674431684630/1463557477122703424) channel.

## How It Works

1.  Downloads the latest [OpenAI spec](https://app.stainless.com/api/spec/documented/openai/openapi.documented.yml).
2.  Compares the downloaded spec with the spec cached in the repository.
3.  If changes are detected, a summary is generated with AI based on the diff.
4.  A new PR is created using the generated summary.
5.  The PR is automatically merged.

## Features

- ⏰ Runs hourly to check for spec changes.
- ✨ Creates and merges a PR with an AI-generated summary of changes.
- 🔔 Sends a notification to a Discord channel.

## Setup

### Prerequisites

- Discord Webhook URL.
- Vercel AI Gateway API Key.

### Installation

1.  Clone/Fork this repository.
2.  Configure Secrets:
    - Go to `Settings` > `Secrets and variables` > `Actions`.
    - Add a new repository secret named `DISCORD_WEBHOOK_URL` with your Discord webhook URL.
    - Add a new repository secret named `AI_GATEWAY_API_KEY` with your Vercel AI Gateway API key.
3.  Permissions:
    - Ensure your GitHub Action has Read and Write permissions.
    - Go to `Settings` > `Actions` > `General` > `Workflow permissions`.
    - Select "Read and write permissions".
    - Check "Allow GitHub Actions to create and approve pull requests".

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) for details.
