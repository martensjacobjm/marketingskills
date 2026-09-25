# AEO and GEO Content Patterns

Reusable content block patterns for pages that answer questions clearly. Use them because they help readers; none of them has a documented AI-citation effect.

Google: "You don't need to write in a specific way just for generative AI search," there is "no ideal page length," and content does not need to be chunked [V]. Bing: "Clear headings, tables, and FAQ sections help surface key information" and "Examples, data, and cited sources help build trust" [V]. Sources: [evidence.md](evidence.md).

Ground rules for every pattern:
- No fixed word counts for answers, paragraphs or passages (no primary source supports one)
- Only real statistics, quotes and sources. The examples below use placeholders or verified sources; never invent numbers or expert quotes
- Structure serves the reader; don't restructure a good page "for AI"

---

## Contents
- Answer Patterns (Definition Block, Step-by-Step Block, Comparison Table Block, Pros and Cons Block, FAQ Block, Listicle Block)
- Evidence Patterns (Statistic Citation Block, Expert Quote Block, Authoritative Claim Block, Key Takeaway Block, Evidence Sandwich Block)
- Domain-Specific Authority Signals (Technology, Health/Medical, Financial, Legal, Business/Marketing)
- Voice and Conversational Queries

## Answer Patterns

Formats that help readers find the answer quickly. They also suit featured snippets and AI features, but no platform documents a format requirement.

### Definition Block

Use for "What is [X]?" topics.

```markdown
## What is [Term]?

[Term] is [concise definition]. [Explanation with key characteristics]. [Context on why it matters or how it's used].
```

**Example:**
```markdown
## What is Generative Engine Optimization?

Generative Engine Optimization (GEO) is the practice of improving how often content is used as a source in AI-generated answers. The term comes from a 2024 research paper (Aggarwal et al., KDD 2024). Google describes optimizing for its generative AI features as "still SEO": the same crawling, indexing and quality systems apply.
```

### Step-by-Step Block

Use for "How to [X]" topics.

```markdown
## How to [Action/Goal]

[1-sentence overview of the process]

1. **[Step Name]**: [Clear action description]
2. **[Step Name]**: [Clear action description]
3. **[Step Name]**: [Clear action description]

[Optional: expected outcome or time estimate, if you know it]
```

**Example:**
```markdown
## How to Check Whether Your Page Is Eligible for AI Overviews

Google's AI features only use pages that are indexed and eligible to show a snippet.

1. **Inspect the URL**: Use Search Console URL Inspection to confirm the page is indexed.
2. **Check snippet directives**: Make sure the page has no `nosnippet`, `max-snippet:0`, or `data-nosnippet` on its main content.
3. **Check robots.txt**: Confirm `Googlebot` is not disallowed for the URL.
4. **Check the site setting**: In Search Console > Settings > Search generative AI, confirm "Include" is selected.
5. **Measure**: Open the Generative AI performance report and export a baseline.
```

Note: HowTo rich results were removed from Google in 2023. Use the numbered list for readers; don't add HowTo schema for Google.

### Comparison Table Block

Use for "[X] vs [Y]" topics.

```markdown
## [Option A] vs [Option B]: [Brief Descriptor]

| Feature | [Option A] | [Option B] |
|---------|------------|------------|
| [Criteria 1] | [Value/Description] | [Value/Description] |
| [Criteria 2] | [Value/Description] | [Value/Description] |
| [Criteria 3] | [Value/Description] | [Value/Description] |
| Best For | [Use case] | [Use case] |

**Bottom line**: [Recommendation based on different needs]
```

Date pricing and feature data ("as of [month year]") and say how you tested.

### Pros and Cons Block

Use for evaluation topics: "Is [X] worth it?", "Should I [X]?"

```markdown
## Advantages and Disadvantages of [Topic]

[1-sentence overview of the evaluation context]

### Pros

- **[Benefit category]**: [Specific explanation]
- **[Benefit category]**: [Specific explanation]

### Cons

- **[Drawback category]**: [Specific explanation]
- **[Drawback category]**: [Specific explanation]

**Verdict**: [Balanced conclusion with recommendation]
```

### FAQ Block

Use for pages where readers have several distinct questions.

```markdown
## Frequently Asked Questions

### [Question as customers actually ask it]?

[Direct answer first]. [Supporting context as long as the question needs].

### [Question as customers actually ask it]?

[Direct answer first]. [Supporting context as long as the question needs].
```

**Tips for FAQ questions:**
- Source questions from sales calls, support tickets and "People Also Ask"
- Use natural phrasing ("How do I..." not "How does one...")
- Answer fully; no word-count target

