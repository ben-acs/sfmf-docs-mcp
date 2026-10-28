# Salesforce Multi-Framework Documentation

A synchronised, LLM-accessible copy of the official Salesforce Multi-Framework documentation index.

This repository maintains a local Markdown copy of Salesforce's published documentation index for use with AI coding assistants, LLM-based workflows, and Model Context Protocol (MCP) integrations.

## Documentation

Start with [`docs/llms-multi-framework.md`](docs/llms-multi-framework.md).

This index links to locally synchronised Markdown pages in `docs/pages/`. The directory structure preserves the upstream Salesforce documentation paths to avoid filename collisions.

Links between downloaded pages are rewritten to local paths. Links to resources outside the downloaded set remain unchanged.

## Official Source

The source document is published by Salesforce:

https://developer.salesforce.com/docs/llms-multi-framework.txt

> The local index and documentation pages are generated from official Salesforce sources. Links to downloaded pages are rewritten to local paths; Salesforce remains the authoritative source.

## Synchronisation

GitHub Actions synchronises the documentation:
- Weekly, on Monday at 06:00 UTC.
- On demand through the workflow's **Run workflow** action.

Each run dynamically discovers Salesforce Markdown URLs listed in the official index and downloads those pages. It does not recursively crawl links found within individual pages.

All downloads must succeed before tracked documentation is updated. The workflow commits changes only when the generated content differs.

The `docs/pages/` directory is generated and must not be edited manually. Pages no longer listed in the upstream index are removed during the next successful sync.

## Implementation

To add this MCP to copilot specifically:
1. Navigate to your local `.copilot` folder on your system
2. Open the `mcp-config.json` in a code editor
3. Add the following object into the `mcpServers` object
```json
"Salesforce Multi-Framework Docs": {
  "tools": [
    "*"
  ],
  "type": "http",
  "url": "https://gitmcp.io/ben-acs/sfmf-docs-mcp"
}
```

## Intended Use

This repository is intended to support:
- AI coding assistants and LLM-based documentation retrieval.
- GitHub Copilot and MCP integrations.
- Search and retrieval of official Salesforce Multi-Framework documentation.
- Version-controlled snapshots of the Salesforce documentation index.

## Source of Truth

Salesforce's official documentation remains the authoritative source.

The contents of this repository may lag behind the upstream source between synchronisation runs. Consult the official Salesforce documentation when the latest behaviour or implementation details must be verified.

## Repository Structure

```text
sfmf-docs-mcp/
├── .github/
│   └── workflows/
│       └── sync-docs.yml
├── docs/
│   ├── llms-multi-framework.md
│   └── pages/
│       └── docs/
│           └── platform/
│               └── ...
├── llms.txt
└── README.md
```