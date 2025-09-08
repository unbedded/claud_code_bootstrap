# Review Commits - Analyze Recent Commit History

**Description:** Analyzes recent commits for quality, patterns, and suggests improvements to commit messages and practices.

**Usage:** `/review-commits [--count <n>] [--since <date>]`

## Options

- `--count <n>`: Number of recent commits to analyze (default: 5)
- `--since <date>`: Analyze commits since date (e.g., "1 week ago", "2023-12-01")

## How it works

1. **Fetch Commits**: Retrieves recent commit history using git log
2. **Analyze Messages**: Reviews commit message quality, conventions, patterns
3. **Check Changes**: Examines the scope and impact of changes
4. **Generate Report**: Provides analysis and improvement suggestions

## Implementation

This command will:
- Run `git log` with specified parameters to get commit history
- Analyze commit message structure and conventions
- Review code changes for each commit
- Identify patterns in development workflow
- Suggest improvements for future commits
- Provide overall commit quality assessment

## Example Output

```
📊 Commit Analysis Report (Last 5 commits)

✅ Good Practices:
- 4/5 commits follow conventional format
- Clear, descriptive commit messages
- Appropriate scope and granularity

⚠️ Areas for Improvement:
- 1 commit missing scope identifier
- Consider breaking down large commits

💡 Suggestions:
- Use "feat(module): description" format consistently
- Keep commits focused on single concerns
- Consider using co-authored-by tags for pair programming
```