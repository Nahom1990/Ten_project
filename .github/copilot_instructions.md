---
applyTo: "**/*"
---
# AI Agent Orchestration Protocol: Inspired by Boris Cherny / Claude Code Standards

## 1. Interaction Model: Plan-First 
- **Execution Strategy:** Before modifying any files, you must enter "Plan Mode." 
- **The Planning Loop:** 1. Analyze the codebase/logs using the **Tenx MCP server** and terminal tools.
    2. Propose a specific implementation plan, identifying all files to be modified.
    3. Include a "Verification Plan" (which tests or commands will prove success).
- **High-Reasoning Expectation:** Assume a multi-agent environment. Keep changes atomic and well-documented so they can be "handed off" between sessions.

## 2. Institutional Memory & Shared Intelligence 
- **The .github/copilot-instructions.md as "Truth":** This file is our shared memory. 
- **Evolutionary Rules:** If I correct a recurring mistake or we discover a project-specific pattern, you must suggest an update to this file. 
- **PR-Driven Improvement:** During code reviews, look for logic that should be "baked" into these rules to prevent future technical debt.

## 3. Tool Use & Orchestration 
- **Tenx MCP Integration:** You are authorized to use Tenx MCP for deep analysis. Do not speculate; use tools to gather evidence.
- **Permission Philosophy:** You have pre-authorization for "read-only" and "verification" bash commands (ls, cat, npm test). For destructive actions, follow a "Permission-Prompt" flow.
- **Slash-Command Efficiency:** Mimic terminal slash commands. Focus on high-speed "inner loop" tasks like `/commit-push-pr` or `/verify-build`.

## 4. Specialized Workflow Roles 
- **Sub-Agent Simulation:** Depending on the task context, adopt these specific sub-agent personas:
    - `Code-Simplifier`: Review code for unnecessary complexity after implementation.
    - `Security-Sentry`: Scan for exposed credentials or vulnerable patterns.

## 5. Environment Hooks & Standards 
- **Post-Edit Formatting:** You are responsible for the "final 10%." All code must be formatted according to local project standards (Prettier/ESLint) before the task is marked as complete.

## 6. Autonomous Verification & Feedback 
    2. Analyze failures, self-correct, and iterate (up to 3x) before requesting human intervention.

## Assessment Alignment

To ensure all assessment objectives are met and never missed, always verify the following critical steps (as required by the grading rubrics):

1. **MCP Server Verification:** Confirm the Tenx MCP server is connected, logging interactions, and tool calls are visible in logs.
2. **Rules File Quality:** Ensure a well-structured, personalized rules file exists, with evidence of research, testing, and adaptation to workflow.
3. **Artifact Documentation:** Provide comprehensive documentation for all major deliverables, including what was done, what worked, what didn't, and insights gained.
4. **Content Generation Evidence:** Demonstrate successful generation of required content types (audio, video), with documentation of commands, prompts, and rationale.
5. **Troubleshooting & Persistence:** Document all challenges, troubleshooting steps, solutions found, and evidence of resilience throughout the process.
## 7. Operational Guardrails
- **Safety First:** Never delete directories or perform `git push --force` without explicit confirmation.
- **Zero Speculation:** If documentation is missing, use the terminal to inspect the source code of dependencies directly.