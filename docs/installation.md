# Installation Guide

## Prerequisites

- **Linux/macOS** (or WSL2 on Windows)
- AI coding agent: [Claude Code](https://www.anthropic.com/claude-code), [GitHub Copilot](https://code.visualstudio.com/), [Gemini CLI](https://github.com/google-gemini/gemini-cli), [Cursor](https://cursor.sh), [Codeium](https://codeium.com), [Tabnine](https://tabnine.com), [Amazon CodeWhisperer](https://aws.amazon.com/codewhisperer/), [Replit Ghostwriter](https://replit.com/site/ghostwriter), [CodiumAI](https://www.codium.ai), or [iFlow CLI](https://platform.iflow.cn/cli/install)
- [uv](https://docs.astral.sh/uv/) for package management
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)

## Installation

### Initialize a New Project

The easiest way to get started is to initialize a new project:

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <PROJECT_NAME>
```

Or initialize in the current directory:

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init --here
```

### Specify AI Agent

You can proactively specify your AI agent during initialization:

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai claude
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai gemini
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai copilot
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai cursor
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai codeium
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai tabnine
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai codewhisperer
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai ghostwriter
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai codium
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai iflow
```

### Ignore Agent Tools Check

If you prefer to get the templates without checking for the right tools:

```bash
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai claude --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai gemini --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai copilot --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai cursor --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai codeium --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai tabnine --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai codewhisperer --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai ghostwriter --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai codium --ignore-agent-tools
uvx --from git+https://github.com/github/spec-kit.git specify init <project_name> --ai iflow --ignore-agent-tools
```

## Verification

After initialization, you should see the following commands available in your AI agent:
- `/specify` - Create specifications
- `/plan` - Generate implementation plans  
- `/tasks` - Break down into actionable tasks

## Troubleshooting

### Git Credential Manager on Linux

If you're having issues with Git authentication on Linux, you can install Git Credential Manager:

```bash
#!/usr/bin/env bash
set -e
echo "Downloading Git Credential Manager v2.6.1..."
wget https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.6.1/gcm-linux_amd64.2.6.1.deb
echo "Installing Git Credential Manager..."
sudo dpkg -i gcm-linux_amd64.2.6.1.deb
echo "Configuring Git to use GCM..."
git config --global credential.helper manager
echo "Cleaning up..."
rm gcm-linux_amd64.2.6.1.deb
```
