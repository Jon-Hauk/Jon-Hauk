### Jon Hauk

Edmonton, AB · targeting SOC Tier 1 / NOC / junior DevSecOps.

**Security+ · Network+ · A+ · CCSK v5**, plus CompTIA CIOS and CSIS
stackables. Six credentials in about nine weeks while working full time.
[Verify on Credly](https://www.credly.com/users/jon-nicholas-hauk/badges).

I build the tools I need, then run them on my own machines until they stop
lying. Industrial ops background: blast radius, rollback, and whether a
control actually ran.

**How I work:** most code in these projects was drafted with AI coding tools.
I own architecture, review, tests, and breakage. Assess me on how I use the
tools. I’ll follow a team’s policy, including unassisted work when required.

---

#### Open source

**[fieldkit](https://github.com/Jon-Hauk/fieldkit)** — read-only Windows/Linux
diagnostics for client engagements. One command, one report; nothing installed
or modified on the target. Windows: 42 checks on PowerShell 5.1. Linux: stdlib
Python 3.8+, 19 findings, **146 tests in CI** (verified 2026-09-11); container
checks run against a live Docker daemon in CI. Unreadable controls report
`UNKN`, not pass. Opt-in M365/Entra mode is read-only against a signed
engagement and refuses over-scoped sign-in.

**[automation-kits](https://github.com/Jon-Hauk/automation-kits)** — single-file
kits a client can run alone. No repo checkout, no deps, readable before trust.

**[win-sec-snapshot](https://github.com/Jon-Hauk/win-sec-snapshot)** — one-command
read-only Windows posture snapshot (JSON + Markdown). Value *names*, not values;
process *names*, not command lines.

**[localagent](https://github.com/Jon-Hauk/localagent)** — local Ollama harness;
every write and execution waits for approval.

**[engineering-records](https://github.com/Jon-Hauk/engineering-records)** —
ADRs, incidents, and lab write-ups. Example: six security gates committed where
they had never executed; five could not have worked as configured. Filed as an
incident instead of a quiet fix.

**[curriculum-proof](https://github.com/Jon-Hauk/curriculum-proof)** — verified
pipeline scores only (Alberta item content stays private): machine-scored
results published in-repo. Caveat from the repo: public forms may be in training
data; one run per form; not an unseen-problem claim.

---

#### Live

**[Veridian](https://veridian.today)** — multi-agent AI console (React 19,
Express 5, PostgreSQL/Drizzle, Clerk, SSE). I wrote the threat model and
security pass: fixed divergent paid-access checks (one ignored user ID),
constant-time API-key compare, quota reserved before the model call so abort
cannot bypass the daily cap.

---

#### Lab work (private; write-ups public)

- **IDS lab** — Suricata on Jetson Orin Nano. One signature fired on two
  deliberate requests; negative control quiet; separate PCAP confirmed payload.
  Evidence hashed + redaction gate.
  [Write-up](https://github.com/Jon-Hauk/engineering-records/blob/main/labs/LAB-2026-09-30-ids-suricata.md).
- **M365 / Entra posture** — fixtures green; first live tenant run found four
  defects. Revoked a standing admin write grant afterward.
  [Write-up](https://github.com/Jon-Hauk/engineering-records/blob/main/labs/LAB-2026-09-20-entra-identity.md).
- **Zero-trust tailnet as code** — default-deny, CI access tests, live-vs-repo
  policy diff. Permitted sources went from a /11 to four hosts, TCP-only, two
  ports — checked against the compiled filter, not the console success toast.
  [ADRs 0002–0004](https://github.com/Jon-Hauk/engineering-records/tree/main/adr).
- **genai** — local GPU + cloud image/video SDK; uv-locked; 44 tests; confirmation
  gate on spend.
- **ESP32-S3 HID** — boots locked; arms on deliberate hold; re-locks when a USB
  host appears.

*(sysmon → Sentinel triage portfolio is local scaffolding only — not listed
here until it’s public and scrubbed.)*

---

#### Find me

[LinkedIn](https://www.linkedin.com/in/jhauk780/) ·
[Credly](https://www.credly.com/users/jon-nicholas-hauk/badges)
