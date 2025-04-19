# Google Drive MCP Server

A server that provides MCP (Machine Control Protocol) interface to interact with Google Drive files and folders.

## Features

- Search for files in Google Drive
- Get file content and metadata
- OAuth authentication with token persistence
- HTTP and stdio transport modes

## Requirements

- Python 3.12 or higher
- Google Drive API credentials

## Setup

1. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install the package in editable mode:
```bash
pip install -e .
```

3. Set up Google Drive API credentials:
   - Go to the [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project or select an existing one
   - Enable the Google Drive API for your project
   - Go to "Credentials" in the left sidebar
   - Click "Create Credentials" and select "OAuth client ID"
   - Choose "Desktop app" as the application type
   - Download the credentials file and save it as `credentials.json`

4. Set up Google Drive authentication:
```bash
python -m gdrive_mcp_server.auth_setup --credentials /path/to/your/credentials.json --token /path/to/your/tokens.json
```

## Usage

Run the server:
```bash
# Standard mode
gdrive-mcp

# HTTP mode
gdrive-mcp --http
```

## Claude Desktop Integration

To integrate with Claude Desktop, add the following configuration to your `claude_desktop_config.json`:

```json
"mcpServers": {
  "google_drive": {
    "command": "/path/to/your/venv/bin/gdrive-mcp",
    "args": [
      "--token",
      "/path/to/your/tokens.json"
    ]
  }
}
```

Replace the paths with your actual paths:
- `command`: Path to the gdrive-mcp executable in your virtual environment
- `args[1]`: Path to your tokens.json file (generated during authentication setup)

## Development

The project uses:
- Python 3.12+
- Google Drive API
- MCP server framework
- FastMCP for HTTP transport
- Rich for terminal formatting

Development dependencies can be installed with:
```bash
pip install -e ".[dev]"
```

## License

MIT License 