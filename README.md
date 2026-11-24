# Plugsky CLI

An AI coding agent in your terminal, powered by the Plugsky API with auto model routing across the Plugsky model ladder.

## Install

```sh
curl -fsSL https://plugsky.com/install | sh
```

Then authenticate:

```sh
plugsky login          # paste your sk-... key (input is hidden)
```

## Usage

```sh
plugsky "add tests for src/util"     # one-shot agentic task
plugsky                              # interactive TUI (REPL)
plugsky chat "explain this repo"     # single streaming reply, no tools
plugsky index                        # build local RAG index for this project
plugsky models                       # list available models
```

### Flags

- `-m, --model <id>`  model or `auto` (default: routes via /plugsky/route)
- `-y, --yes`         full-auto (no approval prompts)
- `--auto-edit`       auto-approve edits, still prompt for shell
- `--cwd <dir>`       working directory
- `--resume`          resume the latest session in this directory

## Commands

| Command | Description |
|---|---|
| `login` | Authenticate with your Plugsky API key |
| `run <task>` | One-shot agentic task with file/shell tools |
| `chat <msg>` | Single streaming chat reply (no tools) |
| `models` | List available models and the Plugsky ladder |
| `usage` | Show token usage and cost |
| `image <prompt>` | Generate an image |
| `speech <text>` | Text-to-speech to an audio file |
| `transcribe <f>` | Transcribe an audio file |
| `moderate <text>` | Run a moderation check |
| `mcp <sub>` | Manage MCP servers |
| `index` | Build/refresh codebase RAG index |
| `config <sub>` | Get/set configuration |
| `update` | Update to the latest version |

## Config

Layered: global `~/.plugsky/config.json` ← project `.plugsky/config.json` ← env (`PLUGSKY_BASE_URL`, `PLUGSKY_MODEL`, `PLUGSKY_API_KEY`).

| Key | Default |
|---|---|
| `defaultModel` | `auto` |
| `approvalMode` | `suggest` |
| `maxTurns` | `25` |
| `temperature` | `0.2` |

## Build from source

```sh
bun install
bun run build          # dist/index.js
bun run typecheck      # bunx --bun tsc --noEmit
bun test
```

## License

MIT

## Links

- Website: https://plugsky.com
- API docs: https://plugsky.com/docs
- Pricing: https://plugsky.com/pricing
- Model catalogue: https://plugsky.com/models
- Research: https://plugsky.com/research
