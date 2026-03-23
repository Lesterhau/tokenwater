# TokenWater
### Cross-platform AI water consumption tracker

**Because water is the hidden cost of intelligence.**

---

You use AI every day. You have no idea how much water that costs.

Microsoft used 6.4 billion liters in 2022 — up 34% year-over-year. Google: +20% the same period. The servers running Claude, ChatGPT, Gemini, and Grok need massive amounts of water for cooling and for the electricity generation that powers them. That number grows every time you send a message. No one tells you. There's no meter running. There's no bill.

TokenWater is the meter.

---

## What It Does

- Tracks token usage across all major LLM platforms
- Estimates water consumption using the proxy metric: ~100ml per 1,000 tokens
- Compares your usage to estimated averages (social comparison, not guilt)
- Generates ready-to-paste memory snippets for each platform, personalized with your actual weekly numbers
- Runs entirely in your browser — no server, no account, no data transmitted anywhere

---

## The Water Math

Token count is a proxy for compute, and compute has a water cost. The estimate: **~100ml of water consumed per 1,000 tokens processed.**

This is derived from data center power usage effectiveness (PUE) data and cooling water intensity ratios for major US cloud providers. It is a directional estimate, not an exact measurement. Actual consumption varies by provider, region, season, and model architecture.

**Sources:**
- Li, P. et al. (2023). "Making AI Less Thirsty: Uncovering and Addressing the Secret Water Footprint of AI Models." UC Riverside. https://arxiv.org/abs/2304.03271
- Luccioni, A.S. et al. (2023). "Power Hungry Processing: Watts Driving the Cost of AI Deployment?" https://arxiv.org/abs/2311.16863
- Microsoft 2022 Environmental Sustainability Report
- Google 2022 Environmental Report

If the math is wrong, open an issue and cite your source. Better estimates make this more useful for everyone.

---

## The Behavior Change Mechanic

This is not an app about guilt. Guilt doesn't change behavior.

The Opower experiment sent households a simple letter: here's your energy use, here's your neighbor's. That's it. No moral lecture. No carbon footprint calculator. Just a comparison. It drove a 2% national reduction in household energy consumption — which at scale is enormous.

TokenWater runs the same mechanic. "You used 34% fewer tokens than the average user this week" is more effective than any environmental messaging. The comparison is built in.

---

## Why Memory Snippets

You can't write directly to most LLMs' memory systems via API. The real lever is system prompt injection every session plus telling users exactly what to paste into each platform's manual memory settings. TokenWater generates personalized snippets — updated weekly with your actual numbers — that you paste once and forget. It's a workaround that works.

---

## Platform Coverage

| Platform | Org | Phase |
|---|---|---|
| Claude | Anthropic | ✅ Phase 1 — Active |
| ChatGPT | OpenAI | ✅ Phase 1 — Active |
| Gemini | Google DeepMind | ✅ Phase 1 — Active |
| Grok | xAI | ✅ Phase 1 — Active |
| DeepSeek | DeepSeek AI | ✅ Phase 1 — Active |
| Perplexity | Perplexity AI | ✅ Phase 1 — Active |
| Meta AI / Llama 4 | Meta | 🟡 Phase 2 — Needs contributor |
| Mistral / Le Chat | Mistral AI | 🟡 Phase 2 — Needs contributor |
| Cohere Command | Cohere | 🟡 Phase 2 — Needs contributor |
| Microsoft Copilot | Microsoft | 🟡 Phase 2 — Needs contributor |
| Qwen | Alibaba Cloud | 🟡 Phase 2 — Needs contributor |
| Groq | Groq Inc. | 🟡 Phase 2 — Needs contributor |
| Together AI | Together AI | ⬜ Phase 3 — Community |
| Hugging Face | HuggingFace | ⬜ Phase 3 — Community |
| AI21 / Jamba | AI21 Labs | ⬜ Phase 3 — Community |
| Amazon Bedrock | Amazon Web Services | ⬜ Phase 3 — Community |
| Pi / Inflection | Inflection AI | ⬜ Phase 3 — Community |
| Fireworks AI | Fireworks AI | ⬜ Phase 3 — Community |
| SiliconFlow | SiliconFlow | ⬜ Phase 3 — Community |
| DeepSeek via Fireworks | Fireworks AI | ⬜ Phase 3 — Community |

---

## How to Use

1. Download `tokenwater.html`
2. Open it in any browser — no install, no server
3. Add API keys (optional — stored locally, never transmitted)
4. Log your token usage after each session
5. Check the Dashboard for your weekly water estimate
6. Grab your Memory Snippets and paste them into each platform

That's it.

---

## How to Contribute

This is a single HTML file. Zero dependencies. MIT licensed. You do not need to be a developer.

**Highest priority:**
- **Phase 2 platform connectors** — If you use Mistral, Cohere, Copilot, Qwen, or Groq, open an issue with the API response format and the token field names. That's the whole spec.
- **Browser extension** — This is the highest-leverage expansion. Auto-captures token counts without manual entry. If you can build this, please do.
- **Better water math** — Per-provider PUE and water intensity data. If you have better numbers than the global average, open a PR against `METHODOLOGY.md`.

**Also welcome:**
- Translations — Japanese, Spanish, Arabic, Hindi are highest priority
- Real-time token counting via streaming APIs
- Community leaderboard (opt-in, anonymized)
- Carbon tracking integration (CodeCarbon, mlco2.github.io)
- Mobile PWA wrapper

---

## Technical Notes

- **No frameworks.** Vanilla HTML/CSS/JS.
- **No server.** Everything runs client-side.
- **localStorage only.** API keys never leave your browser.
- **Single file.** Fork it, host it on GitHub Pages, done.
- **MIT licensed.** Take it, improve it, redistribute it. Cite your sources.

---

## Roadmap

- [ ] GitHub repo + GitHub Pages deploy
- [ ] `CONTRIBUTING.md` with platform connector spec
- [ ] `METHODOLOGY.md` with full water proxy documentation
- [ ] Browser extension (auto token capture)
- [ ] Real-time token counting via streaming
- [ ] Community leaderboard (opt-in)
- [ ] Carbon tracking integration
- [ ] i18n — Japanese, Spanish, Arabic, Hindi
- [ ] Mobile PWA
- [ ] Phase 2 platform connectors
- [ ] ProductHunt launch (post-extension)

---

## Who Built This

Built by [Ryan Lester](https://rlperspectives.com) — Navy veteran, economics student, foresight researcher at University of Houston. TokenWater started as a thought experiment about invisible infrastructure costs and became a tool because nothing like it existed.

MIT licensed. Take it. Make it better. The water is still being used whether you track it or not.

---

*v0.1.0 — MIT License — [rlperspectives.com](https://rlperspectives.com)*
