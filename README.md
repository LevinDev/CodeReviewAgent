# CodeReviewAgent
AI code review agent for iOS pull requests. Multi-agent orchestration with Claude — specialist reviewers + synthesizer, triggered via GitHub Actions.


An experimental AI-powered code review agent for iOS pull requests, built as a hands-on exercise for the Claude Certified Architect exam. Uses the orchestrator-workers pattern: two specialist reviewers (crash risks like force unwraps, Swift style violations) run independently against the PR diff using Claude Haiku 4.5, then a synthesizer using Claude Sonnet 4.6 deduplicates and prioritizes their findings into a single review comment.
Implements the four-tier base-branch resolution chain (CLI arg → CI env var → open PR's base → team default), per-workspace API spend limits via Anthropic Console, and a structured-output contract via forced tool-use. Designed to run identically on a developer's laptop and on a GitHub Actions runner, with the same agent code consuming different input sources.****
