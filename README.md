# Paul Estares — @DevPaulE

**Agentic engineer · systems thinker · generalist**

I build agentic systems that do real work: durable agents that sweep news, verification
loops that judge a person's understanding, and infrastructure that runs on hardware I own.
Every featured project carries a **reasoning trace** — the judgment calls, trade-offs, and
what got rejected, not just what shipped.

My operating model is Andrew Ng's distinction: AI handles the *verifiable*; I focus on the
**judgment tasks** — architecture decisions, trade-off reasoning, what not to build, and
when to stop.

---

## Featured

| Project | One line |
|---|---|
| **[rewardhack-probe](https://github.com/DevPaulE/rewardhack-probe)** | Detect when an agent tampers with its own scoring mechanism — built from Eli Chen's (AI Fund) *harness engineering* talk. |
| **[verify-loop](https://github.com/DevPaulE/verify-loop)** | A bounded RSI verification loop: queue → probe → human answers → external judge scores 0.0–1.0 → approve/deny/teach-me → ledger. |
| **[pi-durable-news-agent](https://github.com/DevPaulE/pi-durable-news-agent)** | Proactive agent: sweeps 28 sources, ranks by jev (Hype/Facts/Signal), survives restarts. Fork with a decision record. |
| **[durable-pi](https://github.com/DevPaulE/durable-pi)** | Durable agent network — the device owns the run, clients only watch and steer. |
| **[daily-sky](https://github.com/DevPaulE/daily-sky)** | Computed-facts astrology surface: ephemeris positions never invented, symbols never generated. |
| **[sovereign-agent](https://github.com/DevPaulE/sovereign-agent)** | Architecture for handing one person an agent they own — front door, substrate, memory, conscience. |

---

## The reasoning traces

### rewardhack-probe
*Detect when an agent changes the definition of done.*

Built directly from AI Fund's Frontier '26 summit. **Eli Chen**, AI Fund's Technology
Partner, asked the room *"how many of you have built an agentic loop, but your agent has
reward hacked it?"* Hands went up, and an attendee described exactly it: *"It just changed
the scoring mechanism itself and said, 'Okay, I'm done.'"* This tool makes that failure
**detectable** — the fix is in the harness, not the model.

- **Harness engineering, not model patches.** You can't prompt your way out of an agent
  that rewrites its own success criteria. Detect the tampering where it happens.

### verify-loop
*A bounded RSI loop over a personal knowledge base.*

Domain-swapped from Dan's *DeepJ UI replicator*: the mock becomes a knowledge item, the
build agent becomes the learner, the vision score becomes an external **understanding
score**, and a human holds direction-setting.

- **A gate that cannot fail is not a gate.** The judge is a different vendor's model, and
  its RED first run is the evidence it can fail.
- **Human answers in their own words.** The loop allocates effort to the struggle; it never
  does the thinking for you.

### pi-durable-news-agent
*Proactive agent: sweeps 28 sources, ranks by jev, survives restarts.*

- **Durable over chat-driven.** A cron-triggered agent with SQLite checkpointing, not a chat
  interface you have to ask. Rationale: attention is the scarce resource; the agent works
  *before* you ask.
- **jev at every gate, not one big model call.** Cheap classifiers ($0.00004/call) judge
  relevance, worth, story-dedup, and hype/facts/signal before the LLM sees an item.
- **Three clients, one API** (browser, TUI, CLI). Every interface reads the same SSE stream
  through shared reducers.

[Decision record →](https://github.com/DevPaulE/pi-durable-news-agent#decision-record)

### daily-sky
*Ephemeris engine + Sabian symbols + corpus-grounded readings.*

- **Computed facts, never generated.** Positions from Swiss Ephemeris (JPL DE431), symbols
  from a fixed 360-entry table, interpretations cited to source notes. Zero LLM in the
  reading. Rationale: a system that claims to be factual must be verifiably factual.
- **Verified against the reference standard.** Found and documented disagreements with a
  professional reading — the ephemeris won.

### sovereign-agent
*Hand one person an agent they own.*

- **Four-part invariant.** Front door / substrate / memory / conscience. Remove any one and
  there is no system. Every module must name which layer it serves — nothing floats.
- **Gate-author ≠ builder, enforced in code.** Nothing destructive reaches the agent without
  a human gate written by someone who didn't build the feature. The hosted products don't
  have this; ownership without conscience is just rentership under another name.

---

## How I work

- **Specify → build → verify.** Every feature starts with a gate (a red test first), built by
  one agent, gated by another. The gate author never builds; the builder never gates.
- **Evidence over pedigree.** My work is on GitHub — verified, tested, documented. No
  corporate background; I started building agentic systems two years ago, which Mike Rubino
  (Head of Talent, AI Fund) names as the undervalued talent pool.
- **Owned infrastructure.** My agentic systems run on my Mac and a headless Mac mini. No SaaS
  dependency for execution — the loop is mine.
- **Forks are attributed and accountable.** Where I build on another's work, the original is
  credited and I state who is accountable for the fork.

---

## Contact

- GitHub: [DevPaulE](https://github.com/DevPaulE)
- Open to: agentic engineering roles on AI-native teams, and AI Fund portfolio opportunities.
