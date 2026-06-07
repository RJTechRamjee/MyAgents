# MyAgents

A curated list of AI agents with detailed usage instructions.

---

## Table of Contents

- [GitHub Copilot Coding Agent](#github-copilot-coding-agent)
- [GitHub Copilot Code Review Agent](#github-copilot-code-review-agent)
- [GitHub Copilot CLI Agent](#github-copilot-cli-agent)
- [Custom Agents (GitHub Copilot Extensions)](#custom-agents-github-copilot-extensions)

---

## GitHub Copilot Coding Agent

**Description:**  
The Copilot Coding Agent is an autonomous AI agent that can read, write, and execute code in a sandboxed environment. It handles multi-step coding tasks such as implementing features, fixing bugs, and refactoring code — all from a natural-language prompt.

**How to Use:**

1. Open a GitHub repository.
2. Navigate to the **Issues** tab and create a new issue describing the task (e.g., "Add unit tests for the login module").
3. Assign the issue to **Copilot** or use the `@copilot` mention in a comment.
4. Copilot will open a pull request with its proposed changes.
5. Review the PR, leave feedback, and Copilot will iterate based on your comments.

**Tips:**
- Be specific in your issue description — include expected behaviour, file paths, and acceptance criteria.
- Use checklists in issues to guide the agent through multi-step work.
- Mention relevant files or functions in the issue body to help the agent focus.

---

## GitHub Copilot Code Review Agent

**Description:**  
The Copilot Code Review Agent automatically reviews pull requests, surfacing bugs, security issues, and logic errors. It posts inline review comments directly on the PR diff.

**How to Use:**

1. Open a pull request in any GitHub repository where Copilot is enabled.
2. In the **Reviewers** panel, request a review from **Copilot**.
3. Copilot will analyse the diff and post review comments on relevant lines.
4. Address the comments, push new commits, and request a new review if needed.

**Tips:**
- Enable **auto-review** in repository settings so every PR is reviewed automatically.
- Resolve each comment or reply with a justification if you choose not to act on it.
- Use the thumbs-up/thumbs-down reaction on comments to improve future suggestions.

---

## GitHub Copilot CLI Agent

**Description:**  
Copilot in the CLI (`gh copilot`) provides AI-powered assistance directly in your terminal. It can explain commands, suggest shell commands from natural language, and help debug errors.

**How to Use:**

1. Install the GitHub CLI: [https://cli.github.com](https://cli.github.com)
2. Install the Copilot extension:
   ```bash
   gh extension install github/gh-copilot
   ```
3. Authenticate:
   ```bash
   gh auth login
   ```
4. Use the agent:
   - **Suggest a command:**
     ```bash
     gh copilot suggest "list all running Docker containers and their ports"
     ```
   - **Explain a command:**
     ```bash
     gh copilot explain "awk '{print $1}' file.txt"
     ```

**Tips:**
- Pass `--target shell` or `--target git` to scope suggestions to a specific tool.
- Pipe error messages directly into `gh copilot explain` to diagnose failures quickly.

---

## Custom Agents (GitHub Copilot Extensions)

**Description:**  
GitHub Copilot Extensions let you build and publish your own agents that integrate with Copilot Chat. Custom agents can query internal APIs, search documentation, or trigger automated workflows.

**How to Build:**

1. Create a GitHub App or OAuth App for your agent.
2. Implement the [Copilot Extensions API](https://docs.github.com/en/copilot/building-copilot-extensions/about-building-copilot-extensions) in your backend (Node.js, Python, etc.).
3. Handle incoming `POST /` requests from Copilot with the message payload.
4. Stream responses back using Server-Sent Events (SSE).
5. Publish the app and install it on the desired repositories or organisation.

**How to Use a Published Custom Agent:**

1. Open GitHub Copilot Chat (in VS Code, GitHub.com, or another supported editor).
2. Type `@<agent-name>` followed by your question or command.
3. The agent will respond based on its custom instructions and data sources.

**Example interaction:**
```
@my-docs-agent How do I configure the authentication middleware?
```

**Tips:**
- Keep the agent's system prompt focused on a single domain to improve response quality.
- Implement streaming responses so users see output as it is generated.
- Add a `copilot-instructions.md` file in `.github/` to give your agent repository-specific context.

---

## Contributing

To add a new agent to this list:

1. Fork this repository.
2. Add a new section to `README.md` following the existing format (Description, How to Use, Tips).
3. Open a pull request with a clear title such as `Add: <Agent Name>`.

---

## Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Building Copilot Extensions](https://docs.github.com/en/copilot/building-copilot-extensions/about-building-copilot-extensions)
- [GitHub CLI](https://cli.github.com)
