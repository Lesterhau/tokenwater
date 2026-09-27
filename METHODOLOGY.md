# TokenWater Methodology

**Version:** 1.1 (methodology integrity update)  
**Updated:** September 2026

## What TokenWater is

TokenWater is a **directional estimator** for the water implications of AI inference. It is not a physical meter and it cannot observe a provider's actual data-center location, cooling system, server utilization, hardware, or electricity source.

The governing design rule is simple: **show the uncertainty; never turn an estimate into a measurement by formatting it more precisely.**

## Why v1.0 changed

v1.0 used a fixed proxy of **100 mL per 1,000 tokens**. Current evidence does not support that value as a universal conversion.

- A 2025 review of data-center workloads found workload-level water use can vary by more than **10,000×** across server efficiency, grid water intensity, utilization, cooling, climate, infrastructure efficiency, and other determinants.
- Google's 2025 production measurement reported a median Gemini Apps text prompt using about **0.26 mL of water** in its environment.
- Oviedo et al. (Joule, 2026) estimated median optimized frontier-scale inference at **0.31 Wh/query**, while long reasoning queries were about **13×** higher.
- ML.ENERGY publishes measured inference-energy data across modern open models, hardware, batch sizes, and tasks.

These sources do not support one universal water-per-token constant.

## v1.1 manual-log scenarios

When the user has exact input and output token counts, a provisional effective-token proxy is:

    effective_tokens = output_tokens + 0.20 × fresh_input_tokens

The 0.20 input weight is an approximation reflecting the lower compute cost of parallelized prefill relative to autoregressive decode. It is not a provider measurement.

TokenWater then uses three **illustrative direct-cooling scenarios**:

| Scenario | mL per 1,000 effective tokens | Purpose |
|---|---:|---|
| Low | 0.036 | Efficient hardware / low-water cooling context |
| Mid | 0.36 | Central illustrative scenario |
| High | 0.79 | Higher-water cooling context |

These values are **scenario values, not a confidence interval**. Real deployments can fall outside them. They cover direct operational cooling water only and are not provider-specific measurements or a full lifecycle footprint.

## What is included

- Inference only
- Direct operational cooling water
- A rough distinction between fresh input and output-generation compute
- Low / mid / high scenarios instead of a single number

## What is not included

- Model training
- Hardware manufacturing / embodied water
- Electricity-generation water (off-site or scope-2 water)
- Networking and end-user-device energy
- Exact provider region, cooling technology, server utilization, or batch size
- Reliable cache-read/cache-write accounting
- Image, audio, or video generation unless separately modeled

## Consumer-chat limitation

Most consumer chat interfaces do **not** expose exact input/output token telemetry to the model inside the conversation. Therefore memory-based TokenWater snippets can only maintain a **directional estimate** unless the platform supplies real usage metadata.

A model should never claim:
- that it knows exact token counts when telemetry is unavailable;
- that TokenWater measured physical water flow;
- that an estimated range is provider-specific unless the provider supplied the underlying data.

## No fabricated population benchmarks

v1.0 used labels such as "casual," "regular," and "power user." TokenWater does not currently have a representative population dataset that supports those categories. They should be removed from product claims and user comparisons.

## Data design

Future versions should retain raw input/output token counts and store the methodology version separately from derived water estimates. That makes historical data recomputable when the science improves instead of baking old assumptions permanently into the log.

## References

1. Chung, J.-W., et al. (2025). **The ML.ENERGY Benchmark: Toward Automated Inference Energy Measurement and Optimization.** NeurIPS Datasets and Benchmarks. https://ml.energy/leaderboard/
2. Li, P., Yang, J., Islam, M. A., & Ren, S. (2025). **Making AI Less 'Thirsty'.** Communications of the ACM, 68(7), 54–61. https://doi.org/10.1145/3724499
3. Google (2025). **Measuring the environmental impact of AI inference.** https://cloud.google.com/blog/products/infrastructure/measuring-the-environmental-impact-of-ai-inference
4. Oviedo, F., et al. (2026). **Energy use of AI inference, efficiency pathways, and test-time scaling.** Joule, 102430. https://doi.org/10.1016/j.joule.2026.102430
5. **The water use of data center workloads: A review and assessment of key determinants.** (2025). Resources, Conservation & Recycling, 219, 108310. https://doi.org/10.1016/j.resconrec.2025.108310

## Next priorities

1. Replace the input-token weight with measurements across multiple modern serving stacks.
2. Add model-specific energy classes using reproducible benchmark data.
3. Separate direct cooling water from electricity-generation water.
4. Add region-sensitive WUE only when the inference region is actually known.
5. Support cache reads/writes without using API pricing as a hidden compute proxy.
6. Version every formula and retain raw token counts so estimates remain reproducible.