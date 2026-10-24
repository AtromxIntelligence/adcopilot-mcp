# AdCopilot — the AI agent for Google Ads

**Run your Google Ads from the chat you already use — Claude, ChatGPT, Copilot, Gemini CLI, Codex or Cursor.**

[adcopilot.cloud](https://adcopilot.cloud) · [Start free: 5-day Pro trial, no card to start](https://app.adcopilot.cloud/signup) · [Security](https://adcopilot.cloud/security) · [Tutorials](https://adcopilot.cloud/tutorials)

AdCopilot is an **AI agent for Google Ads**, built and operated by [Atromx Intelligence](https://atromx.com).
Instead of logging into a separate dashboard, you add one connector to the AI client you already use, sign in
with **your own Google account**, and manage Google Ads in plain language. One connector also reaches the rest
of the stack those ads depend on — **Analytics, Search Console and Tag Manager** — so the same conversation can
tell you whether a conversion was even being counted when the money went out, and what people already search
to find you without paying for it. It reads your account and acts on
it — audits wasted spend, builds campaigns, and adjusts budgets, bids, keywords and negatives — **on your
command**. It cannot delete campaigns, ads or keywords; it can take a negative keyword back out.

> Most AI ad tools make you open another platform. AdCopilot runs where you already are — the demo is a chat.

## Setup, in one step

Add one connector to your AI client, `https://mcp.adcopilot.cloud/mcp`, and sign in with Google (OAuth). The
per-client steps live at [adcopilot.cloud/tutorials](https://adcopilot.cloud/tutorials) — the connector is hosted,
so there is nothing to run.

AdCopilot connects to Google Ads through its own Google Cloud project, with your Google sign-in. If you want
programmatic access to Google Ads for your own software, get your own Google Cloud account and apply for Google
Ads API access there.

## In Claude: the plugin

AdCopilot is published in **Anthropic's plugin directory** as
[adcopilot-claude-plugin](https://github.com/AtromxIntelligence/adcopilot-claude-plugin) (MIT). It bundles this
connector and adds the steps the connector cannot take for you — what to click in Google's own screens, and
the traps that are easy to fall into — as commands: `/adcopilot:setup`, `/adcopilot:launch`,
`/adcopilot:measure`, `/adcopilot:audit`, `/adcopilot:daily`, `/adcopilot:weekly` and `/adcopilot:negatives`.

Two steps, and the second is the one people miss:

1. Add the plugin.
2. **Sign in to the connector it brings with it** — on the web, the plugin's own **Connectors** tab; in Claude
   Code, `/mcp`. There is nothing to add by hand, and adding the connector yourself shadows the plugin's own.

Then run `/adcopilot:setup`: it says what is connected, what is not, and where to go for each. Your Google
products are connected once, inside AdCopilot at [app.adcopilot.cloud](https://app.adcopilot.cloud) — not in
Claude — so a fresh sign-in reporting nothing connected is the server answering correctly, not a fault.

## Why AdCopilot

- **Runs in the chat you already use.** No new dashboard, no extra tab — Claude, ChatGPT, Copilot, Gemini CLI, Codex or Cursor.
- **Safe with a live account.** It cannot delete campaigns, ads or keywords; it can take a negative keyword back out. New campaigns arrive **paused** and AdCopilot **proposes each change first**. For a hard stop, set your AI client to ask before AdCopilot's write tools: Needs approval in Claude; in Cursor, set the run mode to Allowlist and keep them off the allowlist (Cursor's cloud agents never ask).
- **Your login, your data.** It runs under your own Google sign-in. No password is shared; queries run live against your account (audit reads are cached for up to an hour, a saved audit's findings for 180 days), and your Google data is never used to train models.
- **Built for teams.** Per-member Google sign-in: each teammate signs in as themselves, every change is attributed to them, and per-account access rules keep the right hands on the right accounts.

## What it does

- **Audit wasted spend** — find the search terms, devices and placements draining budget without converting.
- **Build campaigns** — Search and Performance Max, with ad groups, responsive search ads and assets — each campaign created **paused**, for your review.
- **Adjust everything, in plain language** — budgets, bids, keywords, negatives, geo, ad schedule and device bid adjustments.

Every change is proposed first; where something should stop, it pauses rather than removes.

## Works in

Claude (Desktop + claude.ai) · Claude Code · ChatGPT · Microsoft Copilot · Gemini CLI · Codex · Cursor.
Setup guides: [adcopilot.cloud/tutorials](https://adcopilot.cloud/tutorials).

## Pricing

**5-day Pro trial** — the full Pro plan for your first workspace, no card to start (one is needed after 1,000
operations). Without a card it then drops automatically to a permanently free plan: one Google Ads account, 10
operations a day (not a lockout); paid plans from $19 a month (plus tax where it applies) add accounts, daily
operations and people. Plans: [adcopilot.cloud/pricing](https://adcopilot.cloud/pricing).
[Start here](https://app.adcopilot.cloud/signup) or ask support@adcopilot.cloud.

## Coverage &amp; limits, stated plainly

- **Google Ads is the only ad platform** today — Meta, LinkedIn and the rest are roadmap, not shipped. Within
  Google it also works on Analytics, Search Console and Tag Manager.
- **No SOC 2** yet. It runs under your own Google sign-in; no password is shared. Google has verified AdCopilot's app for
  Google Ads, Analytics, Search Console and Tag Manager.
- **On its own, AdCopilot only reads.** The daily check-in email (on Mondays, the Monday summary) reads your Google
  Ads account once a day, and a daily check reads your connected Search Console sites; neither changes anything.
  Every change happens when you ask, and is proposed first.

---

AdCopilot by Atromx Intelligence — the AI agent for Google Ads. Google Ads is a trademark of Google LLC.
AdCopilot is not affiliated with or endorsed by Google.
