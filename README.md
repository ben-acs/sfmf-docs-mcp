# Salesforce Multi-Framework Documentation

A synchronised, LLM-accessible copy of the official Salesforce Multi-Framework documentation index.

This repository maintains a local Markdown copy of Salesforce's published documentation index for use with AI coding assistants, LLM-based workflows, and Model Context Protocol (MCP) integrations.

## Documentation

The documentation index is available at:

[`docs/llms-multi-framework.md`](docs/llms-multi-framework.md)

The index identifies Salesforce Multi-Framework documentation resources that can be used to answer implementation, configuration, development, and troubleshooting questions.

## Official Source

The source document is published by Salesforce:

https://developer.salesforce.com/docs/llms-multi-framework.txt

The local Markdown file is generated directly from this source. It is intended to preserve the original content rather than replace or reinterpret Salesforce's documentation.

## Synchronisation

GitHub Actions maintains the local documentation copy.

The workflow runs:
- When changes are pushed to the `main` branch.
- On a daily schedule.
- When manually triggered through GitHub Actions.

When the retrieved source differs from the committed version, the workflow creates a commit containing the updated documentation.

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
│   └── llms-multi-framework.md
├── llms.txt
└── README.md
```