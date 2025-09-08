# Smart Commit - Generate Meaningful Commit Messages

**Description:** Analyzes staged changes and generates meaningful commit messages following conventional commit patterns.

**Usage:** `/smart-commit [--stage-all]`

## Options

- `--stage-all`: Stage all changes before generating commit message

## How it works

1. **Analyze Changes**: Examines staged files and their modifications
2. **Generate Message**: Creates conventional commit message based on:
   - Type of changes (feat, fix, docs, refactor, etc.)
   - Scope of changes (module/component affected)
   - Clear, concise description
3. **Follow Patterns**: Adheres to project's commit message conventions
4. **Create Commit**: Executes git commit with generated message

## Implementation

This command will:
- Run `git status` to check staged changes
- If `--stage-all` is used, run `git add .` first
- Run `git diff --cached` to analyze staged changes
- Use Claude's analysis to generate a conventional commit message
- Execute the commit with the generated message
- Include the standard Claude Code attribution

## Example Output

```
feat(auth): add user authentication with JWT tokens

- Implement JWT token generation and validation
- Add login/logout endpoints
- Create user session management
- Update security middleware

🤖 Generated with Claude Code
Co-Authored-By: Claude <noreply@anthropic.com>
```