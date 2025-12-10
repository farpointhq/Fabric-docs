# Knowledge Base

Give Fabric context about your projects.

## What is the Knowledge Base?

The knowledge base stores information about your projects that persists across conversations:

- Project structure
- Coding conventions
- Common patterns
- Documentation

## Adding Knowledge

### From Files

Drag and drop files into the knowledge base:

1. Open Knowledge Base (`⌘ K`)
2. Drag files from your file system
3. Files are indexed and searchable

### From Conversations

Save useful information from chats:

1. Select text in a response
2. Click "Add to Knowledge Base"
3. Tag and categorize

### Manual Entries

Add custom entries:

```markdown
# API Conventions

- Use REST for public endpoints
- Use GraphQL for internal services
- Always version APIs: /v1/resource
- Include request IDs in headers
```

## Using Knowledge

The AI automatically references relevant knowledge when:

- You mention project-specific terms
- You ask about conventions
- You work on related code

### Explicit Reference

```
Using our API conventions, create a new endpoint for...
```

### Automatic Retrieval

The AI searches the knowledge base for relevant context automatically.

## Organization

### Tags

Organize entries with tags:

- `#api`
- `#frontend`
- `#deployment`
- `#testing`

### Categories

Group related entries:

- Conventions
- Architecture
- Troubleshooting
- Onboarding

## Best Practices

### Keep It Updated

Review and update knowledge regularly:

- Remove outdated information
- Add new conventions
- Refine existing entries

### Be Specific

Good:
```
Database migrations run with: npm run db:migrate
Test database: npm run db:migrate:test
```

Not as good:
```
We have database migrations
```

### Include Examples

```markdown
# Error Handling Pattern

All API errors should return:

{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Email is required",
    "field": "email"
  }
}
```
