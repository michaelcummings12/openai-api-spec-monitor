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
    - Add a new repository secret named `GH_APP_ID` with your GitHub App ID.
    - Add a new repository secret named `GH_APP_PRIVATE_KEY` with the content of the `.pem` file you downloaded.

### Creating the GitHub App

> A GitHub App is required to bypass branch protection rules (e.g., mandatory reviews) and auto-merge PRs.

1.  Go to [Developer Settings](https://github.com/settings/apps) and click **New GitHub App**.
2.  Set the name (e.g., `OpenAI API Spec Monitor Bot`) and homepage URL.
3.  Uncheck "Active" under **Webhook**.
4.  **Permissions**:
    - Repository permissions > **Contents**: Read and Write
    - Repository permissions> **Pull requests**: Read and Write
5.  Create the App.
6.  Note the **App ID** (use for `GH_APP_ID`).
7.  Generate a **Private Key** and download the `.pem` file (use content for `GH_APP_PRIVATE_KEY`).
8.  Install the App on your repository: **Install App** -> Select your account -> Select this repository.
9.  Permissions:
    - Go to `Settings` > `Actions` > `General` > `Workflow permissions`.
    - Select "Read and write permissions".

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) for details.
