# Contributing to aicgen

Thank you for your interest in contributing to aicgen! We welcome contributions from the community.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Coding Guidelines](#coding-guidelines)
- [Commit Message Guidelines](#commit-message-guidelines)

---

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

---

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Clear title and description**
- **Steps to reproduce** the issue
- **Expected vs actual behavior**
- **Environment details** (OS, Node/Bun version, CLI version)
- **Error messages or logs**

Use our [bug report template](https://github.com/aicgen/aicgen/issues/new?template=bug_report.md).

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear, descriptive title**
- **Provide detailed description** of the suggested enhancement
- **Explain why this enhancement would be useful**
- **Include examples** of how it would work

Use our [feature request template](https://github.com/aicgen/aicgen/issues/new?template=feature_request.md).

### 📚 Contributing Guidelines

Help expand our guideline library:

1. Fork [aicgen-data](https://github.com/aicgen/aicgen-data)
2. Add your guideline in the appropriate category
3. Update `data/mappings.json` with metadata
4. Submit a pull request

**Guideline Quality Standards:**
- Clear, actionable advice
- Include code examples (good vs bad)
- Follow existing formatting
- Language-agnostic when possible
- Cite sources if applicable

### 🔧 Contributing Code

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Write or update tests
5. Ensure all tests pass (`bun test`)
6. Commit your changes (see commit guidelines below)
7. Push to your branch (`git push origin feature/amazing-feature`)
8. Open a Pull Request

---

## Development Setup

### Prerequisites

- [Bun](https://bun.sh) >= 1.0.0 (or Node.js >= 20.x)
- Git

### Setup Instructions

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/aicgen.git
cd aicgen

# Install dependencies
bun install

# Build the project
bun run build

# Run tests
bun test

# Run tests with coverage
bun test --coverage

# Run in development mode
bun run dev
```

### Project Structure

```
src/
├── __tests__/              # Test suite
│   └── services/
├── commands/               # CLI commands (init, update, quick-add)
├── services/               # Core business logic
│   ├── guideline-loader.ts
│   ├── assistant-file-writer.ts
│   └── data-source.ts
├── models/                 # TypeScript interfaces
└── config.ts              # Configuration management
```

---

## Pull Request Process

1. **Update tests** - Add or update tests for your changes
2. **Update documentation** - Update README or docs if needed
3. **Follow code style** - Match existing code formatting
4. **Pass all tests** - `bun test` must pass
5. **One feature per PR** - Keep PRs focused
6. **Descriptive PR title** - Use conventional commit format
7. **Fill out PR template** - Provide context and testing details

### PR Checklist

- [ ] Tests pass locally (`bun test`)
- [ ] Code follows project style guidelines
- [ ] Documentation updated (if needed)
- [ ] No new warnings or errors
- [ ] Commits follow conventional commit format
- [ ] Branch is up to date with main

---

## Coding Guidelines

### TypeScript Style

- Use TypeScript strict mode
- Prefer `const` over `let`, avoid `var`
- Use explicit types for function parameters and return values
- Avoid `any` - use `unknown` with type guards
- Use async/await over promise chains

### Code Quality

- **DRY** - Don't repeat yourself
- **SOLID** - Follow SOLID principles
- **Clear naming** - Use descriptive variable and function names
- **Small functions** - Keep functions focused on single responsibility
- **Error handling** - Always handle errors appropriately

### Testing

- Write tests for new features
- Update tests when modifying existing code
- Aim for high coverage (current: 94%)
- Use descriptive test names: `should [expected behavior] when [condition]`

**Test Structure (Arrange-Act-Assert):**
```typescript
test('should return user when ID exists', async () => {
  // Arrange
  const userId = '123';

  // Act
  const user = await userService.findById(userId);

  // Assert
  expect(user).toBeDefined();
  expect(user.id).toBe(userId);
});
```

---

## Commit Message Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification:

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `style`: Code style changes (formatting, semicolons, etc.)
- `refactor`: Code refactoring (no functionality change)
- `perf`: Performance improvement
- `test`: Adding or updating tests
- `chore`: Maintenance tasks (deps, config, etc.)

### Examples

```bash
feat(cli): add quick-add command for selective guideline addition

fix(loader): resolve full level architecture filtering bug

docs(readme): add test coverage section

test(services): add tests for assistant file writer
```

### Best Practices

- Use imperative mood ("add" not "added" or "adds")
- Don't capitalize first letter
- No period at the end of subject
- Limit subject line to 72 characters
- Separate subject from body with blank line
- Use body to explain *what* and *why*, not *how*

---

## Questions?

- Open a [discussion](https://github.com/aicgen/aicgen/discussions)
- Check existing [issues](https://github.com/aicgen/aicgen/issues)
- Read the [documentation](https://github.com/aicgen/aicgen#readme)

---

**Thank you for contributing to aicgen! 🚀**
