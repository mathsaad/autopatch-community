# Contributing to autoPatch Community

Thank you for your interest in contributing to autoPatch Community! This document provides guidelines for contributing to the project.

## Code of Conduct

Please be respectful and constructive in all interactions. We welcome contributors of all skill levels.

## How to Contribute

### Reporting Bugs

1. Check if the bug has already been reported in [Issues](https://github.com/mathsaad/autopatch-community/issues)
2. If not, create a new issue with:
   - Clear, descriptive title
   - Steps to reproduce
   - Expected vs actual behavior
   - System information (OS, versions)
   - Screenshots if applicable

### Suggesting Features

1. Check existing issues and discussions for similar suggestions
2. Create a new issue with the "enhancement" label
3. Describe the feature and its use case clearly

### Submitting Code

#### Branch Protection

This repository requires **pull request reviews** before merging to `main`. Direct pushes to `main` are not allowed.

#### Process

1. **Fork** the repository
2. **Create a branch** from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/your-bug-fix
   ```
3. **Make your changes** following the coding standards
4. **Test your changes** thoroughly
5. **Commit** with clear messages:
   ```bash
   git commit -m "feat: add new feature X"
   git commit -m "fix: resolve issue with Y"
   ```
6. **Push** to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Create a Pull Request** to `main`
8. **Wait for review** - at least one approval is required

#### Commit Message Format

Use conventional commits:
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation only
- `style:` - Code style (formatting, semicolons, etc.)
- `refactor:` - Code refactoring
- `test:` - Adding tests
- `chore:` - Maintenance tasks

### Code Style

#### C++ (Core/Launcher)
- Use consistent indentation (4 spaces)
- Follow existing naming conventions
- Comment complex logic
- Use modern C++ features (C++17)

#### TypeScript/Vue (Builder)
- Follow ESLint configuration
- Use TypeScript types properly
- Keep components focused and small
- Use Composition API for Vue components

## Project Structure

```
autoPatch Community/
├── cpp/                    # C++ core library
│   ├── src/               # Source files
│   │   ├── builder/       # Build system and utilities
│   │   ├── client/        # Client components
│   │   └── core/          # Core logic and functionality
│   └── refs/              # Reference implementations
├── electron-builder/       # Electron + Vue builder app
│   ├── src/
│   │   ├── main/          # Electron main process
│   │   ├── preload/       # Preload scripts
│   │   └── renderer/      # Vue frontend
│   └── native/            # Native embedder tool
├── doc/                   # Documentation
└── samples/               # Sample configurations
```

## Development Setup

### C++ Core
```bash
cd cpp
mkdir build && cd build
cmake ..
cmake --build . --config Release
```

### Electron Builder
```bash
cd electron-builder
npm install
npm run dev
```

## Questions?

- Open an issue for general questions
- Contact: saadrcaa@gmail.com

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
