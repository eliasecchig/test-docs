# CLI Commands

The Agent Starter Pack provides CLI commands to help you create and manage AI agent projects.

## Create Command

The `create` command helps you create new GCP-based AI agent projects from templates.

```bash
agent-starter-pack create PROJECT_NAME [OPTIONS]
```

### Arguments

- `PROJECT_NAME`: Name of the project to create

### Options

The following options will be prompted interactively if not provided:
- `--agent`, `-a`: Agent name or number to use
- `--deployment-target`, `-d`: Deployment target (`agent_engine` or `cloud_run`) 
- `--gcp-account`: GCP service account email
- `--gcp-project`: GCP project ID

Additional options:
- `--include-pipeline`, `-i`: Include data pipeline. Some agents e.g `agentic_rag_vertexai_search` will require and include this by default.
- `--region`: GCP region for deployment (default: us-central1)
- `--debug`: Enable debug logging
- `--output-dir`, `-o`: Output directory for the project (default: current directory)
- `--auto-approve`: Skip credential confirmation prompts

### Example Usage

```bash
# Create a new project
agent-starter-pack create my-agent-project

# Create with specific agent and deployment target and google cloud region
agent-starter-pack create my-agent-project -a chat_agent -d cloud_run --region europe-west1
```

## Setup CICD Command

The `setup-cicd` command helps set up CI/CD infrastructure for your agent project using Terraform.

Important Notes:
- The setup-cicd command is experimental and intended for development/testing
- For production deployments, follow the manual setup in deployment/README.md
- Only GitHub is currently supported as a git provider
- Remote state uses a GCS bucket by default (can be disabled with --local-state)


```bash
agent-starter-pack setup-cicd [OPTIONS]
```

### Options

- `--dev-project`: Development project ID
- `--staging-project`: Staging project ID (required)
- `--prod-project`: Production project ID (required)
- `--cicd-project`: CICD project ID (required)
- `--region`: GCP region (default: us-central1)
- `--repository-name`: Repository name
- `--repository-owner`: Repository owner (defaults to current GitHub user)
- `--host-connection-name`: Host connection name
- `--github-pat`: GitHub Personal Access Token for programmatic auth
- `--github-app-installation-id`: GitHub App Installation ID for programmatic auth
- `--git-provider`: Git provider to use (currently only GitHub is supported)
- `--local-state`: Use local Terraform state instead of remote GCS backend
- `--debug`: Enable debug logging
- `--auto-approve`: Skip confirmation prompts

### Example Usage

```bash
# Basic setup with required projects
agent-starter-pack setup-cicd \
  --staging-project staging-project-id \
  --prod-project prod-project-id \
  --cicd-project cicd-project-id

# Setup with custom repository and region
agent-starter-pack setup-cicd \
  --staging-project staging-project-id \
  --prod-project prod-project-id \
  --cicd-project cicd-project-id \
  --repository-name my-repo \
  --region europe-west1
```
