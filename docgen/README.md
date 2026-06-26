# Dokmatiq DocGen — Claude Code Plugin

One-step install of the Dokmatiq DocGen MCP server (40 tools) plus a triggering `dokmatiq-docgen` skill that tells Claude Code when to use it.

Use this plugin when you want Claude Code to create PDFs, invoices, e-invoices, ZUGFeRD/XRechnung files, Excel workbooks, receipt exports, signed PDFs, filled PDF forms, or documents on company letterhead (Briefpapier/Firmenpapier).

## What's inside

- **MCP server** auto-configured: 40 tools covering PDF generation, e-invoicing (ZUGFeRD/XRechnung/Factur-X), Excel workbooks, digital signatures, PDF operations, AI-powered receipt recognition
- **Skill** with detailed trigger description so Claude reaches for these tools when relevant — without you having to spell it out each time

## Prerequisites

1. **Python 3.11+** with the MCP server installable:
   ```bash
   python3.11 -m pip install --user dokmatiq-docgen-mcp
   ```
2. **Dokmatiq API key** from https://developer.dokmatiq.com
3. **`DOCGEN_API_KEY` environment variable** set in your shell:
   ```bash
   export DOCGEN_API_KEY="dk_live_xxxxxxxxxxxxx"
   ```

## Install

In Claude Code:

```
/plugin marketplace add dokmatiq/claude-plugins
/plugin install docgen@dokmatiq
```

After install, restart Claude Code. The MCP server is auto-configured via the bundled `.mcp.json`, and the skill triggers on relevant prompts.

The bundled `.mcp.json` does not include an `env` block. JSON MCP config files do not perform shell-style `${DOCGEN_API_KEY}` expansion consistently across clients, so the server reads the real `DOCGEN_API_KEY` from the environment of the host process.

If `docgen-mcp` is installed into `~/.local/bin`, make sure that directory is on `PATH` for Claude Code, or configure the MCP server with the absolute command path.

## Verify

In Claude Code:

```
/mcp
```

Should list `docgen` as connected with 40 tools.

Then try:

```
Generate a PDF from this Markdown: # Hello world
```

The skill should fire and Claude should call `generate_pdf_from_markdown`.

## Without the plugin

If you don't use Claude Code (e.g. Claude Desktop, Cursor, Continue, Cline, Hermes), you can still use the MCP server directly — see https://github.com/dokmatiq/docgen-sdks/tree/main/mcp for setup instructions per client.

## License

MIT
