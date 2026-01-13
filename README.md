# Shopify AI Blog Automation (n8n)
Automate blog content generation and publishing for a Shopify store using n8n + LLM (OpenAI/Gemini) + optional web scraping + Google Sheets logging.

## Goal Budget-Controlled SEO Blog Automation
- Control AI + crawling cost (daily quota + token budget + fail-fast checks)
- Feed the model with site + product + SEO signals to reduce hallucination
- Use organic traffic signals (SE Ranking / GSC) to prioritize topics
- Auto-generate publish-ready blog drafts (HTML) + meta + FAQ + image alt ideas

## High-level Flow
Trigger → Load Inputs → Check Existing Articles → Generate Topic → Generate Draft → Validate → Publish → Log
