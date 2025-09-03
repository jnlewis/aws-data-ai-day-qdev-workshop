# aws-data-ai-day-qdev-workshop

## Designing the application
###  Task 4: Manage context
**Creating the dev agent**

```
cat > ~/.aws/amazonq/cli-agents/test-workshop.json << 'EOF'
{
  "name": "dev-workshop",
  "description": "Custom agent for the Advanced Development with Amazon Q Developer workshop",
  "mcpServers": {},
  "tools": ["*"],
  "allowedTools": [
    "fs_read",
    "report_issues"
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

## Testing the application
### Activity 1: Installing the Playwright MCP server
**Creating the test agent**

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
