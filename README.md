# Anyshot

> Decentralized prompt distribution system for AI/LLM developers

Anyshot lets you install, manage, and distribute AI prompts like code dependencies. Install prompts from any source with `npx anyshot add` and reference them type-safely in your projects.

## Quick Start

```bash
# Install a prompt package
npx anyshot add @company/auth-prompts

# Or install from a URL
npx anyshot add https://registry.company.com/prompts/validation
```

## Project Structure

```bash
packages/ai/prompts/        # Your prompts directory
├── node_modules/       # npm packages
├── .anyshot/          # URL-based prompts
├── package.json       # Dependencies
└── index.js          # Type-safe exports
```

## Configuration (prompts.json)

```json
{
  "version": 1,
  "prompts": {
    "login": {
      "source": "@company/auth-prompts/login",
      "version": "1.0.0"
    }
  },
  "registries": {
    "private": "https://private-registry.company.com",
    "public": "https://registry.anyshot.ai"
  }
}
```

## Usage

```typescript
import { usePrompt } from '@anyshot/react'
import { prompt } from '@/prompts/login'

export function LoginForm() {
  const { completion } = usePrompt(prompt, {
    username: formData.username,
    attempt: loginAttempts
  })
}
```

> [!NOTE]
> **PIP support**
>
> Depending on customer demand, we may add support for PIP packages in the future. E.g:
>
> First, install the Anyshot pip library:
>
> ```bash
> pip install anyshot
> ```
>
> Then, install the specific prompt package:
>
> ```bash
> pip install @anyshot/auth-prompts
> ```
>
> Now, use the prompts login example in your Python code:
>
> ```python
> from anyshot import usePrompt
> from @anyshot/auth-prompts import login
>
> def login(username, attempt):
>   return usePrompt(login, username=username, attempt=attempt)
> ```

## Features

- 📦 Install prompts from npm or custom URLs
- 🔒 Private registry support with authentication
- 🏗️ Monorepo-friendly structure
- 💪 Type-safe prompt usage
- 🔄 Version control for prompts

## Documentation

Coming soon...

- `docs/spec.md` and `docs/architecture.md` in draft
- `docs/example.md` to get started
- `CONTRIBUTING.md` for details on how to get involved.

## Community

- [GitHub Discussions](https://github.com/corporai/anyshot/discussions) - Share ideas and feedback

## License

MIT © [Anyshot.ai](https://anyshot.ai)
