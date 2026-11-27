# LMH Agent Data Tools (MCP server)

Remote MCP server with **11 data tools for AI agents**: web page / PDF to Markdown, SEC EDGAR filings and financials, openFDA and clinical trials, PyPI and npm package health, Hugging Face Hub, Grants.gov, USAspending awards, company dossiers, company contacts, and website change monitoring.

- **Official MCP Registry:** `io.github.LMH-Solutions/agent-data-tools`
- **Transport:** Streamable HTTP (hosted by Apify, nothing to install)
- **Auth:** `Authorization: Bearer <your Apify API token>` (free Apify account)
- **Pricing:** pay per result through Apify (no subscription). Example: web page to Markdown is $0.002 per page. See each tool's page for its price.

## Endpoint

```
https://mcp.apify.com/?tools=lmhsolutions/web-page-to-markdown-pdf-to-text,lmhsolutions/sec-edgar-filings,lmhsolutions/openfda-intelligence,lmhsolutions/pypi-package-intelligence,lmhsolutions/npm-package-intelligence,lmhsolutions/huggingface-hub-scraper,lmhsolutions/grants-gov-scraper,lmhsolutions/usaspending-federal-awards,lmhsolutions/company-dossier,lmhsolutions/company-contact-extractor,lmhsolutions/website-change-monitor
```

## Where it's listed

- Official MCP Registry: [io.github.LMH-Solutions/agent-data-tools](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.LMH-Solutions/agent-data-tools)
- Glama: [LMH Agent Data Tools](https://glama.ai/mcp/connectors/io.github.LMH-Solutions/agent-data-tools)
- AptLynx: [LMH Agent Data Tools](https://aptlynx.net/servers/io.github.LMH-Solutions/agent-data-tools)
- Apify Store: [lmhsolutions](https://apify.com/lmhsolutions) (each tool also runs on its own, by API or schedule)

## Example prompts

- "Get Apple's last 8 quarters of revenue and net income from SEC EDGAR, plus any Form 4 insider sales this month."
- "List FDA drug recalls for semaglutide in the past year and the recruiting Phase 3 trials."
- "Convert https://example.com/docs and this PDF to clean Markdown for my RAG index."
- "Compare downloads, license and last release for the npm packages zod, yup and joi."
- "Find open Grants.gov opportunities for rural broadband closing in the next 60 days."
- "Which companies won the most USAspending contract dollars under NAICS 541512 last fiscal year?"

## Tools

| Tool | What it returns | Apify page |
|---|---|---|
| Web Page to Markdown & PDF | Clean, LLM-ready Markdown and text from web pages and PDFs (RAG ingestion) | https://apify.com/lmhsolutions/web-page-to-markdown-pdf-to-text |
| SEC EDGAR | Filings, XBRL financials (revenue, net income, EPS...) and Form 4 insider trades by ticker | https://apify.com/lmhsolutions/sec-edgar-filings |
| openFDA | Drug/food/device recalls, FAERS adverse events, drug labels, ClinicalTrials.gov studies | https://apify.com/lmhsolutions/openfda-intelligence |
| PyPI package health | Downloads, versions, license, dependencies and health signals for Python packages | https://apify.com/lmhsolutions/pypi-package-intelligence |
| npm package health | Downloads, versions, license, dependencies and health signals for npm packages | https://apify.com/lmhsolutions/npm-package-intelligence |
| Hugging Face Hub | Models, datasets and Spaces with downloads, likes, tags and licenses | https://apify.com/lmhsolutions/huggingface-hub-scraper |
| Grants.gov | Federal grant opportunities, deadlines, eligibility and agency contacts | https://apify.com/lmhsolutions/grants-gov-scraper |
| USAspending | Federal contract and grant awards by recipient, agency, NAICS or keyword | https://apify.com/lmhsolutions/usaspending-federal-awards |
| Company Dossier | Company profile from SEC, UK Companies House and the company website | https://apify.com/lmhsolutions/company-dossier |
| Company Contact Extractor | Public emails, phones and social links from company websites | https://apify.com/lmhsolutions/company-contact-extractor |
| Website Change Monitor | Page and price change detection with diffs and alerts | https://apify.com/lmhsolutions/website-change-monitor |

## Connect

### Claude Desktop / Cursor / VS Code (mcp.json style)

```json
{
  "mcpServers": {
    "lmh-agent-data-tools": {
      "url": "https://mcp.apify.com/?tools=lmhsolutions/web-page-to-markdown-pdf-to-text,lmhsolutions/sec-edgar-filings,lmhsolutions/openfda-intelligence,lmhsolutions/pypi-package-intelligence,lmhsolutions/npm-package-intelligence,lmhsolutions/huggingface-hub-scraper,lmhsolutions/grants-gov-scraper,lmhsolutions/usaspending-federal-awards,lmhsolutions/company-dossier,lmhsolutions/company-contact-extractor,lmhsolutions/website-change-monitor",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

### Clients that only support stdio

```json
{
  "mcpServers": {
    "lmh-agent-data-tools": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.apify.com/?tools=lmhsolutions/web-page-to-markdown-pdf-to-text,lmhsolutions/sec-edgar-filings,lmhsolutions/openfda-intelligence,lmhsolutions/pypi-package-intelligence,lmhsolutions/npm-package-intelligence,lmhsolutions/huggingface-hub-scraper,lmhsolutions/grants-gov-scraper,lmhsolutions/usaspending-federal-awards,lmhsolutions/company-dossier,lmhsolutions/company-contact-extractor,lmhsolutions/website-change-monitor", "--header", "Authorization: Bearer YOUR_APIFY_TOKEN"]
    }
  }
}
```

Get a token at https://console.apify.com/settings/integrations.

## About

Built and maintained by LMH Solutions (https://apify.com/lmhsolutions). Issues and requests: open a GitHub issue in this repo.

License: MIT (this README and config). The tools run on Apify under the Apify terms.
