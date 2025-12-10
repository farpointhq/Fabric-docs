# Code Generation

Generate, explain, and improve code with Fabric.

## Generating Code

### Basic Generation

Simply describe what you want:

```
Write a function that validates email addresses
```

### With Requirements

Be specific for better results:

```
Write a TypeScript function that:
- Validates email addresses using regex
- Returns a validation result with error messages
- Handles edge cases like empty strings
- Includes JSDoc comments
```

### In Context

Provide context for integration:

```
I have this React component:
[paste component]

Add form validation that shows errors below each field
```

## Code Explanation

### Understanding Code

```
Explain what this code does:
[paste code]
```

### Line-by-Line Analysis

```
Walk me through this code line by line:
[paste code]
```

### Complexity Analysis

```
What's the time and space complexity of this function?
[paste code]
```

## Code Improvement

### Refactoring

```
Refactor this code to be more readable:
[paste code]
```

### Performance

```
How can I optimize this code for performance?
[paste code]
```

### Best Practices

```
Review this code and suggest improvements:
[paste code]
```

## Tips for Better Results

### 1. Provide Context

Bad:
```
Write a sort function
```

Good:
```
Write a sort function for an array of user objects.
Sort by lastName, then firstName.
Handle null/undefined values gracefully.
```

### 2. Specify Language/Framework

Bad:
```
Create a form component
```

Good:
```
Create a React form component using TypeScript and react-hook-form
```

### 3. Include Error Handling Requirements

```
Write an API client that:
- Fetches user data
- Handles network errors
- Retries failed requests up to 3 times
- Times out after 10 seconds
```

### 4. Ask for Tests

```
Write unit tests for this function using Jest:
[paste function]
```

## Agentic Code Generation

Enable agentic mode for complex tasks:

```
Create a complete authentication system with:
- Login/logout functionality
- Password reset flow
- Session management
- Rate limiting
```

Fabric will:

1. Plan the implementation
2. Create necessary files
3. Write the code
4. Generate tests
5. Present for review
