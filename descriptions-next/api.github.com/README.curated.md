# GitHub Issues & Pull Requests API - Curated OpenAPI Schema

This file contains a carefully curated subset of the GitHub REST API OpenAPI schema with **13 essential endpoints** for reading and searching issues and pull requests.

## File: `api.github.com.curated.json`

This curated schema contains the most commonly used read-only operations for GitHub Issues and Pull Requests, optimized for ChatGPT actions and lightweight integrations.

### What's Included

The schema includes **13 endpoints** for essential operations:

#### Issue Endpoints (5 endpoints)
- `GET /repos/{owner}/{repo}/issues/{issue_number}` - Get an issue
- `GET /repos/{owner}/{repo}/issues/{issue_number}/comments` - List comments on an issue
- `GET /repos/{owner}/{repo}/issues/comments/{comment_id}` - Get a single issue comment
- `GET /repos/{owner}/{repo}/issues/{issue_number}/events` - List events for an issue
- `GET /repos/{owner}/{repo}/issues/{issue_number}/parent` - Get the parent of a sub-issue

#### Pull Request Endpoints (7 endpoints)
- `GET /repos/{owner}/{repo}/pulls` - List pull requests
- `GET /repos/{owner}/{repo}/pulls/{pull_number}` - Get a pull request
- `GET /repos/{owner}/{repo}/pulls/{pull_number}/comments` - List review comments on a pull request
- `GET /repos/{owner}/{repo}/pulls/comments/{comment_id}` - Get a review comment
- `GET /repos/{owner}/{repo}/pulls/{pull_number}/reviews` - List reviews on a pull request
- `GET /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}` - Get a review
- `GET /repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}/comments` - List comments for a review

#### Search Endpoint (1 endpoint)
- `GET /search/issues` - Search for issues and pull requests

### What's NOT Included

This minimal schema excludes:
- Issue and PR creation, updating, or deletion operations (POST, PATCH, PUT, DELETE)
- Organization-level endpoints
- Repository-wide listings
- Label, assignee, and milestone management
- Reaction endpoints
- Timeline and dependency endpoints
- Commit and file listing for PRs
- Merge status and reviewer management

### Schema Statistics

- **Original schema**: 721 paths, 11.35 MB
- **Curated schema**: 13 paths, 279 KB
- **Reduction**: 97.5% smaller
- **Components included**: 66 (schemas, parameters, responses, examples, headers)

### OpenAPI Version

- OpenAPI Specification: 3.1.0

### ChatGPT Action Compatibility

