# How Each AI Platform Picks Sources

What each AI search platform documents about crawling, eligibility and controls. Every claim here traces to a vendor document listed in [evidence.md](evidence.md). Evidence tags: [V] vendor-documented, [R] research, [H] heuristic.

No platform publishes a list of AI "ranking factors" or citation weights. Earlier versions of this file quoted third-party correlation studies (domain-authority shares, "content-answer fit" percentages, freshness multipliers, citation shares for Wikipedia/Reddit, AI Overview/organic overlap figures). None could be traced to a primary source, so they were removed. See the "Removed claims" list in [evidence.md](evidence.md).

---

## The Fundamentals

Every AI search platform shares three baseline requirements:

1. **The platform's search crawler must be allowed** — Each vendor uses its own search token (table below). Block it and you drop out of that product's answers [V].
2. **The page must be indexable and snippet-eligible** — For Google, a page must be "indexed and eligible to be shown in Google Search with a snippet" [V]. For Bing/Copilot, NOCACHE and NOARCHIVE limit or exclude use in AI answers [V].
3. **The content must be worth citing** — First-hand experience, original data, a unique viewpoint, verifiable sources [V Google, V Bing].

There is no required format: Google says no chunking, "no ideal page length," and no need to "write in a specific way just for generative AI search" [V].

---

## Google AI Overviews and AI Mode

**How it works** [V]: Rooted in Google's core Search ranking and quality systems. Answers are grounded on retrieved pages (retrieval-augmented generation), and Google issues related sub-queries ("query fan-out") to find supporting pages. Google: "optimizing for generative AI search is optimizing for the search experience, and thus still SEO."

**Eligibility and controls** [V]:
- Indexed and snippet-eligible. `nosnippet`, `data-nosnippet`, `max-snippet` and `noindex` limit display
- `Googlebot` is the only robots.txt control. `Google-Extended` does NOT affect Search inclusion or ranking
- Search Console > Settings > **Search generative AI**: Include (default) or exclude from AI Overviews, AI Mode and Discover gen-AI features

**What to focus on:**
- Normal SEO fundamentals: crawlable, indexable, helpful pages [V]
- Non-commodity content: first-hand experience, original data or research, a unique viewpoint [V]
- Clear headings and sections; semantic HTML is "generally a good idea," not required [V]
- Relevant images and video following image/video SEO best practices [V]
- Merchant Center for products and Google Business Profile for local businesses [V]
- Structured data for rich-result eligibility only: "there's no special schema.org markup you need to add" [V]

**Don't:** create llms.txt for Google, chunk content, rewrite for AI, build pages for every fan-out variant (scaled content abuse), or seek inauthentic mentions [V].

**Measure:** Search Console Generative AI performance report (impressions by page, country, device, date; export only) [V].

---

## ChatGPT Search (OpenAI)

**Controls** [V]:
- `OAI-SearchBot`: determines whether pages can be shown in ChatGPT search answers. Changes take about 24 hours
- `GPTBot`: foundation-model training only
- `ChatGPT-User`: user-initiated fetches; robots.txt "may not apply"; not used for search inclusion
- OpenAI documents the settings as independent: blocking `GPTBot` does not remove you from ChatGPT search

**What to focus on:** Allow `OAI-SearchBot`. OpenAI documents no content-selection factors, so apply the fundamentals above. OpenAI does not document JavaScript rendering, so keep critical content in the initial HTML [H].

---

## Perplexity

**Controls** [V]:
- `PerplexityBot`: surfaces sites in Perplexity search results; not used for model training
- `Perplexity-User`: user-initiated fetches; "generally ignores robots.txt"

**What to focus on:** Allow `PerplexityBot`. Perplexity documents no content-selection factors. Critical content in initial HTML [H].

---

## Microsoft Copilot and Bing AI Summaries

