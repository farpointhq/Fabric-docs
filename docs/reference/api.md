# API Reference

For developers building integrations with Fabric.

!!! note "Coming Soon"
    The Fabric API is currently in development. This page will be updated with full API documentation when available.

## Planned Features

### REST API

```
GET  /api/v1/chats
POST /api/v1/chats
GET  /api/v1/chats/:id
DELETE /api/v1/chats/:id

POST /api/v1/chats/:id/messages
GET  /api/v1/chats/:id/messages
```

### WebSocket

Real-time streaming responses:

```javascript
const ws = new WebSocket('ws://localhost:3000/api/v1/stream');

ws.send(JSON.stringify({
  type: 'message',
  chatId: 'abc123',
  content: 'Hello!'
}));

ws.onmessage = (event) => {
  const data = JSON.parse(event.data);
  console.log(data.chunk); // Streaming response
};
```

### CLI Integration

```bash
# Send a message
fabric send "What is TypeScript?"

# Interactive mode
fabric chat

# With specific model
fabric send --model gpt-4o "Explain React hooks"
```

## Stay Updated

Follow the [GitHub repository](https://github.com/farpointhq/Fabric) for API announcements.
