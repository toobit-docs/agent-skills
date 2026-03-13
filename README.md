# agent-skills

A collection of AI agent skills for Toobit exchange operations. Each skill is a self-contained Markdown file that tells an AI agent how to use the `toobit` CLI to perform a specific category of tasks — market data queries, portfolio management, and trading.

## Skills

| Skill | Description | Auth Required |
|-------|-------------|---------------|
| [`toobit-cex-market`](skills/toobit-cex-market/SKILL.md) | Public market data: prices, order books, candles, funding rates, open interest, mark price, index price | No |
| [`toobit-cex-trade`](skills/toobit-cex-trade/SKILL.md) | Order management: spot and USDT-M perpetual futures, leverage, margin, TP/SL, flash close | Yes |
| [`toobit-cex-portfolio`](skills/toobit-cex-portfolio/SKILL.md) | Account operations: balances, sub-accounts, balance flow, deposit/withdraw, API key check | Yes |

## Requirements

- [`toobit` CLI](https://www.npmjs.com/package/toobit-trade-cli) installed:
  ```bash
  npm install -g toobit-trade-cli
  ```
- For authenticated skills: Toobit API credentials configured in `~/.toobit/config.toml`

## Installation

```bash
npx skills add toobit-docs/agent-skills
```

## Skill Format

Each skill is a Markdown file with a YAML frontmatter header:

```yaml
---
name: skill-name
description: "Trigger description for the AI agent routing system."
license: MIT
metadata:
  author: toobit
  version: "1.0.0"
  agent:
    requires:
      bins: ["toobit"]
---
```

The `description` field is used by the agent to decide when to activate the skill. It should enumerate the natural-language phrases and scenarios that the skill handles.

## Usage

Skills are loaded by AI agents to provide contextual instructions for CLI-based tasks. The agent reads the skill document and follows the command examples and operation flows described within.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add or improve skills.

## License

MIT — see [LICENSE](LICENSE).
