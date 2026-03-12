# agent-skills

A collection of AI agent skills for Toobit exchange operations. Each skill is a self-contained Markdown file that tells an AI agent how to use the `toobit` CLI to perform a specific category of tasks — market data queries, portfolio management, and trading.

[中文文档](#中文文档)

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

---

# 中文文档

一组适用于 Toobit 交易所的 AI 代理技能集合。每个技能是一个独立的 Markdown 文件，指导 AI 代理如何使用 `toobit` CLI 执行特定类别的任务——行情查询、账户管理和交易操作。

## 技能列表

| 技能 | 说明 | 需要认证 |
|------|------|----------|
| [`toobit-cex-market`](skills/toobit-cex-market/SKILL.md) | 公开行情数据：价格、盘口、K线、资金费率、持仓量、标记价、指数价 | 否 |
| [`toobit-cex-trade`](skills/toobit-cex-trade/SKILL.md) | 订单管理：现货和 USDT-M 永续合约、杠杆、保证金、止盈止损、闪电平仓 | 是 |
| [`toobit-cex-portfolio`](skills/toobit-cex-portfolio/SKILL.md) | 账户操作：余额、子账户、流水、充提、API Key 检查 | 是 |

## 前置条件

- 安装 [`toobit` CLI](https://www.npmjs.com/package/toobit-trade-cli)：
  ```bash
  npm install -g toobit-trade-cli
  ```
- 需认证的技能：在 `~/.toobit/config.toml` 中配置 Toobit API 凭证

## 安装

```bash
npx skills add toobit-docs/agent-skills
```

## 技能格式

每个技能是一个带有 YAML frontmatter 头部的 Markdown 文件：

```yaml
---
name: skill-name
description: "AI 代理路由系统使用的触发描述。"
license: MIT
metadata:
  author: toobit
  version: "1.0.0"
  agent:
    requires:
      bins: ["toobit"]
---
```

`description` 字段供代理判断何时激活该技能，应列举该技能处理的自然语言短语和场景。

## 使用方式

技能由 AI 代理加载，为基于 CLI 的任务提供上下文指令。代理读取技能文档，并遵循其中描述的命令示例和操作流程。

## 贡献

请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解如何添加或改进技能。

## 许可证

MIT — 见 [LICENSE](LICENSE)。
