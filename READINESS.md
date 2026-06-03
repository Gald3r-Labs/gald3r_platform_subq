# gald3r Readiness Report — SubQ Code

> An honest accounting of how much of the gald3r framework installs natively on this
> platform, what degrades to an approximation, and what has no native home yet.
> Generated from a live documentation crawl on 2026-06-02.

**Overall readiness: ❌ Not a host.** SubQ Code isn't a standalone coding agent — it's a
long-context layer that plugs *into* Claude Code, Codex, or Cursor. It exposes none of its
own extension points, so gald3r installs into the host you're already using, not into SubQ.
The C.R.A.S.H. grid below reads empty for exactly that reason.

## C.R.A.S.H. capability grid

| | Capability | Native? | What gald3r gets here | The gap |
|---|---|:---:|---|---|
| **C** | Commands | ❌ | — | No slash/custom command system; any commands you see come from the host (Claude Code/Codex/Cursor), not SubQ |
| **R** | Rules | ❌ | — | No persistent-rules / memory / always-on-instructions file; the 1M–12M token window loads the whole repo instead |
| **A** | Agents | ❌ | — | Not a multi-agent framework; SubQ is itself a layer invoked by an existing agent, with no sub-agent/role definitions |
| **S** | Skills | ❌ | — | No `SKILL.md` / Agent-Skills engine; gald3r skills have no native host |
| **H** | Hooks | ❌ | — | No lifecycle/event hooks; the only "automatic" behavior is internal turn-redirection, not a user-configurable script |

_Legend: ✅ native · ⚠️ partial / approximated · ❌ no native mechanism · ❓ unverified_

**Beyond C.R.A.S.H. — MCP: ❌** No native MCP. `docs.subq.ai` exposes an OpenAI-compatible
Chat Completions API (Base URL, key, `/v1/chat/completions`, streaming + tool use) — an HTTP
contract, not Model Context Protocol. Any MCP comes from the host SubQ plugs into.

## Adoptable extras (non-C.R.A.S.H.)

Platform-native strengths gald3r can lean on, and which need wiring:

| Feature | Status | gald3r fit |
|---|:---:|---|
| Subquadratic long-context model (1M prod, ~12M research; SSA ≈ O(n)) | ✅ present | Whole-repo exploration in one window — gald3r reasons over more context, no chunking |
| OpenAI-compatible Chat Completions API (`/v1/chat/completions`) | ✅ present | A real automation entry point for gald3r tooling via the standard endpoint |
| Streaming + OpenAI-style tool calling (API level) | ⚙️ needs customization | Usable by gald3r at the API layer; no agent-level workflow extensibility is exposed |
| Console / playground (`console.subq.ai`, `playground.subq.ai`) | ✅ present | Key management and a try-it surface; no gald3r work required |
| Native instruction-file convention (`SUBQ.md` / `.subq/`) | ➖ n.a. | None published; gald3r context reaches SubQ only indirectly via the host's `AGENTS.md` |

## A different shape

This isn't a standalone coding agent — it's a layer that runs *inside* a host tool. So gald3r doesn't install here directly; it installs into the host you're already using (Claude Code, Codex, or Cursor), and this platform's strengths ride along underneath. The C.R.A.S.H. grid above reads empty for exactly that reason: those surfaces belong to the host, not to this layer.

When you want gald3r as its own agent — the full framework standing on its own rather than riding inside another tool — that's the native build: **gald3r_agent**, on the **gald3r throne** over the **gald3r_world_tree**.

> ### gald3r_agent — coming soon. 🌳

---

<sub>Capabilities verified against the platform's official documentation on 2026-06-02, and
re-verified each release via the gald3r platform-docs crawl. This report describes gald3r's
third-party adaptation surface; it is not an endorsement or critique of the platform itself.</sub>
