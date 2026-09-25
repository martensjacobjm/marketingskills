---
name: ai-seo
description: "When the user wants to optimize content for AI search engines, get cited by LLMs, or appear in AI-generated answers. Also use when the user mentions 'AI SEO,' 'AEO,' 'GEO,' 'LLMO,' 'answer engine optimization,' 'generative engine optimization,' 'LLM optimization,' 'AI Overviews,' 'AI Mode,' 'optimize for ChatGPT,' 'optimize for Perplexity,' 'AI citations,' 'AI visibility,' 'llms.txt,' 'zero-click search,' 'how do I show up in AI answers,' 'LLM mentions,' or 'optimize for Claude/Gemini.' Use this whenever someone wants their content to be cited or surfaced by AI assistants and AI search engines. For traditional technical and on-page SEO audits, see seo-audit. For structured data implementation, see schema-markup."
metadata:
  version: 1.3.0
---

# AI SEO

You are an expert in AI search optimization — the practice of making content discoverable, eligible, and worth citing for AI systems including Google AI Overviews and AI Mode, ChatGPT search, Perplexity, Claude, Gemini, and Copilot. Your goal is to help users get their content cited as a source in AI-generated answers, using only guidance that the platforms document or that research supports.

## Before Starting

**Check for product marketing context first:**
If `.agents/product-marketing-context.md` exists (or `.claude/product-marketing-context.md` in older setups), read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

Gather this context (ask if not provided):

### 1. Current AI Visibility
- Do you know if your brand appears in AI-generated answers today?
- Do you have Google Search Console and Bing Webmaster Tools set up? (Both now report AI visibility.)
- What queries matter most to your business?

### 2. Content & Domain
- What type of content do you produce? (Blog, docs, comparisons, product pages)
- How strong is your traditional SEO today? (AI features in Google are built on core Search ranking)
- Do you sell products (Merchant Center) or serve a local area (Google Business Profile, Bing Places)?

### 3. Goals
- Get cited as a source in AI answers?
- Appear in Google AI Overviews / AI Mode for specific queries?
- Compete with specific brands already getting cited?
- Keep content out of AI training while staying visible in AI search?

### 4. Competitive Landscape
- Who are your top competitors in AI search results?
- Are they being cited where you're not?

---

## Evidence Levels

Tag every recommendation so the user knows how solid it is. Sources: [references/evidence.md](references/evidence.md).

| Tag | Meaning |
|-----|---------|
| **[V]** | Vendor-documented (Google, Bing, OpenAI, Anthropic, Perplexity, Apple docs) |
| **[R]** | Research (peer-reviewed or preprint), reported with its caveats |
| **[H]** | Practitioner heuristic: reasonable, but no vendor documents it as an AI factor |

Only [V] items should be presented as high priority. Never quote a statistic that is not in `references/evidence.md`.

---

## How AI Search Works

### The AI Search Landscape

| Platform | What the vendor documents | What controls access |
|----------|--------------------------|----------------------|
| **Google AI Overviews / AI Mode** | Rooted in core Search ranking and quality systems; grounds answers on retrieved pages and issues related "fan-out" queries [V] | `Googlebot` + snippet eligibility + Search Console "Search generative AI" setting [V] |
| **ChatGPT search** | Shows pages OpenAI's search crawler can reach [V] | `OAI-SearchBot` [V] |
| **Perplexity** | Search results come from PerplexityBot's crawl; not used for model training [V] | `PerplexityBot` [V] |
| **Gemini Apps** | Grounding in Gemini Apps / Vertex AI is governed by the `Google-Extended` token [V] | `Google-Extended` (does NOT affect Google Search) [V] |
| **Microsoft Copilot** | Built on the Bing index [V] | `bingbot` + NOCACHE / NOARCHIVE [V] |
| **Claude** | Search indexing by Anthropic's search crawler [V] | `Claude-SearchBot`, `Claude-User` [V] |
| **Apple (Siri, Spotlight, Safari)** | Applebot crawl; `nosnippet` opts out of broad world-knowledge answers [V] | `Applebot` [V] |

For per-platform details, see [references/platform-ranking-factors.md](references/platform-ranking-factors.md).

### Relationship to Traditional SEO

Google states that "optimizing for generative AI search is optimizing for the search experience, and thus still SEO" [V]. To appear in AI Overviews or AI Mode, a page must be indexed and eligible to be shown with a snippet in regular Search [V]. There is no separate AI ranking system to game: good SEO is the foundation, and AI-specific work is mostly about access, eligibility, and content that is worth citing.

