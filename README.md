# Google Drive MCP Server

A server that provides MCP (Machine Control Protocol) interface to interact with Google Drive files and folders.

## Features

- Search for files in Google Drive
- Get file content and metadata
- OAuth authentication with token persistence
- HTTP and stdio transport modes

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

3. Set up Google Drive authentication:
```bash
python -m gdrive_mcp_server.auth_setup --credentials /path/to/your/credentials.json
```

## Usage

Run the server:
```bash
# Standard mode
gdrive-mcp

# HTTP mode
gdrive-mcp --http
```

## Development

The project uses:
- Python 3.8+
- Google Drive API
- MCP server framework

## License

MIT License 