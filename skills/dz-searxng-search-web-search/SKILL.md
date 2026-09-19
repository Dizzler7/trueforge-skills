---
name: dz-searxng-search-web-search
description: Search the live web anonymously across multiple search engines (Google, Bing, DuckDuckGo, arXiv, GitHub) using the local SearXNG meta-search engine. Use whenever you need fresh real-time information, research, news, or technical documentation.
---

# SearXNG Web Search Skill

Use this skill when you need to answer questions requiring live, updated external information, current news, technical references, or facts not present in your training data.

## Available MCP Server & Tool

- **MCP Server**: `searxng-search`
- **Tool**: `web_search(query: str, categories: str = "general", max_results: int = 8)`

### Categories
- `general`: Standard web search across major search engines.
- `news`: Current breaking events, press releases, and articles.
- `science`: Academic papers, research journals, arXiv, PubMed.
- `it`: Programming documentation, GitHub, StackOverflow, tech blogs.

## Best Practices & Query Formulation
1. **Targeted Keywords**: Formulate clear search queries. Prefer specific nouns and entities over conversational questions (e.g. `fastmcp v2 migration guide` instead of `how do I migrate to fastmcp v2?`).
2. **Category Selection**: Choose the appropriate category (e.g. `science` for research queries, `it` for programming/framework queries).
3. **Follow-up Scraping**: If a search result snippet indicates relevant content, pass the URL to `crawl4ai-web-scraper` (`crawl` tool) to inspect the full page in clean Markdown.
