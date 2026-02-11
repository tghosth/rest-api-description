# GitHub API Trimmed Schemas - Overview

This directory contains trimmed-down versions of the GitHub REST API OpenAPI schema, optimized for ChatGPT actions and other use cases requiring lightweight, read-only API specifications.

## Available Schemas

### 1. Curated Essential - `api.github.com.curated.json` ⭐ **RECOMMENDED**
**13 endpoints** for essential issue and PR operations

- **Size**: 279 KB (97.5% reduction from full 11.35 MB schema)
- **Focus**: Core operations - get issues/PRs, comments, reviews, search
- **Components**: 66 schemas, parameters, responses, examples, headers
- **Documentation**: [README.curated.md](README.curated.md)
- **Perfect for**: ChatGPT actions, simple integrations, prototyping

**Use Cases**:
- **ChatGPT Actions** - Focused, essential operations
- Simple issue/PR readers
- Lightweight mobile apps
- Quick prototypes and demos

### 2. Issues Only - `api.github.com.issues.json`
**22 endpoints** for GitHub Issues operations

- **Size**: 300 KB (97.5% reduction from full 11.35 MB schema)
- **Focus**: Issue listing, comments, events, labels, reactions, timeline, dependencies, parent/sub-issues
- **Components**: 91 schemas, parameters, responses, examples, headers
- **Documentation**: [README.issues.md](README.issues.md)

**Use Cases**:
- Issue tracking dashboards
- Issue search and analytics
- Bug triage tools
- Issue management assistants

### 3. Pull Requests Only - `api.github.com.pulls.json`
**15 endpoints** for GitHub Pull Requests operations

- **Size**: 257 KB (97.7% reduction from full 11.35 MB schema)
- **Focus**: PR listing, commits, files, reviews, comments, reviewers, merge status
- **Components**: 53 schemas, parameters, responses, examples, headers
- **Documentation**: [README.pulls.md](README.pulls.md)

**Use Cases**:
- Code review assistants
- PR status dashboards
- Review workflow automation
- PR analytics and reporting

### 4. Combined Issues + PRs - `api.github.com.issues-prs.json`
**30 endpoints** (15 issues + 12 PRs + 3 search/repo endpoints)

- **Size**: 453 KB (96.0% reduction from full 11.35 MB schema)
- **Focus**: Comprehensive read-only access to both issues and PRs
- **Components**: 118 schemas, parameters, responses, examples, headers
- **Documentation**: [README.issues-prs.md](README.issues-prs.md)
- **Note**: Trimmed to 30 operations to meet ChatGPT's operation limit

**Use Cases**:
- Unified issue/PR management
- Combined analytics
- General GitHub repository insights
- Full-featured ChatGPT actions

## Schema Comparison

| Schema | Endpoints | Issues | PRs | Size | Reduction | Best For |
|--------|-----------|--------|-----|------|-----------|----------|
| **Curated** ⭐ | 13 | 5 | 7 | 279 KB | 97.5% | ChatGPT actions, simple integrations |
| **Issues Only** | 22 | 18 | 0 | 300 KB | 97.5% | Dedicated issue tracking |
| **PRs Only** | 15 | 0 | 12 | 257 KB | 97.7% | Code review tools |
| **Combined** | 30 | 15 | 12 | 453 KB | 96.0% | Comprehensive coverage |
| **Full Schema** | 721 | - | - | 11.35 MB | - | Complete API access |

## ChatGPT Action Optimizations

All schemas are fully optimized for ChatGPT actions:

✅ **CamelCase operationIds** - e.g., `issuesList`, `pullsGet`, `pullsListReviews`  
✅ **No special characters** - Only alphanumeric characters in operationIds  
✅ **Truncated descriptions** - All descriptions ≤ 300 characters  
✅ **Inline parameters** - All `$ref` parameters converted to inline definitions  
✅ **Valid OpenAPI 3.1.0** - Fully compliant schema structure  
✅ **Resolved references** - All component references are resolved  

## Which Schema Should You Use?

**Choose Curated (`api.github.com.curated.json`) if you:** ⭐ **RECOMMENDED FOR CHATGPT**
- Want the most essential operations only (13 endpoints)
- Are building ChatGPT actions (well under 30-operation limit)
- Need simple, focused functionality
- Want quick setup with minimal complexity

**Choose Issues Only (`api.github.com.issues.json`) if you:**
- Only need issue-related operations
- Want comprehensive issue features (22 endpoints)
- Are building dedicated issue tracking tools

**Choose PRs Only (`api.github.com.pulls.json`) if you:**
- Only need pull request operations
- Are building code review tools
- Want comprehensive PR features (15 endpoints)

**Choose Combined (`api.github.com.issues-prs.json`) if you:**
- Need both issues and PRs with more features
- Are building comprehensive GitHub tools
- Want maximum coverage within 30-operation limit

## Common Features

All schemas include:

### Read-Only Operations
- ✅ GET operations only
- ❌ No POST, PUT, PATCH, DELETE operations
- ❌ No create, update, or delete capabilities

### Search Capabilities
- `/search/issues` - Search for issues and/or pull requests
- Advanced query syntax support
- Pagination support

### Standard Features
- Pagination parameters (`page`, `per_page`)
- Filtering and sorting options
- Rich response schemas with full object definitions

## Excluded Endpoints

To keep schemas focused and within size limits, the following are excluded:

- Organization-level issue endpoints (in combined schema)
- Issue type management
- Repository-wide comment/reaction listings
- Reaction endpoints (to save space)
- Label listing endpoints (in combined schema)
- All modification operations (POST/PUT/PATCH/DELETE)

## Installation & Usage

### For ChatGPT Actions

1. Download your preferred schema
2. Import into ChatGPT custom actions
3. The schema will automatically create tools for each endpoint

### For API Clients

Use with OpenAPI generators:

```bash
# Generate TypeScript client for Issues
openapi-generator-cli generate -i api.github.com.issues.json -g typescript-fetch -o ./client

# Generate Python client for PRs
openapi-generator-cli generate -i api.github.com.pulls.json -g python -o ./client

# Generate Go client for combined
openapi-generator-cli generate -i api.github.com.issues-prs.json -g go -o ./client
```

### For API Documentation

Use with documentation tools:

```bash
# Generate documentation with Redoc
npx @redocly/cli build-docs api.github.com.issues.json

# Generate documentation with Swagger UI
docker run -p 80:8080 -e SWAGGER_JSON=/api.json -v $(pwd):/api swaggerapi/swagger-ui
```

## Validation

All schemas have been validated for:
- ✅ JSON syntax correctness
- ✅ OpenAPI 3.1.0 compliance
- ✅ Component reference resolution
- ✅ ChatGPT action compatibility
- ✅ No duplicate operationIds
- ✅ Parameter name requirements

## Support & Issues

For issues specific to these trimmed schemas, please open an issue on the repository. For issues with the GitHub API itself, please refer to the [GitHub API documentation](https://docs.github.com/rest).

## License

These schemas are derived from the GitHub REST API OpenAPI description, which is licensed under the MIT license.
