# Dokmatiq Claude Code Plugins

Claude Code plugins by [Dokmatiq](https://dokmatiq.com) — one-step install of MCP servers and triggering skills for document automation.

## Install the marketplace

In Claude Code:

```
/plugin marketplace add dokmatiq/claude-plugins
```

Then browse and install plugins:

```
/plugin install docgen@dokmatiq
```

## Available plugins

### [docgen](./docgen)

Document generation with stationery overlay, e-invoicing (ZUGFeRD/XRechnung), Excel, PDF signing, and AI receipt recognition.

Bundles the [Dokmatiq DocGen MCP server](https://github.com/dokmatiq/docgen-sdks/tree/main/mcp) (40 tools) with a triggering skill so Claude reaches for these tools when relevant — without manual prompting.

**Use cases:** generate PDFs on company stationery, create ZUGFeRD/XRechnung e-invoices, sign PDFs digitally, fill PDF forms, build styled Excel workbooks, extract receipts with AI for DATEV/SKR03 export.

**Install:**

```
/plugin marketplace add dokmatiq/claude-plugins
/plugin install docgen@dokmatiq
```

**Requires:** Python 3.11+, `pip install dokmatiq-docgen-mcp`, and a `DOCGEN_API_KEY` environment variable. Get a free API key at [developer.dokmatiq.com](https://developer.dokmatiq.com).

See [docgen/README.md](./docgen/README.md) for full setup instructions.

## License

MIT
