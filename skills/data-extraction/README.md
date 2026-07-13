# AI Data Extraction & Web Crawling

Tools for turning live web pages into clean, structured data (Markdown, JSON, embeddings) suitable for feeding into an LLM, RAG pipeline, or dataset. Reach for these when a task needs to fetch and normalize web content programmatically, rather than a one-off manual fetch.

## Best Repositories

### [unclecode/crawl4ai](https://github.com/unclecode/crawl4ai)
- **Stars:** ~72,500 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, latest release v0.9.1 (2026-07-08)

An async Python web crawler purpose-built for AI pipelines: it renders JavaScript-heavy pages via a browser, then converts the result into clean, LLM-ready Markdown or structured JSON, with no API key required. Supports browser automation (auth, proxies, stealth), LLM-assisted structured extraction, and a Dockerized FastAPI deployment for running it as a service.

Best for: bulk-fetching and normalizing web content for a RAG index, agent tool, or dataset, especially when pages require JS rendering that a plain HTTP fetch can't handle.

**Installation:**
```bash
pip install -U crawl4ai
crawl4ai-setup
```

**Usage example:**
```python
import asyncio
from crawl4ai import AsyncWebCrawler

async def main():
    async with AsyncWebCrawler() as crawler:
        result = await crawler.arun(url="https://example.com")
        print(result.markdown)

asyncio.run(main())
```

## Notes
- JS-rendering crawlers are resource-heavier than plain HTTP scraping (`requests`/`httpx`) — reach for a lighter-weight fetch first if the target pages are static HTML.
- Always check a target site's `robots.txt` and terms of service before crawling at scale; Apache-2.0 covers the tool's own code, not permission to scrape any given site.

## License Summary
| Repository | License |
|---|---|
| unclecode/crawl4ai | Apache-2.0 |
