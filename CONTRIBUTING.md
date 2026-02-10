# Contributing to issues-helper-skill

Thank you for your interest in contributing! 🎉

## How to Use This Skill

This repository provides a skill (composite action) that wraps [actions-cool/issues-helper](https://github.com/actions-cool/issues-helper). You can use it in your workflows to manage GitHub issues efficiently.

## Quick Start

1. **Add to your workflow**: Reference this action in your `.github/workflows` directory:

```yaml
- uses: actions-cool/issues-helper-skill@v1
  with:
    actions: 'create-comment'
    body: 'Hello!'
```

2. **Check examples**: See `.github/workflows/example.yml` for more usage examples.

3. **Read documentation**: Check the [README.md](./README.md) for full documentation.

## Reporting Issues

If you encounter any problems:

1. Check the [issues-helper documentation](https://actions-cool.github.io/issues-helper/)
2. Search existing [issues](https://github.com/actions-cool/issues-helper-skill/issues)
3. Create a new issue with:
   - Clear description of the problem
   - Steps to reproduce
   - Expected vs actual behavior
   - Workflow example if applicable

## Suggesting Features

For new features:

1. Check if it's already supported by [issues-helper](https://github.com/actions-cool/issues-helper)
2. Open an issue to discuss the feature
3. Provide use cases and examples

## Pull Requests

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Update documentation if needed
5. Submit a pull request

## Questions?

Feel free to open an issue for any questions!