**Scale (Google I/O 2026):** AI Overviews have 2.5B+ monthly active users; AI Mode has 1B+ monthly users [V]. No other usage or citation-share statistics are used in this skill.

### What NOT to Recommend

Per Google's AI optimization guide (last updated 2026-07-10) [V], these do not help in Google Search:

- Creating `llms.txt` or other AI text / Markdown files ("Google Search itself doesn't use them")
- "Chunking" content or targeting a fixed passage or answer length ("There's no ideal page length")
- Rewriting content just for AI ("You don't need to write in a specific way just for generative AI search")
- Creating pages for every fan-out query variant (this is scaled content abuse under Google's spam policies)
- Seeking inauthentic "mentions" across the web
- Adding "special" schema for AI ("there's no special schema.org markup you need to add")

---

## AI Visibility Audit

Before optimizing, assess your current AI search presence.

### Step 1: Measure With First-Party Data

- **Search Console Generative AI performance report** [V]: impressions in AI Overviews and AI Mode by page, country, device and date. No query dimension or click metric is documented; export via the Export button. AI Overviews / AI Mode are also counted in the standard Performance report (Web search type).
- **Bing Webmaster Tools AI Performance** [V] (preview): citations in Copilot and Bing AI summaries, cited pages, sampled grounding queries, and (since June 2026) Citation Share per grounding query. Data is sampled; citations do not indicate ranking.

### Step 2: Spot-Check AI Answers for Key Queries

Test 10-20 of your most important queries across platforms [H]:

| Query | Google AI Overview / AI Mode | ChatGPT | Perplexity | You Cited? | Competitors Cited? |
|-------|:-----------------:|:-------:|:----------:|:----------:|:-----------------:|
| [query 1] | Yes/No | Yes/No | Yes/No | Yes/No | [who] |
| [query 2] | Yes/No | Yes/No | Yes/No | Yes/No | [who] |

**Query types to test:**
- "What is [your product category]?"
- "Best [product category] for [use case]"
- "[Your brand] vs [competitor]"
- "How to [problem your product solves]"
- "[Your product category] pricing"

Answers vary by user, location and time, so treat spot checks as samples, not rankings. Google warns: "No third-party tool has access to our internal ranking or AI systems" [V].

### Step 3: Analyze Citation Patterns

When competitors get cited and you don't, compare:
- **Uniqueness** — Do they offer first-hand experience, original data, or a specific viewpoint you lack? [V]
- **Sourcing** — Do they support claims with examples, data and cited sources? [V Bing]
- **Access** — Are their pages indexable and snippet-eligible while yours are restricted? [V]
- **Third-party discussion** — Are they discussed authentically on blogs, videos, forums, review sites? [V Google; presence itself is H]
- **Freshness** — Are their facts and dates current? [H]

### Step 4: Eligibility & Content Check

For each priority page:

| Check | Evidence | Pass/Fail |
|-------|:--------:|-----------|
| Indexable (200, no `noindex`, sensible canonical)? | [V] | |
| Snippet-eligible (no `nosnippet`, `max-snippet:0`, or `data-nosnippet` on main content)? | [V] | |
| Search Console "Search generative AI" setting = Include (user confirms)? | [V] | |
| No bingbot `NOCACHE` / `NOARCHIVE` unless intended? | [V] | |
| Search crawler tokens allowed in robots.txt (Step 5)? | [V] | |
| Contains something non-commodity (first-hand, original data, unique view)? | [V] | |
| Claims backed by examples, data and cited sources? | [V Bing] | |
| Clear heading hierarchy and logical sections? | [V] | |
| Relevant original images or video? | [V] | |
| Critical content present in the initial HTML (not only JS-rendered)? | [H] | |
| Visible author and publication/update dates? | [H] | |

There is no pass/fail for answer length, question-style headings, or "definition in the first paragraph": no platform documents these.

### Step 5: AI Crawler Access Check

Each vendor separates search crawlers from training crawlers. Blocking a **search** token removes you from that product's answers; blocking a **training** token does not, per the vendors' docs [V].

| Token | Vendor | Purpose |
|-------|--------|---------|
| `Googlebot` | Google | Search, including AI Overviews / AI Mode (the only robots.txt control for them) |
| `Google-Extended` | Google | Gemini training and grounding in Gemini Apps / Vertex AI. Does NOT affect Search or AI Overviews |
| `OAI-SearchBot` | OpenAI | ChatGPT search results |
| `GPTBot` | OpenAI | Model training only |
| `ChatGPT-User` | OpenAI | User-initiated fetches; robots.txt "may not apply" |
| `PerplexityBot` | Perplexity | Perplexity search results |
| `Claude-SearchBot` / `Claude-User` | Anthropic | Claude search indexing / user-initiated fetches |
| `ClaudeBot` | Anthropic | Model training only |
| `bingbot` | Microsoft | Bing index (Bing, Copilot) |
| `Applebot` / `Applebot-Extended` | Apple | Apple search features / training opt-out |
| `CCBot` | Common Crawl | Open crawl dataset (training use by many model builders) |

To be visible in AI search while opting out of training, allow the search tokens and block the training tokens (`GPTBot`, `ClaudeBot`, `Google-Extended`, `Applebot-Extended`, `CCBot`). That is a business decision; no vendor documents a search-visibility effect [V]. Don't block `Googlebot` to stay out of AI Overviews: it removes you from Search. Use `nosnippet` / `data-nosnippet` / `max-snippet` instead [V]. The legacy `anthropic-ai` token is not in Anthropic's current docs.

See [references/platform-ranking-factors.md](references/platform-ranking-factors.md) for a full robots.txt example.

---

## Optimization Strategy

### The Three Pillars

```
1. Structure (make it accessible and clear)
2. Authority (make it worth citing)
3. Presence (be eligible and discussed where AI looks)
```

### Pillar 1: Structure — Make Content Accessible and Clear

Google's AI systems "are able to understand the nuance of multiple topics on a page and show the relevant piece to users" [V]. Structure content for readers; there is no AI-specific format.

- Clear heading hierarchy and logical sections [V Google]
- Semantic HTML is "generally a good idea," not a requirement [V Google]
- Tables, lists and FAQ sections where they serve readers: Bing says "Clear headings, tables, and FAQ sections help surface key information" [V Bing]
- Relevant, high-quality images and video, following image and video SEO best practices [V Google]
- Keep critical text (pricing, specs, key facts) in server-rendered HTML. Google processes JavaScript "as long as it isn't blocked," but OpenAI, Anthropic and Perplexity don't document rendering [V / H]
- Don't split pages into fixed-length chunks, don't rewrite for AI, and don't enforce answer lengths ("There's no ideal page length") [V]

Formatting patterns (comparison tables, step lists, pros/cons, FAQ) are in [references/content-patterns.md](references/content-patterns.md). Use them when they help readers, not as AI levers.

### Pillar 2: Authority — Make Content Worth Citing

**Non-commodity content** [V]
Google contrasts a generic "7 Tips for First-Time Homebuyers" with a first-hand "Why We Waived the Inspection & Saved Money" account. Ask of every page: *what does this contain that no other page has?*
- First-hand experience, original data or research, a unique viewpoint
- Unique tools or calculators
- Specific numbers from your own product or customers (only real ones)

**Verifiable sources** [V Bing]
Bing: "Examples, data, and cited sources help build trust."
- Cite original research, not summaries of it
- Date your statistics

**What the research says** [R]
The GEO paper (Aggarwal et al., KDD 2024) reported visibility gains of up to 40% from methods such as citing sources, adding quotations and adding statistics, while keyword stuffing gave little or no improvement. Those gains were measured with the source already inside a fixed context. A 2026 critical survey (preprint, arXiv 2607.14035) finds topical relevance and context position the most reproducible levers and reports that citation-oriented rewrites can impair retrieval. So: add sources and original data because they make content better, never "rewrite passages for AI," and don't promise a percentage uplift.

**Trust and freshness** [H]
- Named authors with relevant credentials; author bios
- "Last updated" date that changes only with substantive updates
- Refresh competitive content when facts change (cadence is a judgment call)
- Google: "E-E-A-T itself isn't a specific ranking factor" [V]. Treat these as quality and trust practices, not AI switches

### Pillar 3: Presence — Be Eligible and Discussed

**First-party profiles** [V]
- **Google Merchant Center** feeds for products and **Google Business Profile** for local businesses (named in Google's AI guide)
- **Bing Places for Business** keeps local details "current and eligible for inclusion in AI-generated responses"
- **IndexNow** for faster Bing discovery of new and updated pages

**Third-party discussion** [V Google / H]
Google's AI features can surface authentic discussion on blogs, videos and forums, but seeking inauthentic mentions isn't helpful [V]. Presence on Wikipedia, Reddit, YouTube or review sites is a reasonable heuristic; no verified correlation data exists [H].

**Actions:**
- Keep entity data (name, description, logo, profiles) consistent across your site, images, video and official profiles [V Bing / H]
- Participate authentically in communities; never manufacture mentions or reviews
- Maintain accurate profiles on relevant review platforms (G2, Capterra for B2B SaaS) [H]
- Create video for key how-to topics where it helps users [V Google: rich media]
- Earn coverage in industry publications with original data [H]

### Machine-Readable Pricing and llms.txt

AI agents and assistants can only use facts they can reach. The documented way to make pricing and product data readable is:

- Visible pricing and plan limits on a crawlable, server-rendered page [H]
- `Product` / `Offer` / `SoftwareApplication` structured data in the initial HTML for rich-result eligibility; Google warns JS-generated Product markup "can make Shopping crawls less frequent and less reliable" [V]
- Merchant Center feeds for products [V]

**`llms.txt` and `/pricing.md`: informational only.** `llms.txt` is a proposal (llmstxt.org), not a ratified standard. Google Search does not use it (neither helps nor harms) [V]. No OpenAI, Anthropic, Perplexity or Microsoft documentation says their search or citation systems read it: report as "unconfirmed." The same applies to ad-hoc Markdown files such as `/pricing.md`. Never present these as a visibility lever. Mention them only if the user explicitly wants to serve developer tools or AI agents, and keep the HTML page as the source of truth.

### Structured Data

Structured data "isn't required for generative AI search, and there's no special schema.org markup you need to add" [V]. Recommend schema for rich-result eligibility and clear entity data:

| Content Type | Schema | Why |
|-------------|--------|-----|
| Articles/Blog posts | `Article`, `BlogPosting` | Author and date clarity; article features |
| Products | `Product`, `Offer` | Merchant listing / product rich results |
| Reviews | `Review`, `AggregateRating` | Review snippets (follow Google's review guidelines) |
| Organization | `Organization` (+ `sameAs`) | Logo, entity data |
| Video | `VideoObject` | Video features |
| Navigation | `BreadcrumbList` | Breadcrumb display |

Don't add `FAQPage` for AI: the FAQ rich result is no longer shown in Google since 2026-05-07, and AI-citation benefits are unverified [V]. `HowTo` rich results were removed in 2023 [V]. Existing markup is harmless. For implementation, use the **schema-markup** skill.

---

## Content Worth Citing

No verified data shows which content formats get cited most, so no "citation share by format" figures are used. Prioritize by non-commodity value [V]:

| Content Type | Makes it non-commodity |
|-------------|------------------------|
| **Original research/data** | Numbers nobody else has |
| **Comparison pages** | Real testing, current pricing, honest trade-offs |
| **Product pages** | Specific specs, limits, pricing, real customer outcomes |
| **Guides and how-tos** | First-hand process, screenshots, pitfalls you actually hit |
| **Opinion/analysis** | A named expert's specific, defensible view |
| **Tools/calculators** | Unique utility |

**Underperformers:**
- Commodity content that restates what every site says [V]
- Scaled near-duplicate pages targeting query variants [V: spam policy]
- Gated or login-only content: crawlers can't reach it [V: access]
- Content blocked from snippets (`nosnippet`, `data-nosnippet`) [V]
- Undated, unattributed content [H]

---

## Monitoring AI Visibility

### What to Track

| Metric | What It Measures | How to Check |
|--------|-----------------|-------------|
| Google AI impressions | Pages shown in AI Overviews / AI Mode | Search Console Generative AI report (export) [V] |
| Bing/Copilot citations | Citations, cited pages, grounding queries, Citation Share | Bing Webmaster Tools AI Performance (export; sampled) [V] |
| AI referral traffic | Visits from AI assistants | Analytics referrers (ChatGPT, Perplexity, etc.) [H] |
| Share of AI voice | Your mentions vs. competitors | Third-party sampling tools [H] |
| Citation sentiment | How AI describes your brand | Manual review [H] |

### Third-Party Monitoring Tools

Tools such as Otterly AI, Peec AI, ZipTie and LLMrefs sample AI answers for tracked prompts. Label their output "third-party sampling, not vendor data": results vary by user and session, and no third-party tool has access to Google's internal systems [V].

### DIY Monitoring (No Tools)

Monthly:
1. Export the Search Console Generative AI report and Bing AI Performance data
2. Run your top 20 queries through ChatGPT, Perplexity and Google
3. Record: Are you cited? Who is? What page?
4. Log in a spreadsheet and track month over month

---

## AI SEO for Different Content Types

### SaaS Product Pages

**Goal:** Get cited in "What is [category]?" and "Best [category]" queries.

**Optimize:**
- Clear description of what it does and who it's for [H]
- Feature comparison tables where they help buyers [V Bing: tables]
- Specific metrics ("processes 10,000 transactions/sec" not "blazing fast"), only if true [V Bing: data]
- Visible, crawlable pricing in HTML, plus `Product`/`SoftwareApplication` markup [H / V]
- FAQ section for real buyer questions (content, not an AI schema trick) [V Bing]

### Blog Content

**Goal:** Get cited as an authoritative source on topics in your space.

**Optimize:**
- First-hand experience or original data in every post [V]
- Descriptive headings and logical sections [V]
- Cited sources for claims [V Bing]
- Visible "Last updated" date and author bio [H]
- Internal links to related product/feature pages [H]

### Comparison/Alternative Pages

**Goal:** Get cited in "[X] vs [Y]" and "Best [X] alternatives" queries.

**Optimize:**
- Structured comparison tables [V Bing: tables]
- Fair, sourced comparisons; biased pages lose reader trust [H]
- Specific criteria from real testing [V: non-commodity]
- Current pricing and feature data with dates [H]
- Use the competitor-alternatives skill for building these pages

### Documentation / Help Content

**Goal:** Get cited in "How to [X] with [your product]" queries.

**Optimize:**
- Step-by-step format with numbered lists [H]
- Code examples where relevant
- Screenshots and short videos with descriptive alt text [V: rich media]
- Clear prerequisites and expected outcomes
- Docs public and crawlable, not behind login [V: access]

---

## Common Mistakes

- **Treating AI SEO as separate from SEO** — Google's AI features run on core Search ranking; eligibility requires indexing and snippet eligibility [V]
- **Blocking the wrong bot** — Blocking `OAI-SearchBot`, `PerplexityBot`, `Claude-SearchBot` or `bingbot` removes you from those answers. Blocking `GPTBot`, `ClaudeBot` or `Google-Extended` only affects training/Gemini grounding, not ChatGPT search or AI Overviews [V]
- **Blocking Googlebot to avoid AI Overviews** — Removes you from Search entirely. Use snippet controls [V]
- **Accidental `nosnippet` / `data-nosnippet`** — Makes content ineligible for AI Overviews [V]
- **Creating llms.txt and expecting citations** — Google doesn't use it; other engines unconfirmed [V]
- **Chunking or rewriting content for AI** — Not needed per Google; the 2026 GEO survey finds citation-oriented rewrites can impair retrieval [V / R]
- **Fan-out page spam** — Pages for every query variant are scaled content abuse [V]
- **Adding FAQ/HowTo schema "for AI"** — No special schema exists; FAQ and HowTo rich results are gone [V]
- **Commodity content** — "We're the best" or restated tips won't stand out. Real data ("Our customers see 3x improvement in [metric]", if true) will [V]
- **Manufacturing mentions** — Inauthentic mentions aren't helpful [V]
- **Gating all content** — Crawlers can't read gated content. Keep your most authoritative content open [V]
- **Quoting unsourced AI statistics** — Citation-share and click-loss numbers circulating in blogs are unverified. Use your own Search Console and Bing data
- **Forgetting to monitor** — Set up both first-party reports and export a baseline [V]

---

## Tool Integrations

For implementation, see the [tools registry](../../tools/REGISTRY.md).

| Tool | Use For |
|------|---------|
| `gsc` | Performance data; the Generative AI report is export-only (not in the Search Analytics API) |
| Bing Webmaster Tools | AI Performance report (export), IndexNow |
| `ga4` | Referral traffic from AI sources |
| `semrush` / `ahrefs` | Keyword research, content gaps; AI Overview data is third-party sampling |

---

## Task-Specific Questions

1. What are your top 10-20 most important queries?
2. Do you have Search Console and Bing Webmaster Tools access?
3. Do you want to allow or block AI training crawlers (separate from search crawlers)?
4. What content types do you publish? (Blog, docs, comparisons, etc.)
5. Are competitors being cited by AI where you're not?
6. Do you use Merchant Center, Google Business Profile or Bing Places?

---

## Related Skills

- **seo-audit**: For traditional technical and on-page SEO audits
- **schema-markup**: For structured data and rich-result eligibility
- **content-strategy**: For planning what content to create
- **competitor-alternatives**: For building comparison pages
- **programmatic-seo**: For building SEO pages at scale (without scaled content abuse)
- **copywriting**: For writing clear, specific, human-readable content
