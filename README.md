# CentraMCP

An MCP server that enables agentic e-commerce operations on [Centra](https://centra.com) — orders, products, inventory, pricing, returns, shipments, and analytics, operated by AI assistants as first-class users.

This repository hosts the **binary releases** of CentraMCP. Documentation lives at **[centra.dev/centra-mcp](https://centra.dev/centra-mcp)**.

## Install

CentraMCP ships in two formats:

### Claude Desktop (one-click `.mcpb`)

Download **[centra-mcp.mcpb](https://github.com/centrahq/centra-mcp/releases/latest/download/centra-mcp.mcpb)** — always the newest release — and open it in Claude Desktop. The install form asks for your Centra Integration API URL and token, the write/production permission toggles, and license acceptance. One `.mcpb` install is bound to one Centra instance; install once per instance.

> The `.mcpb` is currently unsigned — hosts may show an "unverified publisher" warning. Verify your download against the SHA256 in `checksums.txt` on the [releases page](https://github.com/centrahq/centra-mcp/releases).

### CLI via Homebrew (Linux / macOS / WSL)

```bash
brew install centrahq/centra-mcp/centra-mcp
```

One CLI install manages any number of Centra instances. After installing:

```bash
centra-mcp setup add <clientname> --env qa --token <YOUR_API_TOKEN>
centra-mcp setup test
centra-mcp setup install-user claude-code   # or cursor, gemini, codex, claude-desktop
```

On Windows, use the `.mcpb` with Claude Desktop, or run the CLI inside WSL.

## Connecting to Centra

Create a **dedicated Integration in Centra (AMS → System → API Tokens) for each CentraMCP installation** and issue the MCP's token from it — sharing an integration with another system disables live event sync. Write access and production access are **off by default**; you enable them explicitly. Full setup guidance: [centra.dev/centra-mcp](https://centra.dev/centra-mcp).

## Feedback

Bug reports and feature requests are welcome on the [issue tracker](https://github.com/centrahq/centra-mcp/issues).

## License

CentraMCP is distributed under the [CentraMCP Freeware License](LICENSE): free to use with your own Centra instance, no redistribution, provided as-is. Embedded open-source components are listed with their licenses in the `THIRD-PARTY-NOTICES.md` file inside every download. The source code is not public.
