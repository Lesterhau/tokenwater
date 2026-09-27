# TokenWater
### Cross-platform AI water consumption tracker — v1.0

**Because water is the hidden cost of intelligence.**

**Live app: [lesterhau.github.io/tokenwater](https://lesterhau.github.io/tokenwater)**

No download. No account. Open in any browser and you're done.

---

You use AI every day. You have no idea how much water that costs.

Microsoft used 6.4 billion liters in 2022 — up 34% year-over-year. Google: +20% the same period. The servers running Claude, ChatGPT, Gemini, and Grok consume enormous amounts of water for cooling and electricity generation. That number grows every time you send a message. No one tells you. There's no meter running. There's no bill.

TokenWater is an estimator, not a meter. It makes an invisible infrastructure cost visible while keeping the uncertainty visible too.

---

## How It Works

TokenWater is a setup tool, not a dashboard. You open it once, set your weekly water quota, pick your AI platforms, and copy a memory snippet for each one. Paste the snippet into your AI's memory settings. Close the tab. Done.

From that point on, your AI can maintain a directional usage estimate from conversation context. Exact token counts are only available when the platform exposes usage telemetry; otherwise the estimate must be labeled as approximate.

**You do not need to keep this page open after setup.**

Every morning, your first conversation shows you:
- Yesterday's water usage (in liters and a physical comparison — "about one toilet flush")
- Your weekly pace and projection
- How you compare with the personal budget you chose
- Alerts at 50%, 75%, 90%, 95%, and 100% of your weekly quota

---

## What's New in v1.0

- 13 platforms supported across persistent memory and session-only tiers
- Water comparisons in plain English (water bottles, showers, toilet flushes)
- Anonymous community impact counter — see how many people are tracking
- Monthly refresh reminder baked into every snippet
- Discourages unnecessary AI follow-up questions to reduce token waste
- Praise system for good usage — irreverent, never sycophantic
- Shareable weekly stat with #TokenWater hashtag auto-generated
- Over-quota alerts at 100% and 110%

---

## Platforms

| Platform | Memory | Notes |
|---|---|---|
| Claude | ✅ Persistent | Settings → Capabilities → Memory → Manage edits |
| ChatGPT | ✅ Persistent | Settings → Personalization → Memory → Add memory (app or browser) |
| Gemini | ✅ Persistent | Settings → Extensions & Personalization → About you |
| Microsoft Copilot | ✅ Persistent | Settings → Account → Privacy → Personalization and memory |
| Claude Code | ✅ Persistent | Paste into CLAUDE.md in your project root |
| OpenClaw | ✅ Persistent | Add to persona/memory context during onboarding |
| Grok | ⚡ Session only | Paste at start of each conversation |
| Perplexity | ⚡ Session only | Paste at start of each conversation |
| Perplexity Computer | ⚡ Session only | High token burn — consider higher quota |
| DeepSeek | ⚡ Session only | Paste at start of each conversation |
| Claude Cowork | ⚡ Session only | Paste at start of each session |
| Ernie Bot (Baidu) | ⚡ Session only | Paste at start of each conversation |
| HyperCLOVA X (Naver) | ⚡ Session only | Paste at start of each conversation |

---

## The Water Math

**There is no universal water-per-token constant.**

Modern measurements show large variation by model, hardware, serving configuration, query type, cooling system, climate, and electricity source. TokenWater is moving to a versioned low/mid/high scenario methodology rather than presenting one fixed coefficient as measured reality. See [METHODOLOGY.md](METHODOLOGY.md).

**Current sources:**
- Chung, J.-W. et al. (2025). "The ML.ENERGY Benchmark." NeurIPS Datasets & Benchmarks. https://ml.energy/leaderboard/
- Li, P. et al. (2025). "Making AI Less 'Thirsty'." Communications of the ACM. https://doi.org/10.1145/3724499
- Google (2025). "Measuring the environmental impact of AI inference." https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference
- Oviedo, F. et al. (2026). "Energy use of AI inference, efficiency pathways, and test-time scaling." Joule. https://doi.org/10.1016/j.joule.2026.102430
- Data-center workload water-use review (2025). Resources, Conservation & Recycling. https://doi.org/10.1016/j.resconrec.2025.108310

If the methodology is wrong, open an issue and cite your source.

---

## The Behavior Change Mechanic

This is not an app about guilt. Guilt doesn't change behavior.

The Opower experiment sent households a simple letter: here's your energy use, here's your neighbor's. No moral lecture. Just a comparison. It drove a 2% national reduction in household energy consumption.

TokenWater runs the same mechanic. "You used 34% fewer tokens than the average user this week" is more effective than any environmental messaging. The comparison is built in.

---

## How to Contribute

Single HTML file. Zero dependencies. MIT licensed. You do not need to be a developer.

**Highest priority:**
- **Phase 2 platform connectors** — If you use Mistral, Cohere, Qwen, or Groq, open an issue with the API response format and the token field names. That's the whole spec.
- **Better water math** — Per-provider PUE and water intensity data. Open a PR against METHODOLOGY.md with a source.
- **Browser extension** — Auto-captures token counts without manual entry. Highest-leverage expansion.
- **Translations** — Japanese, Spanish, Arabic, Hindi are highest priority.
- **Cloudflare Worker** — Community impact counter backend. See CONTRIBUTING.md.

---

## Technical Notes

- **No frameworks.** Vanilla HTML/CSS/JS.
- **No server.** Everything runs client-side.
- **localStorage only.** API keys never leave your browser.
- **Single file.** Fork it, host it on GitHub Pages in 5 minutes.
- **MIT licensed.** Take it, improve it, redistribute it.

---

## Who Built This

Built by [Ryan Lester](https://rlperspectives.com) — Navy veteran, economics student at the University of Houston, foresight researcher. TokenWater started as a thought experiment about invisible infrastructure costs and became a tool because nothing like it existed.

Essays on systems, power, and the future: **[RLPerspectives.com](https://rlperspectives.com)**

MIT licensed. Take it. Make it better. The water is still being used whether you track it or not.

---

*v1.0 — MIT License — [rlperspectives.com](https://rlperspectives.com)*
