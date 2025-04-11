# MCP (Message Control Protocol)

This repository contains an implementation of a Message Control Protocol system using Python. The project provides both client and server components for handling message-based communications.

## Project Structure

- `mcp.py` - Client implementation with websocket connection handling
- `app.py` - Server implementation using FastMCP framework

## Features

- WebSocket-based communication
- Tool registration and management
- Dynamic resource routing
- Example implementations:
  - Addition tool
  - Dynamic greeting resource

## Getting Started

### Prerequisites

```bash
pip install smithery
pip install mcp
```

### Server Setup

The server component (`app.py`) demonstrates how to:
1. Create an MCP server
2. Register tools and resources
3. Handle dynamic routing

Example server code:
```python
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("Demo")

@mcp.tool()
def add(a: int, b: int) -> int:
    return a + b
```

### Client Usage

The client component (`mcp.py`) shows how to:
1. Connect to the MCP server
2. List available tools
3. Make tool calls

Example client code:
```python
async with websocket_client(url) as streams:
    async with mcp.ClientSession(*streams) as session:
        tools_result = await session.list_tools()
```

## Configuration

Make sure to set up your environment with:
- Smithery API key
- GitHub Personal Access Token (if using GitHub integration)

## Contributing

Feel free to submit issues and pull requests to improve the implementation.

## License

This project is open source and available under the MIT License.