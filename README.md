# Claude Code Prompt/Command Library

A collection of reusable Claude Code commands for the Comfy-Org team to streamline development workflows.

> **💡 Looking for more commands?** Check out [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code) - a community collection of general-purpose Claude Code commands!

## Quick Start

Commands are stored in `.claude/commands/` and can be invoked using `/project:command-name` or `/user:command-name`.

## Commands

### Meta Commands

- [`/user:AGENT-create-command`](.claude/commands/agents/AGENT-create-command.md) - Create a command by providing a task description and automatically generate an optimal prompt file
- [`/user:AGENT-improve-command`](.claude/commands/agents/AGENT-improve-command.md) - Improve an existing command by referencing Claude/Anthropic documentation materials
- [`/user:AGENT-playbook-to-automated-agent-workflow`](.claude/commands/agents/AGENT-playbook-to-automated-agent-workflow.md) - Convert playbooks/workflows to automated agent workflows using local files and MCP tools
- [`/user:AGENT-summarize-and-log-current-session`](.claude/commands/agents/AGENT-summarize-and-log-current-session.md) - Create ultra-compact summaries of conversations and save them with timestamp-based filenames
- [`/user:AGENT-memory-search`](.claude/commands/agents/AGENT-memory-search.md) - Search through past conversations using semantic memory system
- [`/user:AGENT-learn-claude-code-best-practices`](.claude/commands/agents/AGENT-learn-claude-code-best-practices.md) - Study and synthesize Claude Code best practices from comprehensive knowledge base
- [`/user:summarize-book`](.claude/commands/summarize-book.md) - Create comprehensive summaries of books with structured analysis

### GitHub/Git Commands

- [`/user:PR-submit-local-as-new-pr`](.claude/commands/github/PR-submit-local-as-new-pr.md) - Make a PR based on local changes, whether you've committed, made a branch, etc. or not
- [`/user:GH-PR-implement-review-comments`](.claude/commands/github/GH-PR-implement-review-comments.md) - Fetch the PR associated with local branch, read reviews and comments, implement the requested changes with one commit for each change
- [`/user:SOLVEBUG-solve-issue-tdd`](.claude/commands/github/SOLVEBUG-solve-issue-tdd.md) - Fetch an issue at the provided link. Solve the bug using test-driven development (write tests first, verify they fail, keep trying to fix until tests pass)
- [`/user:GH-create-github-issue`](.claude/commands/github/GH-create-github-issue.md) - Create a GitHub issue or feature request. Reference the repo name at least once in the argument
- [`/user:GH-ISSUE-enhance-issue-description`](.claude/commands/github/GH-ISSUE-enhance-issue-description.md) - Enhance GitHub issue descriptions with better formatting and clarity
- [`/user:GH-PR-add-review-comments-to-pr`](.claude/commands/github/GH-PR-add-review-comments-to-pr.md) - Add review comments to a pull request
- [`/user:GH-PR-summarize-my-open-prs`](.claude/commands/github/GH-PR-summarize-my-open-prs.md) - Summarize the status of all open pull requests for the current user
- [`/user:GH-summarize-my-recent-prs`](.claude/commands/github/GH-summarize-my-recent-prs.md) - Summarize your recent pull requests across repositories
- [`/user:GH-daily-report`](.claude/commands/github/GH-daily-report.md) - Create a daily summary of GitHub issues and PRs for comfy-org repos
- [`/user:GH-rebase-onto`](.claude/commands/github/GH-rebase-onto.md) - Rebase the current branch onto the target branch, handling conflicts safely human-in-the-loop style

### Research Commands

- [`/user:STUDY-comfy-api-architecture`](.claude/commands/research/STUDY-comfy-api-architecture.md) - Load pre-generated architecture overview for Comfy-Org/comfy-api
- [`/user:STUDY-comfyui-custom-nodes-ecosystem`](.claude/commands/research/STUDY-comfyui-custom-nodes-ecosystem.md) - Analyze ComfyUI custom nodes ecosystem patterns and trends using comprehensive dataset
- [`/user:STUDY-current-repo`](.claude/commands/research/STUDY-current-repo.md) - Study and analyze current repository structure and architecture
- [`/user:STUDY-microservices-architecture`](.claude/commands/research/STUDY-microservices-architecture.md) - Reference guide for microservices architecture patterns
- [`/user:STUDY-node-editor-performance-optimizations`](.claude/commands/research/STUDY-node-editor-performance-optimizations.md) - Absorb performance optimization research for modern graph/canvas libraries
- [`/user:research-with-auto-mcp`](.claude/commands/research/research-with-auto-mcp.md) - Automatically select and use the best MCP tool for research tasks
- [`/user:STUDY-knowledge-folder`](.claude/commands/research/STUDY-knowledge-folder.md) - Study all markdown files in a knowledge folder for comprehensive understanding

