# aws-data-ai-day-qdev-workshop

## Activity 1: Installing the Playwright MCP server

```
cat > ~/.aws/amazonq/cli-agents/test-workshop.json << 'EOF'
{
  "name": "test-workshop",
  "description": "Custom agent for the Advanced Testing with Amazon Q Developer workshop",
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": [
        "@playwright/mcp@latest"
      ],
      "disabled": false,
      "alwaysAllow": []
    }
  },
  "tools": [
    "fs_read",
    "fs_write",
    "execute_bash",
    "use_aws",
    "@playwright"
  ],
  "allowedTools": [
    "fs_read"
  ],
  "resources": [
    "file://workshop_specs/*.md"
  ],
  "hooks": {
    "agentSpawn": []
  }
}
EOF
```
