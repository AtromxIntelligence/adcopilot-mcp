# AdCopilot — the hosted Google Ads MCP server

**The AI agent that runs your Google Ads — inside Claude, ChatGPT, Copilot, Gemini CLI, Cursor, or any MCP client.**

[adcopilot.cloud](https://adcopilot.cloud) · [Start a free 7-day pilot](https://mcp.adcopilot.cloud/signup) · [Security model](https://adcopilot.cloud/security) · [Tutorials](https://adcopilot.cloud/tutorials)

AdCopilot is a hosted [Model Context Protocol](https://modelcontextprotocol.io) connector for Google Ads,
built and operated by [Atromx Intelligence](https://atromx.com). You sign in with **your own Google
account**, receive a private connector address, and paste it into the AI client you already use.
No developer token, no Cloud project, no server to run.

```bash
# Claude Code / any CLI that takes a remote MCP:
claude mcp add --transport http adcopilot https://mcp.adcopilot.cloud/c/<your-key>/mcp
```

```json
{ "mcpServers": { "adcopilot": { "httpUrl": "https://mcp.adcopilot.cloud/c/<your-key>/mcp" } } }
```

## Why hosted, and why this one

| | Free self-hosted servers | **AdCopilot (hosted)** |
|---|---|---|
| Tools | 3, read-only | **32, reads and writes** |
| Can it change a campaign? | No | Yes — create, adjust, pause, enable |
| Can it delete anything? | — | **No. Structurally.** The four `remove_*` tools are never exposed, and any mutate carrying a `REMOVED` status is refused server-side, in any letter case. |
| Developer token | Yours to obtain and manage | Ours by default (bring-your-own supported) |
| Sign-in | Your OAuth plumbing | Your own Google account; Google-verified OAuth (Aug 2026) |
| Teams | — | Per-member sign-in; each teammate individually revocable; org-level scoping |
| Audit | — | Every call recorded — tool, account, outcome, refusals included |
| Runs where | Your machine | Hosted; nothing to install |

## The 32 hosted tools


### Read & audit

- **`search`** — Fetches data from the Google Ads API using the search method
- **`list_accessible_customers`** — Returns ids of customers directly accessible by the user authenticating the call.
- **`get_resource_metadata`** — Retrieves the selectable, filterable, and sortable fields for a specific Google Ads resource. Use this tool to find out which fields you can

### Campaigns

- **`create_campaign`** — Creates a new Google Ads campaign with a budget.
- **`update_campaign`** — Updates an existing Google Ads campaign's settings.
- **`set_campaign_status`** — Enables, pauses, or removes a Google Ads campaign. This is a convenience tool for quickly changing campaign status.
- **`create_performance_max_campaign`** — Creates a Performance Max campaign with a budget, business name, and logo. PMax campaigns require a business name and logo asset linked at t

### Ad groups & ads

- **`create_ad_group`** — Creates a new ad group within a campaign.
- **`update_ad_group`** — Updates an existing ad group's settings.
- **`create_responsive_search_ad`** — Creates a responsive search ad in an ad group. Responsive search ads allow you to provide multiple headlines and descriptions, and Google Ad
- **`update_ad_status`** — Enables, pauses, or removes an ad.

### Keywords

- **`add_keywords`** — Adds keywords to an ad group.
- **`add_negative_keywords`** — Adds negative keywords to a campaign to block irrelevant traffic. Negative keywords prevent your ads from showing for specific search terms.
- **`update_keyword`** — Updates a keyword's status or bid.

### Targeting & bids

- **`set_geo_targets`** — Sets geo targeting for a campaign by adding location criteria. Common location IDs (Google Ads geo target constants): US=2840, UK=2826, Cana
- **`set_ad_schedule`** — Sets ad schedule (day/hour targeting) for a campaign. Controls which days and hours ads are shown.
- **`set_device_bid_adjustment`** — Sets a bid adjustment for a specific device type on a campaign. Use this to increase or decrease bids for Mobile, Desktop, or Tablet devices

### Assets

- **`create_sitelink_asset`** — Creates a sitelink asset that can be linked to campaigns or ad groups. Sitelinks add additional links below your ad, directing users to spec
- **`create_callout_asset`** — Creates a callout asset that can be linked to campaigns or ad groups. Callouts add short snippets of text to your ad (e.g., "Free Shipping",
- **`create_structured_snippet_asset`** — Creates a structured snippet asset that can be linked to campaigns or ad groups. Structured snippets highlight specific aspects of your prod
- **`create_call_asset`** — Creates a call asset that can be linked to campaigns or ad groups. Call assets add a phone number to your ad, allowing users to call directl
- **`create_image_asset`** — Creates an image asset from a URL or local file path. Supports both web URLs and local file paths on the user's computer. Recommended image 
- **`create_promotion_asset`** — Creates a promotion asset that can be linked to campaigns or ad groups. Promotion assets highlight sales and special offers in your ads.
- **`create_price_asset`** — Creates a price asset that can be linked to campaigns or ad groups. Price assets showcase your products or services with their prices.
- **`create_lead_form_asset`** — Creates a lead form asset that can be linked to campaigns or ad groups. Lead form assets collect user information directly from the ad.
- **`create_text_asset`** — Creates a text asset for use in Performance Max asset groups. Use this to create headline, description, and long headline assets that can be
- **`create_youtube_video_asset`** — Creates a YouTube video asset for use in Performance Max campaigns.
- **`link_asset_to_campaign`** — Links an existing asset to a campaign. After creating an asset (sitelink, callout, etc.), use this tool to attach it to a campaign so it app
- **`link_asset_to_ad_group`** — Links an existing asset to an ad group. After creating an asset (sitelink, callout, etc.), use this tool to attach it to an ad group so it a
- **`link_assets_to_customer`** — Links assets at the customer (account) level so they apply to all campaigns.
- **`create_asset_group`** — Creates an asset group for a Performance Max campaign and links all provided assets to it. Asset groups and their assets must be created tog
- **`add_assets_to_asset_group`** — Adds assets to an existing asset group. Use this to add more assets to an asset group after it's been created.


### Deliberately absent

`remove_ad`, `remove_keyword`, `remove_campaign_asset`, `remove_asset_from_asset_group` exist in the
underlying 36-tool server and are **never exposed to hosted connectors** — and a status change to
`REMOVED` (the Google Ads API's delete) is refused before it reaches Google. The worst an approved
action can do is reversible. That is a capability boundary, not a prompt.

## Works in

Claude (Desktop + claude.ai) · Claude Code · ChatGPT · GitHub Copilot · Gemini CLI · Cursor ·
OpenCode — anything speaking MCP over streamable HTTP. Setup guides: [adcopilot.cloud/tutorials](https://adcopilot.cloud/tutorials).

## Security model, in one paragraph

Your connector runs under your own Google sign-in, so it reaches exactly the accounts Google already
lets you reach. We store one credential — an encrypted refresh token — never your password, never your
advertising data. Withdraw access any time from your own Google account and the credential dies at
source. Connectors can be scoped to named customer IDs, switched off per member, and every call —
including every refusal — is in the audit trail. Full detail: [adcopilot.cloud/security](https://adcopilot.cloud/security).

## Pricing

Free 7-day pilot on one account — full toolset, no card. Then a simple subscription:
[start here](https://mcp.adcopilot.cloud/signup) or ask support@atromx.com.

---

Google Ads is a trademark of Google LLC. AdCopilot is not affiliated with or endorsed by Google.
