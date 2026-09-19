---
name: crawl4ai-web-scraper
description: Extract high-fidelity, clean Markdown and structured content from any web page or web application. Handles single-page JavaScript apps, dynamic DOMs, article extraction, and JavaScript execution via local headless Chromium.
---

# Crawl4AI Web Scraper Skill

Use this skill whenever you need to read the full contents of a web page, scrape articles, read online documentation, or extract information from websites that require JavaScript rendering.

## Available MCP Server & Tools

- **MCP Server**: `crawl4ai-scraper`
- **Tools**:
  - `crawl(urls: list[str], crawler_config: dict | null, browser_config: dict | null)`: Scrapes one or more URLs and returns clean, LLM-ready markdown, metadata, and extracted links.
  - `execute_js(url: str, scripts: list[str])`: Navigates to a webpage, runs custom JavaScript snippets in the DOM, and returns the evaluated results.
  - `ask(query: str, context_type: str = "all")`: Retrieves Crawl4AI library documentation and implementation patterns.

## Recommended Workflow
1. **Discovery**: Identify the target URL from conversation or via `searxng-web-search`.
2. **Scraping**:
   - Call `crawl(urls=["https://example.com/target-page"])`.
   - Crawl4AI automatically strips boilerplate, ads, navbars, and cookie banners, returning clean semantic markdown.
3. **Synthesis**: Quote key findings, cite the original source URL, and integrate the extracted facts into your answer.
