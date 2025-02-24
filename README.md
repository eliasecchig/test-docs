# 🚀 Agent Starter Pack

[![PyPI Package - Not Yet Released](https://img.shields.io/badge/PyPI%20Package-Not%20Yet%20Released-lightgray)](link-to-pypi-when-available) [![License - Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue)](LICENSE) [![Code of Conduct](https://img.shields.io/badge/Code%20of%20Conduct-2.0-green)](CODE_OF_CONDUCT.md)

### From Prototype to Production in Minutes.


|                                             |                                                                                                                                      |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| [**1-Minute Video Overview**](https://youtu.be/D_VQYTczBpc)     | [<img src="https://img.youtube.com/vi/D_VQYTczBpc/maxresdefault.jpg" width="100" alt="Preview Video">](https://youtu.be/D_VQYTczBpc) |
| [**20-Minute Video Walkthrough**](https://youtu.be/kwRG7cnqSu0) | [<img src="https://img.youtube.com/vi/kwRG7cnqSu0/maxresdefault.jpg" width="100" alt="Preview Video">](https://youtu.be/kwRG7cnqSu0) |

---

Launch production-ready AI agents on Google Cloud in minutes, not weeks. 
This comprehensive starter pack eliminates boilerplate, letting you focus on innovation.

*   **⚡️ Launch in Minutes:**  Pre-built agent templates (ReAct, RAG, multi-agent, Live Multimodal API) get you from idea to prototype *fast*.
*   **🧪 Experiment & Refine:**  Built-in Vertex AI evaluation and an interactive playground make testing and iteration a breeze.
*   **✅ Deploy with Confidence:**  Production-ready infrastructure with monitoring, observability, and CI/CD is already set up.
*   **☁️ Your Choice of Deployment:**  Fully managed Agent Engine or serverless Google Cloud Run.
*   **🛠️ Make it Your Own:**  Easily extend and customize these templates to fit your specific needs.

---

## 🚀 Get Started in 1 Minute

Ready to build your AI agent? Follow these simple steps:

```bash
# 1. Install the Agent Starter Pack CLI
pip install agent-starter-pack

# 2. Create a new agent project (choose from available templates)
agent-starter-pack create my-awesome-agent
```

**That's it!**  You now have a fully functional agent project ready to explore and customize.


Need more control? Customize your project creation with additional options:

```bash
# Example: Create a LangGraph project for Agent Engine in europe-west1:
agent-starter-pack create my-agent --d agent_engine --a langgraph_base_react --region europe-west1
```

*See the [full list of options](#available-options) for details.*

## 🏗️ Available Agents

| Agent Name                  | Description                                                                                                                       |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| `langgraph_base_react`      | A agent implementing a base ReAct agent using LangGraph |
| `agentic_rag_vertexai_search` | A RAG agent using Vertex AI Search and LangGraph for document retrieval and Q&A       |
| `crewai_coding_crew`       | A multi-agent system implemented with CrewAI created to support coding activities       |
| `multimodal_live_api`       | A real-time multimodal RAG agent powered by Gemini, supporting audio/video/text chat with vector DB-backed responses                       |

**More agents are on the way!** We are continuously expanding our [agent library](./agents/).  Have a specific agent type in mind?  [Contribute!](#contributing)

## High-Level Architecture

This starter pack covers all aspects of Agent development, from prototyping and evaluation to deployment and monitoring.

![High Level Architecture](https://storage.googleapis.com/github-repo/generative-ai/sample-apps/e2e-gen-ai-app-starter-pack/high_level_architecture.png "Architecture")

### ⚙️ CI/CD Setup (Experimental)

This starter pack provides an *experimental* command to automate the setup of a basic CI/CD pipeline.  This pipeline connects your agent to a GitHub repository and uses Google Cloud Build for automated testing and deployment.

See more details (here)(TODO)

## 🔧 Requirements

- Python 3.10+
- [Google Cloud SDK](https://cloud.google.com/sdk/docs/install)
- [uv](https://github.com/astral-sh/uv)
- [Terraform](https://developer.hashicorp.com/terraform/downloads) (for deployment)


## 📚 Documentation

Visit our [documentation](https://github.com/yourusername/agent-starter-pack/docs) for:
- Detailed setup guides
- Template customization
- Best practices
- Deployment strategies

## Contributing

Contributions are welcome! See the [Contributing Guide](CONTRIBUTING.md).

## Feedback

We value your input! Your feedback helps us improve this starter pack and make it more useful for the community.

### Getting Help

If you encounter any issues or have specific suggestions, please first consider [raising an issue](https://github.com/GoogleCloudPlatform/generative-ai/issues) on our GitHub repository.

### Share Your Experience

For other types of feedback, or if you'd like to share a positive experience or success story using this starter pack, we'd love to hear from you! You can reach out to us at <a href="mailto:e2e-gen-ai-app-starter-pack@google.com">e2e-gen-ai-app-starter-pack@google.com</a>.

Thank you for your contributions!

## Disclaimer

This repository is for demonstrative purposes only and is not an officially supported Google product.
# test-docs
