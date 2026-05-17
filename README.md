# Sitemap Generator

A high-performance web crawling and link discovery engine designed to automatically compile, validate, and update website sitemaps. 

Built with lightning-fast parsing layers, this tool crawls internal navigation patterns to export production-grade directory structures across multiple formats (**XML, HTML, Text**). It includes an advanced state-merger engine that handles existing asset updates without dropping legacy metadata.

## 🚀 Key Features

- **Multi-Format Compilations:** Generates standard schemas for modern distribution arrays:
  - **XML:** Fully compliant with Google, Bing, and sitemaps.org protocols.
  - **HTML:** Responsive, user-facing discovery layout with embedded structural titles.
  - **Text:** Ultra-clean, line-separated text files optimized for programmatic AI parsing.
- **Stateful Sitemap Merging:** Ingests your existing `sitemap.xml` file, overlays fresh crawl metadata, and cleanly appends newly discovered assets while preserving unchanged historical routes.
- **Smart Priority Weighting:** Automatically maps depth metrics down to proportional search hierarchy ranks (from `1.0` at the home node down to a floor of `0.1`).
- **Data Ingestion Profiling:** Delivers parallel dataset records containing clean strings for page `<title>`, calculated crawl depths, and ISO 8601 mutation states.

## 🛠 Usage & Integration

This tool runs as a managed Actor on the Apify platform.
**[Run on Apify Store →](https://apify.com/datawinder/sitemap-generator)**

### Strategic Inputs & Ingestion Targets

| Field | Type | Required | Default | Description |
| :--- | :--- | :--- | :--- | :--- |
| `websiteUrl` | String | ✅ | – | Root domain address to analyze (e.g., `https://example.com`) |
| `sitemapUrl` | String | ❌ | – | Path to live `sitemap.xml` target for historical merge states |
| `sitemapFormat` | String | ❌ | `"xml"` | Desired layout encoding: `"xml"`, `"html"`, or `"text"` |
| `maxCrawlDepth` | Integer | ❌ | `10` | Maximum structural navigation layers to trace (0-50) |
| `excludePatterns`| Array | ❌ | `[]` | Glob arrays to omit (e.g., `["/admin/*", "*.pdf"]`) |

---

## 📥 Ingestion Architecture Samples

### Scenario A: Generation and Compilation Loop
```json
{
  "websiteUrl": "[https://example.com](https://example.com)",
  "sitemapFormat": "text",
  "maxCrawlDepth": 3,
  "maxRequestsPerCrawl": 500
}
```
Scenario B: Legacy State Overlays (Merge)
```json
{
  "websiteUrl": "[https://example.com](https://example.com)",
  "sitemapUrl": "[https://example.com/sitemap.xml](https://example.com/sitemap.xml)",
  "sitemapFormat": "xml",
  "excludePatterns": ["/private/*"]
}
```
📦 Extracted Data Archetype
Every discovered path appends metadata tracking schemas directly into your target dataset records:

```json
{
  "url": "[https://example.com/docs/api](https://example.com/docs/api)",
  "title": "Developer Core API - Example Engine",
  "lastModified": "2026-05-17T23:31:00.000Z",
  "priority": "0.8",
  "depth": 2
}
```