This schema is fully optimized for ChatGPT actions:
- All operationIds use camelCase format (e.g., `issuesGet`, `pullsList`, `pullsListReviews`)
- OperationIds are valid identifiers containing only alphanumeric characters
- No special characters (slashes, hyphens) that might cause issues with tool ID mapping
- All operation descriptions are clear and ≤ 300 characters (ChatGPT action limit)
- All parameter references (`$ref`) have been inlined with explicit `name` fields
- Exactly 13 operations (well under ChatGPT's 30-operation limit)

### Use Cases

This curated schema is perfect for:
- **ChatGPT Actions** - Import as a focused action for essential GitHub operations
- **Simple Integrations** - Build tools that need only core issue/PR reading capabilities
- **Prototyping** - Quick setup with minimal overhead
- **Learning** - Understand GitHub's API without overwhelming complexity
- **Mobile Apps** - Lightweight schema for mobile API clients

### Example Workflows

**Issue Management**:
1. Search for issues (`searchIssuesAndPullRequests`)
2. Get issue details (`issuesGet`)
3. Read comments (`issuesListComments`, `issuesGetComment`)
4. Check events (`issuesListEvents`)

**Code Review**:
1. List pull requests (`pullsList`)
2. Get PR details (`pullsGet`)
3. Read reviews (`pullsListReviews`, `pullsGetReview`)
4. Read review comments (`pullsListReviewComments`, `pullsListCommentsForReview`)

**Issue Hierarchy**:
1. Get issue details (`issuesGet`)
2. Check parent issue (`issuesGetParent`)
3. Read related comments (`issuesListComments`)

### Generation

This schema was created by:
1. Selecting 13 most essential read-only endpoints for issues and PRs
2. Extracting only GET operations
3. Recursively resolving all component references (schemas, parameters, responses, etc.)
4. Maintaining all ChatGPT action optimizations (camelCase IDs, truncated descriptions, inline parameters)
5. Ensuring all descriptions are clear and informative within the 300-character limit

### Endpoint Details

| OperationId | Method | Path | Description Length |
|------------|--------|------|-------------------|
| issuesGet | GET | `/repos/{owner}/{repo}/issues/{issue_number}` | 275 chars |
| issuesGetComment | GET | `/repos/{owner}/{repo}/issues/comments/{comment_id}` | 140 chars |
| issuesListComments | GET | `/repos/{owner}/{repo}/issues/{issue_number}/comments` | 141 chars |
| issuesListEvents | GET | `/repos/{owner}/{repo}/issues/{issue_number}/events` | 30 chars |
| issuesGetParent | GET | `/repos/{owner}/{repo}/issues/{issue_number}/parent` | 64 chars |
| pullsList | GET | `/repos/{owner}/{repo}/pulls` | 46 chars |
| pullsGet | GET | `/repos/{owner}/{repo}/pulls/{pull_number}` | 246 chars |
| pullsGetReviewComment | GET | `/repos/{owner}/{repo}/pulls/comments/{comment_id}` | 48 chars |
| pullsListReviewComments | GET | `/repos/{owner}/{repo}/pulls/{pull_number}/comments` | 113 chars |
| pullsListReviews | GET | `/repos/{owner}/{repo}/pulls/{pull_number}/reviews` | 99 chars |
| pullsGetReview | GET | `/repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}` | 42 chars |
| pullsListCommentsForReview | GET | `/repos/{owner}/{repo}/pulls/{pull_number}/reviews/{review_id}/comments` | 50 chars |
| searchIssuesAndPullRequests | GET | `/search/issues` | 153 chars |

### Validation

The schema has been validated as:
- ✓ Valid JSON
- ✓ Valid OpenAPI 3.1.0 structure
- ✓ All component references resolved
- ✓ No unresolved `$ref` pointers
- ✓ All operationIds are unique and valid identifiers (camelCase)
- ✓ All descriptions ≤ 300 characters
- ✓ All parameters inline with explicit names
- ✓ ChatGPT action compatible

### Related Files

- `api.github.com.json` - Full GitHub REST API schema (721 endpoints)
- `api.github.com.issues.json` - Issues-only schema (22 endpoints)
- `api.github.com.pulls.json` - Pull Requests-only schema (15 endpoints)
- `api.github.com.issues-prs.json` - Combined Issues + PRs schema (30 endpoints)
- `api.github.com.curated.json` - **This file** - Curated essential endpoints (13 endpoints)

### Comparison

| Schema | Endpoints | Size | Best For |
|--------|-----------|------|----------|
| **Curated** | 13 | 279 KB | ChatGPT actions, simple integrations |
| Issues | 22 | 300 KB | Dedicated issue tracking |
| PRs | 15 | 257 KB | Dedicated code review tools |
| Combined | 30 | 453 KB | Comprehensive coverage |
| Full | 721 | 11.35 MB | Complete API access |

### Installation & Usage

**For ChatGPT Actions**:
1. Download `api.github.com.curated.json`
2. Import into ChatGPT custom actions
3. The 13 endpoints will be available as tools

**For API Clients**:
```bash
# Generate TypeScript client
openapi-generator-cli generate -i api.github.com.curated.json -g typescript-fetch -o ./client

# Generate Python client
openapi-generator-cli generate -i api.github.com.curated.json -g python -o ./client
```

**For Documentation**:
```bash
# Generate documentation with Redoc
npx @redocly/cli build-docs api.github.com.curated.json
```

### Support

For issues specific to this curated schema, please open an issue on the repository. For issues with the GitHub API itself, refer to the [GitHub API documentation](https://docs.github.com/rest).
