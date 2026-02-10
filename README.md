# issues-helper-skill

🛠 A skill that allows you to quickly use all the features of [issues-helper](https://github.com/actions-cool/issues-helper).

[![](https://img.shields.io/badge/using-actions--cool-blue?style=flat-square)](https://github.com/actions-cool)

## 📖 Introduction

This is a composite GitHub Action that wraps [actions-cool/issues-helper](https://github.com/actions-cool/issues-helper) to provide quick access to all its features. It simplifies the usage by providing a unified interface with all available parameters.

## 🚀 Features

This skill provides access to all issues-helper features including:

### ⭐ Base Actions
- `add-assignees` - Assign issues to users
- `add-labels` - Add labels to issues
- `close-issue` - Close an issue
- `create-comment` - Create a comment on an issue
- `create-issue` - Create a new issue
- `create-label` - Create a new label
- `delete-comment` - Delete a comment
- `get-issue` - Get issue information
- `lock-issue` - Lock an issue
- `open-issue` - Open an issue
- `remove-assignees` - Remove assignees from an issue
- `remove-labels` - Remove labels from an issue
- `set-labels` - Set labels on an issue
- `unlock-issue` - Unlock an issue
- `update-comment` - Update a comment
- `update-issue` - Update an issue

### 🌟 Advanced Actions
- `check-inactive` - Check for inactive issues
- `check-issue` - Verify issue conditions
- `close-issues` - Batch close issues
- `find-comments` - Find comments by criteria
- `find-issues` - Find issues by criteria
- `lock-issues` - Batch lock issues
- `mark-assignees` - Quick assign with commands
- `mark-duplicate` - Mark duplicate issues
- `toggle-labels` - Toggle labels based on content
- `welcome` - Welcome new contributors

## 📦 Usage

### Basic Example

```yaml
name: Issue Management

on:
  issues:
    types: [opened, edited]

jobs:
  manage-issues:
    runs-on: ubuntu-latest
    steps:
      - name: Add labels
        uses: actions-cool/issues-helper-skill@v1
        with:
          actions: 'add-labels'
          labels: 'needs-triage'
```

### Create Comment Example

```yaml
name: Comment on Issue

on:
  issues:
    types: [opened]

jobs:
  comment:
    runs-on: ubuntu-latest
    steps:
      - name: Create comment
        uses: actions-cool/issues-helper-skill@v1
        with:
          actions: 'create-comment'
          body: |
            Hello @${{ github.event.issue.user.login }}! 
            Thank you for opening this issue.
          emoji: '+1,heart'
```

### Check Inactive Issues Example

```yaml
name: Check Inactive

on:
  schedule:
    - cron: "0 0 1 * *"

jobs:
  check-inactive:
    runs-on: ubuntu-latest
    steps:
      - name: Check inactive issues
        uses: actions-cool/issues-helper-skill@v1
        with:
          actions: 'check-inactive'
          inactive-day: 30
          inactive-label: 'inactive'
```

### Multiple Actions Example

```yaml
name: Issue Workflow

on:
  issues:
    types: [opened]

jobs:
  process-issue:
    runs-on: ubuntu-latest
    steps:
      - name: Add labels and assignees
        uses: actions-cool/issues-helper-skill@v1
        with:
          actions: 'add-labels,add-assignees'
          labels: 'needs-review'
          assignees: 'maintainer1,maintainer2'
          random-to: 1
```

### Create Issue Example

```yaml
name: Monthly Report

on:
  schedule:
    - cron: "0 0 1 * *"

jobs:
  create-report:
    runs-on: ubuntu-latest
    steps:
      - name: Create monthly issue
        uses: actions-cool/issues-helper-skill@v1
        with:
          actions: 'create-issue'
          title: 'Monthly Report - ${{ github.event.repository.updated_at }}'
          body: 'This is the monthly report issue'
          labels: 'report,monthly'
```

## 📝 Inputs

All parameters from [issues-helper](https://github.com/actions-cool/issues-helper) are supported. Here are the main inputs:

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `actions` | Action type to perform | Yes | - |
| `token` | GitHub token | No | `${{ github.token }}` |
| `issue-number` | Issue number to operate on | No | Current issue |
| `title` | Title for issue operations | No | - |
| `body` | Body content | No | - |
| `labels` | Labels to add/remove/set | No | - |
| `assignees` | Assignees to add/remove | No | - |
| `emoji` | Emoji reactions | No | - |
| `inactive-day` | Days of inactivity | No | - |

For a complete list of inputs, see the [action.yml](./action.yml) file.

## 📤 Outputs

| Output | Description |
|--------|-------------|
| `comment-id` | ID of created/updated comment |
| `issue-number` | Number of created/found issue |
| `issue-title` | Title of the issue |
| `issue-body` | Body of the issue |
| `issue-labels` | Labels of the issue |
| `issue-assignees` | Assignees of the issue |
| `issue-state` | State of the issue |
| `check-result` | Result of check-issue action |
| `comments` | Array of found comments |
| `issues` | Array of found issues |

## 🔗 Links

- [issues-helper Documentation](https://actions-cool.github.io/issues-helper/)
- [issues-helper Repository](https://github.com/actions-cool/issues-helper)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

## 📄 License

[MIT](./LICENSE)

## 🤝 Contributing

Issues and pull requests are welcome!

## ⭐ Show your support

Give a ⭐️ if this project helped you!
