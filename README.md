# Paul Estares — @DevPaulE

**Agentic engineer · systems thinker · generalist**

I build agentic systems that do real work — durable agents that sweep news,
parse ephemeris data, and run personal infrastructure on owned hardware. Every
project below has a **reasoning trace**: the judgment calls, trade-offs, and
what got rejected, not just what shipped.

My operating model is Andrew Ng's distinction: AI handles the *verifiable* —
I focus on the *judgment tasks*: architecture decisions, trade-off reasoning,
what not to build, and when to stop.

---

## Projects

### Pi Durable News Agent
*Proactive agent: sweeps 28 sources, ranks by jev (Hype/Facts/Signal), survives restarts*

Decision trace:
- **Durable over chat-driven.** A cron-triggered agent with SQLite checkpointing, not a chat interface you have to ask. Rationale: attention is the scarce resource; the agent should work *before* you ask.
- **jev at every gate, not one big model call.** Cheap classifiers ($0.00004/call) judge relevance, worth, story-dedup, importance, and hype/facts/signal before the LLM ever sees an item. Trade-off: more moving parts, lower cost, no single point of hallucination.
- **Three clients, one API** (browser, TUI, CLI). Rationale: every interface reads the same SSE stream through shared reducers; a capability list test fails if any client is missing a feature.

[Read more →](https://github.com/DevPaulE/pi-durable-news-agent#decision-record)

### daily-sky
*Ephemeris engine + Sabian symbols + corpus-grounded readings, feeding a pi widget*

Decision trace:
- **Computed facts, never generated.** Positions from Swiss Ephemeris (JPL DE431), symbols from a fixed 360-entry table, interpretations cited to source notes. Zero LLM in the reading. Rationale: astrology that claims to be factual must be verifiably factual — one wrong degree and the whole thing is performance.
- **Verified against astro.com.** Every body position checked against the reference standard. Found and documented disagreements with a professional reading (Moon, Ascendant, Chiron all off) — ephemeris wins.

[Read more →](https://github.com/DevPaulE/daily-sky)

### Sovereign Agent
*Architecture for handing one person an agent they own*

Decision trace:
- **Four-part invariant.** Remove any one (front door / substrate / memory / conscience) and there is no system. Every module must name which layer it serves — nothing floats.
- **Gate-author ≠ builder** enforced in code. Nothing destructive reaches the agent without a human gate written by someone who didn't build the feature. Rationale: the hosted products don't have this; ownership without conscience is just rentership under another name.

[Read more →](https://github.com/DevPaulE/sovereign-agent)

### Fusion Harness
*Multi-seat debate + collaborate across models on one checkout*

Decision trace:
- **No judge seat.** Dan's multi-seat design deliberately has no judge verdict — the human decides. Rationale: a judge that overrules introduces the same single-point failure it solves.
- **Proposal-first, then build.** The cockpit decides; the build executes. Rationale: this is the Foundry Loop — the operator is the specifier, the machine is the builder, never the reverse.

[Read more →](https://github.com/DevPaulE/fusion-harness)

---

## How I work

- **Specify → build → verify.** Every feature starts with a gate (red test first), built by one agent, gated by another. The gate author never builds; the builder never gates.
- **Evidence over pedigree.** My work is on GitHub, verified, tested, and documented. No corporate background — I started building agentic systems 2 years ago, which Mike Rubino (AI Fund) names as the undervalued talent pool.
- **Owned infrastructure.** My agentic systems run on my Mac and a headless Mac mini. No SaaS dependency for execution — the loop is mine.

---

## Contact

- GitHub: [DevPaulE](https://github.com/DevPaulE)