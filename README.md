# energy-attest-holo

**Honest, holographic energy-attestation surface for the SZL Holdings sovereign mesh.**

Static, self-contained HTML page (0 runtime CDN) that reports the estate's **energy
attestation** posture and never fabricates a joule. When there are no live NVML meters —
the current, honest state — it attests **UNAVAILABLE in RED**. An attestation page that goes
RED when the meters are dead is the honesty flex, not a bug.

- **Live Space:** https://huggingface.co/spaces/SZLHOLDINGS/energy-attest-holo
- **Status:** ROADMAP → **LIVE** (static page live; sovereign energy meters honestly **DOWN**
  until the sovereign boxes + Cloudflare tunnels are powered up — the "no live meters yet"
  state is the honest launch state).

## What it shows

| Panel | Source (keyless, client-side) | Label |
|---|---|---|
| Sovereign mesh energy meters | a11oy [`/govern/health`](https://szlholdings-a11oy.hf.space/api/a11oy/v1/govern/health) — per-engine `LIVE`/`DOWN`, per-meter NVML reachability (`530` → UNAVAILABLE), `engines_live/total` | **REPORTED** (a11oy self-report) + **MEASURED** (this browser's probe) |
| GB grid carbon intensity | [National Grid ESO Carbon Intensity API](https://carbonintensity.org.uk) `/intensity` | **REPORTED** (grid context, not our own compute) |
| GB generation mix | Carbon Intensity API `/generation` | **REPORTED** |

## Honesty doctrine (binding)

- **MEASURED** = this browser saw the real HTTP result · **REPORTED** = upstream self-report
  pass-through · **UNAVAILABLE** = source unreachable / capability honestly absent — never fabricated.
- **Energy is null unless a real NVML meter reports.** No invented joules.
- **Λ = Conjecture 1** — advisory, never proven, trust ceiling 0.97, never green.
- **0 runtime CDN** — no external libraries, no web fonts; a single vanilla-JS 2D canvas
  draws the holographic lattice.

## Deploy

Hugging Face **static** Space — the root `index.html` is served as-is. To update the live
Space, commit `index.html` + `README.md` to the Space repo (or mirror this GitHub repo).

## Estate

Part of the SZL Holdings estate: [a-11-oy.com](https://a-11-oy.com) ·
[szl-energy-attest](https://github.com/szl-holdings/szl-energy-attest) ·
[🤗 SZLHOLDINGS](https://huggingface.co/SZLHOLDINGS) · Λ = Conjecture 1.

## License

[Apache-2.0](LICENSE) — consistent with the SZL Holdings estate convention (a11oy, killinchu,
anatomy, szl-energy-attest are all Apache-2.0).
