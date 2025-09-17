# OAuth UI Guide

This guide walks you through setting up OAuth connections in the Keyboard.dev platform using the updated UI.

## Overview

The OAuth UI in Keyboard allows you to:
- Add server providers (MCP servers)
- Manage shared connectors from your organization
- Connect your personal OAuth accounts
- Configure WebSocket connections for real-time approvals

## Step 1: Adding a Server Provider

To add a new MCP server provider:

1. Navigate to the **Settings** page
2. Click on **Connectors** in the left sidebar
3. Click **"Join or create a server"** button
4. In the modal dialog:
   - Enter a **Server name** (e.g., "My Salesforce")
   - Enter the **Server URL** provided by the service (e.g., `http://localhost:4000`)
   - Click **Connect** to establish the connection

![Add Server Provider Dialog](../images/oauth-ui/add-server-provider.png)

> **Note:** The server URL should be provided by the MCP server you're connecting to. For local development, this is typically a localhost URL.

## Step 2: Managing Connectors

Once you've added server providers, you can manage them from the Connectors page:

### Shared Connectors

The **Shared connectors** section displays integration hubs controlled by your organization, team admin, or another service. These are grouped by server:

#### Available Connectors per Server

- **Onboarding connectors**: Used for onboarding processes (can be disconnected)
- **X (Twitter)**: Social media integration (click "Connect" to authorize)
- **Google**: Google services integration (shows connected account email when active)

Each connector shows its current status and available actions:
- **Connected**: Shows "Disconnect" button
- **Not connected**: Shows "Connect" button
- **Account info**: Displays connected account details (e.g., email for Google)

![Connectors Management Page](../images/oauth-ui/connectors-page.png)

### Multiple Servers

You can have multiple shared connector servers. Each server appears as a separate section with:
- Server name as the header
- Delete button (trash icon) to remove the server
- List of available connectors for that server

If a server has no connectors available, it will display "No connectors available" with an option to "Join or create a server".

## Step 3: WebSocket Configuration

The WebSocket connection is crucial for the human-in-the-loop approval workflow:

1. Go to **Settings** → **WebSocket**
2. You'll see your **Connection key** (partially hidden for security)
3. Key details:
   - Created date and time
   - Auto-regeneration date (typically monthly)
   - Option to manually **Regenerate key** if needed

![WebSocket Configuration](../images/oauth-ui/websocket-config.png)

> **Important:** 
> - The connection key is like a password - do not share it
> - It's stored securely on your device
> - Applications need this key to connect to the approver
> - The key regenerates automatically for security

## Step 4: Message Approvals

After configuring your WebSocket connection:

1. The approval interface shows authentication status:
   - Green "Authenticated" badge when logged in
   - "GitHub Connected" status indicator
   - Settings button for quick access to configuration

2. The main approval area displays:
   - "No messages to approve" when idle
   - "Waiting for WebSocket messages..." status
   - Real-time approval requests when automation scripts run

![Message Approvals Interface](../images/oauth-ui/message-approvals.png)

## Workflow Overview

1. **Setup Phase**:
   - Add server providers via the modal dialog
   - Configure shared connectors for your organization
   - Set up WebSocket connection for approvals

2. **Connection Phase**:
   - Connect OAuth accounts (Google, X, etc.)
   - Authorize necessary permissions
   - Verify connected accounts in the UI

3. **Approval Phase**:
   - Monitor the Message Approvals page
   - Review and approve/reject automation requests
   - Track authentication status and connections

## Best Practices

- **Security**: Never share your WebSocket connection key
- **Organization**: Group related connectors under appropriate servers
- **Monitoring**: Regularly check the Message Approvals page when running automations
- **Maintenance**: Regenerate keys periodically or when team members change

## Troubleshooting

### Common Issues

1. **Server won't connect**:
   - Verify the server URL is correct
   - Ensure the MCP server is running
   - Check firewall/network settings

2. **OAuth connection fails**:
   - Clear browser cookies for the service
   - Try disconnecting and reconnecting
   - Verify you have the necessary permissions

3. **No approval messages appearing**:
   - Check WebSocket connection status
   - Regenerate connection key if needed
   - Ensure your automation script has the correct key

## Next Steps

After setting up your OAuth connections:
- Create automation scripts using the connected services
- Set up team-wide shared connectors for collaboration
- Configure additional MCP servers as needed

For more information on creating MCP servers and automation scripts, see the [MCP Server Development Guide](./mcp-server-guide.md).