### Analysis Commands

- [`/user:ANALYZE-repo-for-claude`](.claude/commands/analysis/ANALYZE-repo-for-claude.md) - Analyze repository to provide Claude with necessary context and understanding

### Notion Commands

- [`/user:NOTION-TASKS-audit-task-view`](.claude/commands/notion/NOTION-TASKS-audit-task-view.md) - Audit and update team task views in Notion
- [`/user:NOTION-convert-to-bounty-task`](.claude/commands/notion/NOTION-convert-to-bounty-task.md) - Convert Notion tasks to bounty format for external contributors

### Team Commands

- [`/user:TEAM-team-standup-analysis`](.claude/commands/team/TEAM-team-standup-analysis.md) - Analyze team standup notes and provide insights

### ComfyUI Frontend Commands

- [`/user:frontend/FE-generate-primevue-reference`](.claude/commands/frontend/FE-generate-primevue-reference.md) - Generate a list of all available PrimeVue components and their properties, for help with building frontend UIs
- [`/user:frontend/FE-manually-publish-to-pypi`](.claude/commands/frontend/FE-manually-publish-to-pypi.md) - Publish the ComfyUI frontend package to PyPI with specified version

### Utilities

- [`/user:estimate-context-window`](.claude/commands/utilities/estimate-context-window.md) - Estimate token usage and context window requirements for large-scale analysis tasks
- [`/user:run-gemini-headless`](.claude/commands/utilities/run-gemini-headless.md) - Execute long-running Gemini tasks in background for large context analysis

### Validation

- [`/user:scan-accessibility`](.claude/commands/validation/scan-accessibility.md) - Scan for WCAG 2.1 AA compliance and accessibility issues
- [`/user:scan-api-contracts`](.claude/commands/validation/scan-api-contracts.md) - Scan API contracts for consistency and breaking changes
- [`/user:scan-bundle-size`](.claude/commands/validation/scan-bundle-size.md) - Analyze bundle sizes and identify optimization opportunities
- [`/user:scan-circular-dependencies`](.claude/commands/validation/scan-circular-dependencies.md) - Detect circular dependencies in the codebase
- [`/user:scan-configuration`](.claude/commands/validation/scan-configuration.md) - Validate configuration files for errors and best practices
- [`/user:scan-dead-code`](.claude/commands/validation/scan-dead-code.md) - Identify unused code, imports, and dependencies
- [`/user:scan-error-handling`](.claude/commands/validation/scan-error-handling.md) - Analyze error handling patterns and coverage
- [`/user:scan-index`](.claude/commands/validation/scan-index.md) - Index of all validation commands with descriptions
- [`/user:scan-memory-leaks`](.claude/commands/validation/scan-memory-leaks.md) - Detect potential memory leaks and resource management issues
- [`/user:scan-performance`](.claude/commands/validation/scan-performance.md) - Identify performance bottlenecks and optimization opportunities
- [`/user:scan-test-coverage`](.claude/commands/validation/scan-test-coverage.md) - Analyze test coverage metrics and identify gaps
- [`/user:scan-type-safety`](.claude/commands/validation/scan-type-safety.md) - Check TypeScript type safety and strict mode compliance
- [`/user:validate-basic-security`](.claude/commands/validation/validate-basic-security.md) - Basic security validation for common vulnerabilities
- [`/user:validate-code-quality`](.claude/commands/validation/validate-code-quality.md) - Comprehensive code quality metrics and analysis
- [`/user:validate-dependencies`](.claude/commands/validation/validate-dependencies.md) - Audit dependencies for security, licensing, and updates

### Development

- [`/user:create-feature-task`](.claude/commands/development/create-feature-task.md) - Create structured feature development tasks with comprehensive tracking
- [`/user:use-command-template`](.claude/commands/development/use-command-template.md) - Generate new commands using standardized templates

### Testing