**Controls** [V]:
- `bingbot` crawls for the Bing index, which Copilot and Bing AI summaries draw on
- `NOCACHE` (robots meta or `<meta name="bingbot">`): only URL, title and snippet may be used in chat answers
- `NOARCHIVE`: excluded from chat answers. Both tags present = treated as NOCACHE
- The same tags govern training of Microsoft's generative AI foundation models
- Documented for Bing Chat (2023-09-22); application to Copilot is an inference

**Bing's content guidance** [V Bing] (AI Performance announcement, 2026-02):
- "Clear headings, tables, and FAQ sections help surface key information"
- "Examples, data, and cited sources help build trust"
- Describe the same entities consistently across text, images and video
- Use IndexNow so new and updated content is discovered quickly
- Bing Places for Business keeps local details "current and eligible for inclusion in AI-generated responses"

**Measure:** Bing Webmaster Tools AI Performance: Total Citations, Average Cited Pages, sampled grounding queries, page-level citations; since 2026-06-16 also Intents, Topics, Citation Share and Compare. Data is sampled; citations do not indicate ranking [V].

---

## Claude (Anthropic)

**Controls** [V]:
- `Claude-SearchBot`: indexing to improve Claude's search results
- `Claude-User`: user-initiated fetches; blocking may reduce visibility for user-directed search
- `ClaudeBot`: model training only
- The legacy `anthropic-ai` token is not listed in Anthropic's current documentation

**What to focus on:** Allow `Claude-SearchBot` and `Claude-User`. Anthropic documents no content-selection factors. Critical content in initial HTML [H].

---

## Gemini Apps

**Controls** [V]: `Google-Extended` is a control token (no separate user agent) that governs use of content for Gemini training and grounding in Gemini Apps / Vertex AI. It does not affect Google Search inclusion or ranking, including AI Overviews.

---

## Apple (Siri, Spotlight, Safari)

**Controls** [V]:
- `Applebot`: Spotlight, Siri and Safari search features; follows Googlebot rules if not named in robots.txt; may render JavaScript
- `Applebot-Extended`: opt out of foundation-model training
- `nosnippet` opts a page out of Apple's broad world-knowledge answers

---

## robots.txt: Visible in AI Search, Opted Out of Training

```
# Search and user-initiated fetches: allowed
User-agent: Googlebot
User-agent: bingbot
User-agent: OAI-SearchBot
User-agent: PerplexityBot
User-agent: Claude-SearchBot
User-agent: Claude-User
User-agent: Applebot
Allow: /

# Model training: opted out (business decision)
User-agent: GPTBot
User-agent: ClaudeBot
User-agent: Google-Extended
User-agent: Applebot-Extended
User-agent: CCBot
Disallow: /
```

Blocking training tokens is a business decision; no vendor documents that it changes search visibility [V]. If you want your content used for training too, simply don't block those tokens. Don't block `Googlebot` to keep content out of AI Overviews: that removes the page from Search entirely. Use `nosnippet`, `data-nosnippet` or `max-snippet` instead [V].

Tokens such as `anthropic-ai`, `Bytespider` or `cohere-ai`: report if present, make no recommendation (purpose unverified).

---

## Where to Start

1. **Access** — Allow the search tokens for the platforms you care about; remove unintended `noindex`, `nosnippet`, `data-nosnippet` and bingbot NOARCHIVE [V]
2. **Google eligibility** — Confirm the Search Console "Search generative AI" setting is Include [V]
3. **Measurement** — Set up the Search Console Generative AI report and Bing AI Performance; export a baseline [V]
4. **Content** — Add first-hand experience and original data to priority pages; cite sources [V]
5. **Profiles** — Merchant Center, Google Business Profile, Bing Places where relevant; IndexNow for Bing [V]
6. **Trust** — Visible authors and dates; consistent entity data across site and profiles [H]

Informational only (never scored, never a quick win): `llms.txt` (not used by Google Search; unconfirmed elsewhere) and RSL licensing declarations.
