# Claude Code for Expo & Spring Boot

A Claude Code configuration for productive full-stack development with Expo (React Native for web, Android, and iOS) and a Java 21 + Spring Boot backend. This plugin provides **12 slash commands** and **11 specialized AI agents** to supercharge your development workflow.

## Note
This is a fork from the original edmunds-claude-code plugin. The changes in this fork are in beta; they were AI generated and haven't been tested.

## Quick Install

```bash
# Step 1: Add the marketplace
/plugin marketplace add edmund-io/edmunds-claude-code

# Step 2: Install the plugin
/plugin install edmunds-claude-code
```

## What's Inside

### 📋 Development Commands (7)

- `/new-task` - Analyze code for performance issues
- `/code-explain` - Generate detailed explanations
- `/code-optimize` - Performance optimization
- `/code-cleanup` - Refactoring and cleanup
- `/feature-plan` - Feature implementation planning
- `/lint` - Linting and fixes
- `/docs-generate` - Documentation generation

### 🔌 API Commands (3)

- `/api-new` - Create new API endpoints
- `/api-test` - Test API endpoints
- `/api-protect` - Add protection & validation

### 🎨 UI Commands (2)

- `/component-new` - Create Expo/React Native components
- `/page-new` - Create Expo/React Native screens


### 🤖 Specialized AI Agents (11)

**Architecture & Planning**
- **tech-stack-researcher** - Technology choice recommendations with trade-offs
- **system-architect** - Scalable system architecture design
- **backend-architect** - Backend systems with data integrity & security
- **frontend-architect** - Performant, accessible UI architecture
- **requirements-analyst** - Transform ideas into concrete specifications

**Code Quality & Performance**
- **refactoring-expert** - Systematic refactoring and clean code
- **performance-engineer** - Measurement-driven optimization
- **security-engineer** - Vulnerability identification and security standards

**Documentation & Research**
- **technical-writer** - Clear, comprehensive documentation
- **learning-guide** - Teaching programming concepts progressively
- **deep-research-agent** - Comprehensive research with adaptive strategies

## Installation

### From GitHub (Recommended)

```bash
# Add marketplace
/plugin marketplace add edmund-io/edmunds-claude-code

# Install plugin
/plugin install edmunds-claude-code
```

### From Local Clone (for development)

```bash
git clone https://github.com/edmund-io/edmunds-claude-code.git
cd edmunds-claude-code

# Add as local marketplace
/plugin marketplace add /path/to/edmunds-claude-code

# Install plugin
/plugin install edmunds-claude-code
```

## Best For

- Expo / React Native developers
- Java / Spring Boot developers
- TypeScript projects
- PostgreSQL users
- Full-stack engineers

## Usage Examples

### Planning a Feature

```bash
/feature-plan
# Then describe your feature idea
```

### Creating an API

```bash
/api-new
# Claude will scaffold a complete Java/Spring Boot REST controller, service, and entity
```

### Research Tech Choices

Just ask Claude questions like:
- "Should I use WebSockets or SSE?"
- "How should I structure this database?"
- "What's the best library for X?"

The tech-stack-researcher agent automatically activates and provides detailed, researched answers.

## Philosophy

This setup emphasizes:
- **Type Safety**: Never uses `any` types
- **Best Practices**: Follows modern Expo/React Native and Java/Spring Boot patterns
- **Productivity**: Reduces repetitive scaffolding
- **Research**: AI-powered tech decisions with evidence

## Requirements

- Claude Code 2.0.13+
- Works with any project (optimized for Expo/React Native + Java/Spring Boot)

## Customization

After installation, you can customize any command by editing files in `.claude/commands/` and `.claude/agents/`.

## Contributing

Feel free to:
- Fork and customize for your needs
- Submit issues or suggestions
- Share your improvements

## License

MIT - Use freely in your projects

## Author

Created by Edmund
Fork by Erick

---

**Note**: This setup has been adapted for Expo/React Native and Java/Spring Boot workflows.
