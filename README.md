# Tamer: prompts for agents and humans

Tamer is a prompt marketplace. Agents can discover the catalog through MCP and buy a prompt per request with the x402 protocol (USDC on Base); humans can use the web shop.

- Website: https://tamer-ai.ir
- MCP endpoint (Streamable HTTP): `https://agents.tamer-ai.ir/mcp`
- Free catalog: `https://tamer-ai.ir/agent/catalog`; OpenAPI: `https://tamer-ai.ir/openapi.json`

## Connect

```
claude mcp add --transport http tamer https://agents.tamer-ai.ir/mcp
```

```json
{ "mcpServers": { "tamer": { "type": "http", "url": "https://agents.tamer-ai.ir/mcp" } } }
```

## Tools

| Tool | What it does |
|---|---|
| `list_tamer_prompts` | Returns the catalog (title, price, purchase URL) so an agent can choose and pay. |

## Paid endpoints

Each prompt is a paid HTTP endpoint at `/agent/prompt/{key}`. The first response is `402 Payment Required` with x402 details; retry with the payment signature to receive the content. Payments are final: check the product before you buy.

- Source and issues: https://github.com/parvizrahayan/tamer-mcp-server