- [`/user:analyze-test-failures`](.claude/commands/testing/analyze-test-failures.md) - Analyze test failures with balanced approach to identify test bugs vs implementation bugs
- [`/user:comprehensive-test-review`](.claude/commands/testing/comprehensive-test-review.md) - Perform thorough review of test suite quality and coverage
- [`/user:create-test-plan`](.claude/commands/testing/create-test-plan.md) - Generate comprehensive test plans for features or changes
- [`/user:test-failure-mindset`](.claude/commands/testing/test-failure-mindset.md) - Set proper investigative mindset for analyzing test failures

### System

- [`/user:memory-health-check`](.claude/commands/system/memory-health-check.md) - Check semantic memory system health and perform maintenance
- [`/user:semantic-memory-search`](.claude/commands/system/semantic-memory-search.md) - Search through semantic memory for past conversations and context

### Blog Management

- [`/user:add-idea`](.claude/commands/blog/add-idea.md) - Add new blog post ideas to the backlog
- [`/user:generate-outline`](.claude/commands/blog/generate-outline.md) - Generate structured outlines for blog posts
- [`/user:list-ideas`](.claude/commands/blog/list-ideas.md) - List and prioritize blog post ideas from backlog
- [`/user:prepare-publish`](.claude/commands/blog/prepare-publish.md) - Prepare blog posts for publication with final checks
- [`/user:research-topic`](.claude/commands/blog/research-topic.md) - Research topics for technical blog posts
- [`/user:review-readability`](.claude/commands/blog/review-readability.md) - Review blog posts for readability and clarity
- [`/user:review-seo`](.claude/commands/blog/review-seo.md) - Review blog posts for SEO optimization
- [`/user:review-style`](.claude/commands/blog/review-style.md) - Review blog posts for style and consistency
- [`/user:review-technical`](.claude/commands/blog/review-technical.md) - Review technical accuracy of blog posts
- [`/user:write-draft`](.claude/commands/blog/write-draft.md) - Write first drafts of blog posts

### Validation Commands

#### Frontend Validation

- [`/user:scan-comfy-conventions`](.claude/commands/validation/frontend/scan-comfy-conventions.md) - Check ComfyUI-specific patterns and PrimeVue usage
- [`/user:scan-performance-reactivity`](.claude/commands/validation/frontend/scan-performance-reactivity.md) - Validate Vue performance and reactivity patterns
- [`/user:scan-vue-patterns`](.claude/commands/validation/frontend/scan-vue-patterns.md) - Check Vue 3 best practices and anti-patterns

### Minor Precautions

- [`/user:careful-of-refactor-between-msgs`](.claude/commands/minor-precautions/careful-of-refactor-between-msgs.md) - Reminder to be careful about refactoring between messages

## Installation

1. Clone this repository
2. Commands are automatically available in your Claude Code session when working in this project
3. To make commands globally available, copy desired command files to `~/.claude/commands/`
4. **Install Gemini CLI** (required for large context analysis tasks):
   - Install from [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli)
   - Used automatically for tasks exceeding Claude's context window
5. **Set up filepath mapping** (required for repository analysis commands):
   ```bash
   cd project-summaries-for-agents
   cp filepath-mapping.json.template filepath-mapping.json
   # Edit filepath-mapping.json with your local repository paths
   ```
   See [project-summaries-for-agents/README.md](project-summaries-for-agents/README.md) for details.
6. **Install claude-code-vector-memory** (required for memory integration and search):
   - The semantic memory system is required for searching through past conversations
   - Install from: [claude-code-vector-memory repository](https://github.com/christian-byrne/claude-code-vector-memory)
   - After cloning the repository, navigate to the semantic-memory-system directory and run the setup script:
     ```bash
     cd claude-code-vector-memory/semantic-memory-system
     ./setup.sh
     ```
   - The setup script will create a virtual environment, install dependencies, build the initial index, and run a health check
7. **Install Context7 MCP** (optional but recommended):
   - Provides official documentation for many libraries via the `/research-with-auto-mcp` command
   - Install the Context7 MCP server or CLI from its repository and ensure it is running locally when using research commands

## Creating New Commands

Use the `/user:AGENT-create-command` command to generate new commands based on your requirements.

## Resources

- [Claude Documentation - Prompt Library](https://docs.anthropic.com/en/resources/prompt-library/library)
- [Claude Code Tutorials](https://docs.anthropic.com/en/docs/claude-code/tutorials)
- [Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)

## Development

### Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding new commands.

### Tips

- Commands can include the `$ARGUMENTS` placeholder to accept parameters
- Use descriptive filenames with prefixes (e.g., `GH-`, `NOTION-`, `AGENT-`) for better organization
- Test commands thoroughly before sharing with the team
