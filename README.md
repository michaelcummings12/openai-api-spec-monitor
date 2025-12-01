# OpenAI API Spec Monitor

A bot that runs as a GitHub Action to monitor the [OpenAI API Specification](https://app.stainless.com/api/spec/documented/openai/openapi.documented.yml) for changes. When a change is detected, it analyzes the diff using AI and creates a Pull Request with a semantic title and detailed description.

## How It Works

1.  Downloads the latest `openapi.documented.yml` from Stainless.
2.  Compares the downloaded spec with the cached version in the repository.
3.  If changes are detected, it sends the git diff to OpenAI (via Vercel AI SDK) to generate a summary.
4.  A PR is created with the AI-generated title and description.
5.  The PR is automatically merged (if enabled).

## Setup

### Prerequisites

- A GitHub repository.
- An OpenAI API Key.

### Installation

1.  Clone/Fork this repository.
2.  Configure Secrets:
    - Go to `Settings` > `Secrets and variables` > `Actions`.
    - Add a new repository secret named `OPENAI_API_KEY` with your OpenAI API key.
3.  Permissions:
    - Ensure your GitHub Action has Read and Write permissions.
    - Go to `Settings` > `Actions` > `General` > `Workflow permissions`.
    - Select "Read and write permissions".
    - Check "Allow GitHub Actions to create and approve pull requests".

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
