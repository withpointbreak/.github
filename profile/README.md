# 🌊 Pointbreak

AI assistants can write code. Now they can debug it too.

Pointbreak gives AI assistants real debugger access, letting them set breakpoints, step through code, and inspect variables in your IDE, all through natural language.

Instead of guessing what's wrong or adding print statements everywhere, your AI assistant can:

- 🎯 Set breakpoints exactly where bugs occur
- 🔍 Inspect actual variable values while code runs
- 🪜 Step through execution to understand program flow
- 🐛 Find root causes by examining real program state

## 🔧 How It Works

```
┌─────────────┐      MCP          ┌──────────────┐      IDE Extension      ┌─────────────┐
│     AI      │  ─── Protocol ──► │  Pointbreak  │  ─────────────────────► │     IDE     │
│  Assistant  │                   │ MCP Server   │                         │  Debugger   │
└─────────────┘                   └──────────────┘                         └─────────────┘
```

Architecture:

1. AI assistant sends debugging commands via Model Context Protocol (MCP)
2. Pointbreak MCP server translates commands to IDE operations
3. IDE extension controls the native debugger (CodeLLDB, debugpy, Node Debug, etc.)
4. Your code runs in the real debugger with breakpoints visible in the IDE

Two installation paths:

Built-in AI agents (GitHub Copilot, Cursor Agent):

- Install IDE extension, MCP server auto-registers
- Everything works automatically

External AI assistants (Claude Code, Codex, etc.):

- Install IDE extension, install MCP server, configure AI assistant
- Gives any MCP-compatible assistant debugger access

### [pointbreak](https://github.com/withpointbreak/pointbreak)

The main MCP server and VS Code extension. Download binaries, read docs, and report issues.

Supported:

- Languages: Python, JavaScript, TypeScript, Rust, Go, C, C++, and any language with Debug Adapter Protocol support
- AI Assistants: GitHub Copilot, Cursor, Claude Code, Codex, and any MCP-compatible tool
- IDEs: VS Code, Cursor, Windsurf, and VS Code-compatible editors
- Platforms: macOS, Linux, Windows (x64 + ARM64)

## 🚀 Get Started

Path 1: Built-in AI agents (GitHub Copilot / Cursor Agent)

```bash
# Install VS Code/Cursor extension, MCP server auto-installs
# Search "Pointbreak" in Extensions marketplace
```

Path 2: External AI assistants (Claude Code, Codex, etc.) or Windsurf

```bash
# Step 1: Install IDE extension (search "Pointbreak" in Extensions)

# Step 2: Install MCP server
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/withpointbreak/pointbreak/main/scripts/install.sh | sh

# Windows (PowerShell)
irm https://raw.githubusercontent.com/withpointbreak/pointbreak/main/scripts/install.ps1 | iex

# Step 3: Configure your AI assistant's MCP settings
# See docs for your specific assistant
```

📚 **[Full documentation](https://docs.withpointbreak.com)**

## 💡 Example

```
User: "Debug this test and tell me why user_input is empty"

AI: Setting breakpoint at line 15... Starting debugger...
    [Breakpoint appears in VS Code]
    [Debug session starts]
    [Code pauses at breakpoint]

    Found it! You're reading user_input before prompting the user.
    The input happens on line 18, but you're using it on line 15.
    Move the prompt above the read.
```

## 🤝 Community

Pointbreak is free, but it's not currently Open Source Software. At this early stage, your feedback is highly valued in helping shape the future of the project:

- 🐛 **[Report bugs](https://github.com/withpointbreak/pointbreak/issues)** - Help identify and fix issues
- 💡 **[Request features](https://github.com/withpointbreak/pointbreak/issues/new?template=feature_request.yml)** - Share ideas for improvements
- 💬 **[Discussions](https://github.com/withpointbreak/pointbreak/discussions)** - Share use cases and experiences
- 🌐 **[Website](https://withpointbreak.com)** - Learn more

**Glass-box debugging for AI-assisted development. Proof beats prediction.**

Built by [Kevin Swiber](https://github.com/kevinswiber)

Made with ❤️ in Santa Cruz, California
