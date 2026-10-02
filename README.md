# AdCopilot — the AI agent for Google Ads

**Run your Google Ads from the chat you already use — Claude, ChatGPT, Copilot, Gemini CLI, or Cursor.**

[adcopilot.cloud](https://adcopilot.cloud) · [Start a free 7-day trial](https://app.adcopilot.cloud/signup) · [Security](https://adcopilot.cloud/security) · [Tutorials](https://adcopilot.cloud/tutorials)

AdCopilot is an **AI agent for Google Ads**, built and operated by [Atromx Intelligence](https://atromx.com).
Instead of logging into a separate dashboard, you add one connector to the AI client you already use, sign in
with **your own Google account**, and manage Google Ads in plain language. One connector also reaches the rest
of the stack those ads depend on — **Analytics, Search Console and Tag Manager** — so the same conversation can
tell you whether a conversion was even being counted when the money went out, and what people already search
to find you without paying for it. It reads your account and acts on
it — audits wasted spend, builds campaigns, and adjusts budgets, bids, keywords and negatives — **on your
command**, and it can **never delete**.

> Most AI ad tools make you open another platform. AdCopilot runs where you already are — the demo is a chat.

## Setup, in one step

Add one connector to your AI client and sign in with Google. The exact address and per-client steps live in
your dashboard at [adcopilot.cloud](https://adcopilot.cloud) — there's no key or token to copy, and nothing to
install.

## In Claude: the plugin

AdCopilot is published in **Anthropic's plugin directory** as
[adcopilot-claude-plugin](https://github.com/AtromxIntelligence/adcopilot-claude-plugin) (MIT). It bundles this
connector and adds the steps the connector cannot take for you — what to click in Google's own screens, and
the traps that are easy to fall into — as five commands: `/adcopilot:setup`, `/adcopilot:launch`,
`/adcopilot:measure`, `/adcopilot:audit` and `/adcopilot:daily`.

Two steps, and the second is the one people miss:

1. Add the plugin.
2. **Sign in to the connector it brings with it** — on the web, the plugin's own **Connectors** tab; in Claude
   Code, `/mcp`. There is nothing to add by hand, and adding the connector yourself shadows the plugin's own.

Then run `/adcopilot:setup`: it says what is connected, what is not, and where to go for each. Your Google
products are connected once, inside AdCopilot at [app.adcopilot.cloud](https://app.adcopilot.cloud) — not in
Claude — so a fresh sign-in reporting nothing connected is the server answering correctly, not a fault.

## Why AdCopilot

- **Runs in the chat you already use.** No new dashboard, no extra tab — Claude, ChatGPT, Copilot, Gemini CLI or Cursor.
- **Safe with a live account.** It can **never delete** — removing a campaign, ad or keyword simply isn't something it can do. New campaigns arrive **paused**, and **every change waits for your approval**.
- **Your login, your data.** It runs under your own Google sign-in. No password is shared, and your ad data is not stored or used to train models.
- **Built for teams.** Per-member Google sign-in: each teammate signs in as themselves, every change is attributed to them, and per-account allow-lists keep the right hands on the right accounts.

## What it does

- **Audit wasted spend** — find the search terms, devices and placements draining budget without converting.
- **Build campaigns** — Search and Performance Max, ad groups, responsive search ads, assets — created **paused**, for your review.
- **Adjust everything, in plain language** — budgets, bids, keywords, negatives, geo, ad schedule and device bid adjustments.

Every action is proposed and then gated behind your approval, so the worst an approved action can do is reversible.

## Works in

Claude (Desktop + claude.ai) · Claude Code · ChatGPT · Microsoft Copilot · Gemini CLI · Cursor · OpenCode.
Setup guides: [adcopilot.cloud/tutorials](https://adcopilot.cloud/tutorials).

## Pricing

Free **7-day Pro trial** — full capability, no card. After the trial it drops automatically to a permanently
free plan for one account (not a lockout); paid plans add more accounts and seats.
[Start here](https://app.adcopilot.cloud/signup) or ask support@atromx.com.

## Coverage &amp; limits, stated plainly

- **Google Ads is the only ad platform** today — Meta, LinkedIn and the rest are roadmap, not shipped. Within
  Google it also reads Analytics, Search Console and Tag Manager.
- **No SOC 2** yet. It runs under your own Google OAuth; no password is shared and ad data is not stored.
- **Unattended, always-on auditing is roadmap, not shipped.** Today the agent acts when you ask, and every change waits on your approval.

---

AdCopilot by Atromx Intelligence — the AI agent for Google Ads. Google Ads is a trademark of Google LLC.
AdCopilot is not affiliated with or endorsed by Google.
