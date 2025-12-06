# Contributing

Thank you for your interest in contributing to Purple Squirrel Media! This guide will help you get started.

---

## Welcome Contributors

Whether you're a developer, blockchain enthusiast, or creator, there's space for you to collaborate on our Solana projects. Let's build the future together!

---

## Ways to Contribute

### Code Contributions
- Bug fixes
- New features
- Performance improvements
- Documentation updates

### Non-Code Contributions
- Reporting bugs
- Suggesting features
- Improving documentation
- Testing and QA
- Community support

---

## Getting Started

### 1. Find an Issue

Browse open issues in our repositories:
- Look for `good first issue` labels for beginner-friendly tasks
- Check `help wanted` for issues needing attention
- Review `enhancement` for feature requests

### 2. Fork the Repository

```bash
# Fork via GitHub UI, then clone your fork
git clone https://github.com/YOUR_USERNAME/REPO_NAME.git
cd REPO_NAME

# Add upstream remote
git remote add upstream https://github.com/PurpleSquirrelMedia/REPO_NAME.git
```

### 3. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 4. Make Your Changes

Follow the coding standards and project conventions.

### 5. Test Your Changes

```bash
# Run tests
yarn test

# Build the project
yarn build

# Start local development
yarn start
```

### 6. Commit Your Changes

```bash
git add .
git commit -m "Brief description of changes"
```

### 7. Push and Create PR

```bash
git push origin feature/your-feature-name
```

Then create a Pull Request on GitHub.

---

## Pull Request Guidelines

### PR Template

Most repositories include a PR template. Please fill it out completely:

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
Describe testing performed

## Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] Tests added/updated
```

### PR Best Practices

1. **Keep PRs focused** - One feature or fix per PR
2. **Write clear descriptions** - Explain what and why
3. **Include screenshots** - For UI changes
4. **Reference issues** - Link related issues
5. **Respond to feedback** - Address review comments promptly

---

## Coding Standards

### TypeScript/JavaScript

```typescript
// Use descriptive variable names
const userWalletAddress = "...";  // Good
const addr = "...";                // Avoid

// Use async/await over callbacks
const data = await fetchData();   // Good

// Add types to function parameters
function processTransaction(tx: Transaction): Promise<string> {
  // ...
}
```

### Rust

```rust
// Follow Rust naming conventions
fn process_instruction(
    program_id: &Pubkey,
    accounts: &[AccountInfo],
    instruction_data: &[u8],
) -> ProgramResult {
    // ...
}

// Use meaningful error types
#[error]
pub enum CustomError {
    #[msg("Invalid account owner")]
    InvalidOwner,
}
```

### General Guidelines

- Use meaningful commit messages
- Keep functions small and focused
- Add comments for complex logic
- Write tests for new functionality
- Follow existing project patterns

---

## Code Review Process

1. **Automated Checks** - CI runs tests and linting
2. **Peer Review** - Team members review code
3. **Feedback** - Address comments and suggestions
4. **Approval** - Maintainer approves changes
5. **Merge** - PR is merged to main branch

---

## Issue Reporting

### Bug Reports

Include:
- Clear title and description
- Steps to reproduce
- Expected vs actual behavior
- Environment details (OS, Node version, etc.)
- Screenshots or logs if applicable

### Feature Requests

Include:
- Clear description of the feature
- Use case / motivation
- Proposed implementation (if any)
- Alternatives considered

---

## Communication

### GitHub Issues
Best for bug reports and feature requests.

### Pull Requests
For code contributions and discussions.

### Email
For sensitive matters: matthew@purplesquirrel.work

---

## Help Wanted

We're especially looking for contributors with expertise in:

- **Blockchain Technology** - Solana program development
- **Smart Contracts** - Anchor framework, Rust
- **Frontend Development** - React, TypeScript
- **Testing** - Integration and unit testing
- **Documentation** - Technical writing

---

## Recognition

All contributors are recognized in:
- PR acknowledgments
- Release notes
- Project documentation

---

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what's best for the community
- Show empathy towards others

### Unacceptable Behavior

- Harassment or discrimination
- Trolling or insulting comments
- Publishing private information
- Inappropriate conduct

---

## License

By contributing, you agree that your contributions will be licensed under the project's Apache 2.0 license.

---

## Questions?

- Open an issue for general questions
- Email matthew@purplesquirrel.work for direct contact
- Check existing documentation first

Thank you for contributing to Purple Squirrel Media!

---

[Back to Home](Home) | [Getting Started](Getting-Started)
