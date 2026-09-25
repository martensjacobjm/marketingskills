# AI SEO Evidence Register

Every factual claim in `SKILL.md`, `platform-ranking-factors.md` and `content-patterns.md` traces to a source below. Add a new claim only after reading the primary document. Blog posts and vendor marketing are used only to locate primary sources.

Adapted from the claude-seo GEO evidence register (`skills/seo-geo/references/geo-evidence.md`, 2026-09-24). Last reviewed: 2026-09-25.

## Evidence Levels

| Tag | Level | Examples |
|-----|-------|----------|
| [V] | Vendor-documented | Google Search Central, Search Console Help, Bing Webmaster blog, OpenAI/Anthropic/Perplexity/Apple crawler docs |
| [R] | Research: peer-reviewed or preprint (preprints labeled) | GEO paper (KDD 2024); GEO critical survey (arXiv preprint) |
| [H] | Practitioner heuristic | Server-rendering critical content, sameAs consistency, visible authors/dates, off-site presence |

Only [V] findings should be presented as high priority. Vendor suffixes such as [V Google] or [V Bing] name the vendor.

## Google [V]

| Source | Date | Claim used |
|--------|------|------------|
| [Guide to Optimizing for Generative AI Features](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide) | Last updated 2026-07-10 | AI features rooted in core ranking/quality systems (RAG, query fan-out); "still SEO"; llms.txt / AI text / Markdown files not used by Google Search; no chunking, "no ideal page length"; no need to write "in a specific way just for generative AI search"; AI systems "can understand synonyms and general meanings"; fan-out page creation = scaled content abuse; inauthentic mentions not helpful; "no special schema.org markup"; semantic HTML a good idea, not required; JS processed if not blocked; images/video; Merchant Center + Google Business Profile; eligibility = indexed + snippet-eligible; non-commodity example ("7 Tips for First-Time Homebuyers" vs "Why We Waived the Inspection..."); "No third-party tool has access to our internal ranking or AI systems" |
| [AI features and your website](https://developers.google.com/search/docs/appearance/ai-features) | Last updated 2025-12-10 | AI Overviews / AI Mode counted in Performance report (Web); Googlebot is the robots.txt control; nosnippet / data-nosnippet / max-snippet / noindex limit display |
| [Search generative AI control (Help 16908024)](https://support.google.com/webmasters/answer/16908024) | All sites 2026-08-31 | Settings > Search generative AI; include/exclude AI Overviews, AI Mode, Discover gen-AI; default Include; separate from Google-Extended |
| [Gen AI performance reports (blog)](https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports) | 2026-06-03 | Impressions; Pages, Countries, Devices, Dates; no query dimension or click metric documented |
| [Gen AI performance report (Help 16984139)](https://support.google.com/webmasters/answer/16984139) | Fetched 2026-09 | Covers AI Overviews + AI Mode; export button; 1,000-row limit |
| [Search Analytics API: query](https://developers.google.com/webmaster-tools/v1/searchanalytics/query) | 2026-08-11 | No generative-AI `type` value (so the report is export-only; inference from absence) |
| [Search Central changelog](https://developers.google.com/search/updates) | 2023-2026 | FAQ rich result no longer shown from 2026-05-07, docs removed 2026-06-15; HowTo rich result removed (2023); sitelinks search box removed (2024-11); 2026-06-15 llms.txt clarification |
| [Google common crawlers](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) | 2026-07-14 | Google-Extended: control token, no own UA; no effect on Search inclusion or ranking; governs Gemini training and grounding |
| [Structured data generated with JavaScript](https://developers.google.com/search/docs/appearance/structured-data/generate-structured-data-with-javascript) | Via claude-seo schema register | JS-generated Product markup "can make Shopping crawls less frequent and less reliable" |
| [Spam policies](https://developers.google.com/search/docs/essentials/spam-policies) | Last updated 2026-08-28 (fetched 2026-09-25) | Scaled content abuse: "many pages are generated for the primary purpose of manipulating search rankings and not helping users"; doorway abuse; keyword stuffing |
| [Creating helpful content](https://developers.google.com/search/docs/fundamentals/creating-helpful-content) | Via claude-seo ranking-signals register | "E-E-A-T itself isn't a specific ranking factor" |
| [Google I/O 2026 keynote](https://blog.google/innovation-and-ai/sundar-pichai-io-2026/) | 2026 | AI Overviews 2.5B+ monthly active users; AI Mode 1B+ monthly users |

## Other AI Search Vendors [V]

| Source | Claim used |
|--------|------------|
| [OpenAI crawlers](https://developers.openai.com/api/docs/bots) | OAI-SearchBot = ChatGPT search inclusion (~24h to take effect); GPTBot = training only; ChatGPT-User = user-initiated, robots.txt "may not apply", not used for search inclusion; settings independent |
| [Anthropic crawlers](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler) | ClaudeBot = training; Claude-User = user-initiated; Claude-SearchBot = search indexing; `anthropic-ai` not listed |
| [Perplexity crawlers](https://docs.perplexity.ai/docs/resources/perplexity-crawlers) | PerplexityBot = search results, not training; Perplexity-User "generally ignores robots.txt" |
| [Apple Applebot](https://support.apple.com/en-us/119829) | Applebot = Spotlight/Siri/Safari; Applebot-Extended = training opt-out; nosnippet opts out of world-knowledge answers; follows Googlebot rules if not named; may render JS |
| [Common Crawl CCBot](https://commoncrawl.org/ccbot) | Block with `User-agent: CCBot` |

## Microsoft Bing [V]

| Source | Date | Claim used |
|--------|------|------------|
| [Bing Chat content controls](https://blogs.bing.com/webmaster/september-2023/Announcing-new-options-for-webmasters-to-control-usage-of-their-content-in-Bing-Chat) | 2023-09-22 | NOCACHE: URL/title/snippet only; NOARCHIVE: excluded; both = NOCACHE; same tags govern training of Microsoft generative AI models. Names Bing Chat only; Copilot by inference |
| [AI Performance in Bing Webmaster Tools](https://blogs.bing.com/webmaster/2026/2/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview/) | 2026-02 (preview) | Total Citations, Average Cited Pages, grounding queries (sampled), page-level citations; "Clear headings, tables, and FAQ sections help surface key information"; "Examples, data, and cited sources help build trust"; consistent entities across formats; IndexNow; Bing Places keeps details "current and eligible for inclusion in AI-generated responses" |
| [New AI visibility insights](https://blogs.bing.com/search/2026/6/New-AI-Visibility-Insights-in-Bing-Webmaster-Tools-Intents-Topics-Citation-Share-Compare/) | 2026-06-16 (preview) | Intents, Topics, Citation Share (share of citations per grounding query; not traffic or quality), Compare |

## Standards

| Source | Claim used |
|--------|------------|
| [llmstxt.org](https://llmstxt.org/) | A proposal (2024, revised 2026), not a ratified standard |
| [HTTP Archive Web Almanac 2025, SEO](https://almanac.httparchive.org/en/2025/seo) | llms.txt on 2.13% of desktop / 2.10% of mobile sites |

Not confirmed: that any non-Google engine reads llms.txt for crawling, ranking or citation.

## Research [R]

- **Aggarwal et al., "GEO: Generative Engine Optimization"**, KDD 2024, [arXiv 2311.09735](https://arxiv.org/abs/2311.09735) (peer-reviewed). Up to 40% visibility gain on GEO-bench; best methods Cite Sources, Quotation Addition, Statistics Addition; keyword stuffing little or no improvement. **Caveat (always state it):** measured with the source already in a fixed context.
- **Martinez, GEO critical survey 2023-2026**, [arXiv 2607.14035](https://arxiv.org/abs/2607.14035) (preprint, single author, 45 studies). Gains "conditional on a source already being present in a fixed context"; "topical relevance and context position are the most reproducible levers"; "citation-oriented rewrites can impair retrieval"; "no reviewed technique shows a stable, longitudinal, cross-platform causal effect on organic discoverability".

## Removed Claims (no primary source found)

Removed from this skill on 2026-09-25. Do not re-introduce without a fetched primary source:

- "AI Overviews appear in ~45% of Google searches"; "45%+ of Google searches"
- "AI Overviews reduce clicks to websites by up to 58%"; "over 60% of Google searches end without a click"
- "Brands are 6.5x more likely to be cited via third-party sources"; "Optimized content gets cited 3x more often"
- Per-method GEO boosts presented as general facts (+40% cite sources, +37% statistics, +30% quotations, +25% authoritative tone, +20% clarity, +18% technical terms, +15% vocabulary, +15-30% fluency, "-10% keyword stuffing", "up to 115% for low-ranking sites", "15-30%" statistics boost)
- "Content with proper schema shows 30-40% higher AI visibility"; schema as "the single biggest lever" for AI Overviews
- "132% visibility boost" for citations and "89%" for authoritative tone
- "Only about 15% of AI Overview sources overlap with organic results"; "a page can get cited even if it ranks on page 2 or 3"
- SE Ranking domain-authority shares (40% / 35% / 25%, "8.4 citations", "350K+ referring domains")
- ZipTie "content-answer fit" 55% / 12% / 14%
- "Content updated within 30 days cited 3.2x more"
- Citation shares: Wikipedia 7.8%, Reddit 1.8%, Forbes 1.1% of ChatGPT citations; content-type citation shares (comparisons ~33%, guides ~15%, research ~12%, etc.)
- "ChatGPT search draws from a Bing-based index"; "Claude uses Brave Search"; "Perplexity combines its own index with Google's", curated domain boosts, time-decay algorithm, PDF and publishing-velocity preferences
- "Perplexity cites pages with FAQ schema more often"; FAQPage / HowTo schema for AI citations
- "Copilot: LinkedIn/GitHub boosts; sub-2-second page speed threshold"
- "GPTBot powers ChatGPT search" / "allow GPTBot for AI visibility"; `anthropic-ai` as a current token; "Google-Extended controls AI Overviews"
- "Keep answer passages to 40-60 words"; "FAQ answers 50-100 words"; "voice answers under 30 words"; "definition in first paragraph"; question-matching headings as an AI rule; "AI systems extract passages, not pages"
- llms.txt or `/pricing.md` as files to add for AI visibility
- Content-pattern examples with unsourced figures ("70% of web traffic from mobile / 24% higher bounce", "HubSpot: 77% more backlinks", "1,500-2,500 words optimal", "featured snippets within 2-4 weeks") and an attributed expert quote that could not be verified
