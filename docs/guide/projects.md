# Projects

Organize your work with Fabric projects.

## What are Projects?

Projects group related chats together and can store context about your codebase.

## Creating a Project

1. Click **New Project** in the sidebar
2. Name your project
3. (Optional) Add a project directory

## Project Directory

Link a local directory to give Fabric context:

```
Project: My Web App
Directory: ~/Projects/my-web-app
```

With a linked directory, Fabric can:

- Search your codebase
- Read file contents
- Understand your project structure

## Project Context

Add custom instructions for the project:

```
This is a Next.js 14 app using:
- TypeScript
- Tailwind CSS
- Prisma ORM
- PostgreSQL

Follow these conventions:
- Use server components by default
- Keep API routes in app/api
- Use zod for validation
```

## Best Practices

### One Project Per Codebase

Keep separate projects for separate codebases:

- ✅ `my-web-app` project for frontend
- ✅ `my-api` project for backend
- ❌ One project for everything

### Update Context Regularly

As your project evolves:

1. Update project context
2. Remove outdated information
3. Add new conventions

### Archive Old Projects

Don't delete - archive:

1. Right-click project
2. Select "Archive"
3. Access from "Archived Projects"
