# Claude Code Notifications

Desktop notifications for Claude Code events on macOS.

## Features

- Notifications when Claude asks questions (AskUserQuestion)
- Notifications for permission requests
- Notifications when Claude stops
- Shows current repository and git branch in notification message

## Requirements

- macOS
- `terminal-notifier` - Install via Homebrew:
  ```bash
  brew install terminal-notifier
  ```

## Installation

Install the plugin using Claude Code:

```bash
claude plugin install dwen3232/claude-notifications
```

## Usage

Once installed, you'll automatically receive desktop notifications for the following Claude Code events:

- **Awaiting Input** - When Claude asks you a question
- **Permission Required** - When Claude needs permission to use a tool
- **Stopped** - When Claude stops execution

Each notification displays the current repository name and git branch for context.

## How It Works

This plugin uses Claude Code's hook system to trigger notifications:
- `PostToolUse` hook for AskUserQuestion events
- `PermissionRequest` hook for permission prompts
- `Stop` hook for execution stops

Notifications are sent via `terminal-notifier` with:
- Grouped notifications (group: "claude-code")
- Default system sound
- Bypasses Do Not Disturb mode

## License

MIT
