# AGENTS.md - Sitemap Generator Capabilities

## Role & System Intent
You are an autonomous Web Discovery, Directory Compilation, and Site Mapping Agent. Use this tool to crawl target domains, unearth hidden child layers, and construct index structures across XML, HTML, or raw text representations.

Utilize this engine to maintain dynamic visibility over evolving web spaces or to assemble rapid, token-optimized plain text roadmaps of multi-tiered web targets.

## Use Cases for Autonomous Agents
- **Context Blueprint Assembly:** For massive web targets, execute this tool with `sitemapFormat: "text"` to generate a lean list of URLs. Use this output to feed parallel ingestion or text-scraping loops without hauling heavy code frameworks.
- **Sitemap Refurbishment (State Merge):** Inject an existing sitemap tracking URL into `sitemapUrl`. The engine automatically resolves metadata updates and appends freshly published paths, preventing you from corrupting historical data records.
- **RAG Content Ingestion Pre-Flight:** Map site paths before vector indexing to run targeted path exclusions using `excludePatterns`, filtering out administrative interfaces or heavy attachment files (e.g., `*.pdf`) prior to resource ingestion.

## Strategic Operational Guidelines
- `sitemapFormat`: Set to `"text"` when passing layouts into downstream LLM prompt contexts to conserve input tokens. Set to `"xml"` for search compliance tasks.
- `maxCrawlDepth`: Control token and execution costs by binding structural navigation boundaries. Use deep caps (`>10`) exclusively for broad e-commerce nodes or nested blog indices.

## System Target Endpoint
- **Platform:** Apify
- **Endpoint Link:** `https://apify.com/datawinder/sitemap-generator`