**Schema note:** Google stopped showing the FAQ rich result on 2026-05-07 and removed its documentation on 2026-06-15. FAQ content is still useful to readers (Bing names FAQ sections as helpful), but `FAQPage` markup no longer earns a Google rich result, and claims that it improves AI citations are unverified. Existing markup is harmless; don't add it expecting a benefit.

### Listicle Block

Use for "Best [X]", "Top [X]", "[Number] ways to [X]" topics.

```markdown
## [Number] Best [Items] for [Goal/Purpose]

[Intro establishing context and how you selected and tested the items]

### 1. [Item Name]

[Why it's included, with specific, first-hand detail]

### 2. [Item Name]

[Why it's included, with specific, first-hand detail]
```

Google's AI guide contrasts a generic "7 Tips for First-Time Homebuyers" with a first-hand account. A listicle stands out only if it contains testing or experience others don't have.

---

## Evidence Patterns

Patterns for supporting claims. Research note [R]: the GEO paper (Aggarwal et al., KDD 2024) reported visibility gains of up to 40% from citing sources, adding quotations and adding statistics, but measured with the source already inside a fixed context; a 2026 critical survey (preprint, arXiv 2607.14035) reports that citation-oriented rewrites can impair retrieval. Use these patterns because sourced claims are better content, not as a guaranteed uplift.

### Statistic Citation Block

Always include the source and date.

```markdown
[Claim statement]. According to [Source/Organization], [specific statistic with number and timeframe]. [Context for why this matters].
```

**Example (verified source):**
```markdown
Most sites still don't publish an llms.txt file. The HTTP Archive Web Almanac 2025 found one on 2.13% of desktop and 2.10% of mobile sites. Google Search doesn't use the file, so its absence is not an SEO problem.
```

### Expert Quote Block

Named attribution adds credibility. Use only real quotes you have permission to use.

```markdown
"[Direct quote from expert]," says [Expert Name], [Title/Role] at [Organization]. [1 sentence of context or interpretation].
```

**Example (placeholder, fill with a real interview):**
```markdown
"[What your customer or in-house expert actually said about the problem]," says [Name], [Title] at [Company]. [Why this matters for the reader].
```

### Authoritative Claim Block

State the claim, then the source.

```markdown
[Topic] [is/has/requires/involves] [clear, specific claim]. [Source] [confirms/reports/found] that [supporting evidence]. This [means/suggests] [implication or action].
```

**Example:**
```markdown
E-E-A-T is a framework, not a single ranking signal. Google's guide to creating helpful content states that "E-E-A-T itself isn't a specific ranking factor." This means author bios and credentials help by making content more trustworthy to readers, not by flipping a switch.
```

### Key Takeaway Block

A short summary for readers who skim. Write it for people; it is not an AI "answer chunk."

```markdown
**[Topic/Question]**: [Clear summary with the specific details, numbers, or examples from this page.]
```

**Example:**
```markdown
**Blocking GPTBot**: GPTBot is OpenAI's training crawler. Blocking it opts you out of model training but, per OpenAI's crawler documentation, does not remove you from ChatGPT search, which uses OAI-SearchBot.
```

### Evidence Sandwich Block

```markdown
[Opening claim statement].

Evidence supporting this includes:
- [Data point 1 with source]
- [Data point 2 with source]
- [Data point 3 with source]

[Concluding statement connecting evidence to actionable insight].
```

---

## Domain-Specific Authority Signals

Different domains call for different trust signals [H; stricter standards for health, finance and news align with Google's YMYL guidance].

### Technology Content
- Technical precision and correct terminology
- Version numbers and dates for software/tools
- Links to official documentation
- Code examples where relevant

### Health/Medical Content
- Cite peer-reviewed studies with publication details
- Expert credentials (MD, RN, etc.) and reviewer names
- Note study limitations and context
- "Last reviewed" dates

### Financial Content
- Reference regulatory bodies (SEC, FTC, etc.)
- Specific numbers with timeframes and sources
- Note that information is educational, not advice

### Legal Content
- Cite specific laws, statutes, and regulations
- State the jurisdiction clearly
- Professional disclaimers; note when to consult a lawyer

### Business/Marketing Content
- Case studies with real, measurable results
- Primary industry research and reports (not recycled blog stats)
- Percentage changes with timeframes and baselines

---

## Voice and Conversational Queries

Spoken and chat-style queries tend to be full questions ("How do I...", "What is...", "Where can I find..."). AI systems "can understand synonyms and general meanings" [V Google], so you don't need a page per phrasing.

- Answer the question directly, then give the detail
- Use natural, conversational language
- Avoid jargon unless targeting an expert audience
- Include local context (address, hours, service area) and keep Google Business Profile / Bing Places current for local queries [V]
