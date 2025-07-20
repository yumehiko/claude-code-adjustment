# Project-specific instructions for claude-code-adjustment

This is a Claude Code workflow improvement project that collects insights and issues from working with Claude Code to develop better rules and custom commands.

## Copy Rules Command

When the user says "copy rules" (in any language):

1. Copy the global rules from `/rules/global/` to the user's global configuration at `~/.claude/CLAUDE.md`
2. Copy custom commands from `/rules/commands/` to `~/.claude/commands/`
3. If existing global configuration is found:
   - First read and show the existing content
   - Ask the user whether to append, merge, or replace
   - Proceed according to user's preference
4. Preserve the existing file structure and formatting when merging