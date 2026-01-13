# Shopify AI Blog Automation (n8n)
Automate blog content generation and publishing for a Shopify store using n8n + LLM (OpenAI/Gemini) + optional web scraping + Google Sheets logging.

## Goal Budget-Controlled SEO Blog Automation
- Control AI + crawling cost (daily quota + token budget + fail-fast checks)
- Feed the model with site + product + SEO signals to reduce hallucination
- Use organic traffic signals (SE Ranking / GSC) to prioritize topics
- Auto-generate publish-ready blog drafts (HTML) + meta + FAQ + image alt ideas

## High-level Flow
Trigger → Load Inputs → Check Existing Articles → Generate Topic → Generate Draft → Validate → Publish → Log

# Core Workflow

## A) Content Feeding 
1. Read webSite (priority sources)
   - product pages / collection pages
   - blog category pages
   - top landing pages
2. Extract facts
   - product specs, sizes, MOQ, shipping, materials, use-cases
   - internal links candidates
3. Build "Context Pack" (short + structured)
   - key facts bullets
   - top internal links

## B) Organic Traffic Signal (what to write first)
  - Pull analytics/traffic or domain research data → pick pages/keywords with opportunity

## C) Prompt Library (versioned)
1. Topic Selector Prompt (outputs strict JSON)
2. Outline Builder Prompt
3. Article Generator Prompt (HTML + meta + FAQ + alt)
4. QA/Policy Prompt (check claims, numbers, prohibited words)
5. Formatter Prompt (Shopify-ready HTML)

## D) Web Crawling (optional)
- Crawl competitor pages or references (limited)
- Summarize to structured bullets
- Never copy; only extract facts + angles

## E) Generation & Publish
- Generate JSON payload
- Validate JSON schema
- Create Shopify article (draft by default)
- Log results (Sheet/DB): title, keyword, cost, sources, status
