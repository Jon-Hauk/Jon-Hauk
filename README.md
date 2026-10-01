### Jon Hauk

IT support and security, Windows and Linux. Edmonton, AB.

**Security+ · Network+ · A+ · CCSK v5**, plus CompTIA's CIOS and CSIS
stackables: six credentials in nine weeks, earned while working full time.
[Verify them on Credly](https://www.credly.com/users/jon-nicholas-hauk/badges).

I build tools I need, then run them against my own machines until they stop
lying to me. My background is industrial operations, so I think in terms of
blast radius, rollback, and whether a control actually ran.

**How I work:** most of the code in these projects was drafted with AI coding
tools. I choose the architecture, review what lands, write and run the tests,
and own the result when it breaks. I'd rather be assessed on how well I use the
tools than have it come up later. I'll work to whatever policy a team has,
including unassisted where that's the requirement.

---

#### Open source

**[fieldkit](https://github.com/Jon-Hauk/fieldkit)**: read-only diagnostics for
client engagements, Windows and Linux. Windows has 42 checks across system
inventory, network fault isolation and a security baseline, in PowerShell 5.1
with no dependencies. Linux has the same contract in standard-library Python
3.8+: 19 findings across 15 areas and 146 tests in CI, with container checks
run against a live Docker daemon. Nothing is installed on the target and
nothing is modified. A check that could not read its input reports `UNKN`, not
a pass.

**[automation-kits](https://github.com/Jon-Hauk/automation-kits)**: single-file
diagnostic kits handed to a client to run on their own machine. No repo, no
dependencies, readable before they trust it.

**[win-sec-snapshot](https://github.com/Jon-Hauk/win-sec-snapshot)**: a
one-command, read-only Windows security posture snapshot (JSON + Markdown). It
records value names, not values, and process names, not command lines.

**[localagent](https://github.com/Jon-Hauk/localagent)**: a coding harness for
local Ollama models where every write and every execution waits for my
approval.

**[engineering-records](https://github.com/Jon-Hauk/engineering-records)**:
decision records, incident reports and lab write-ups from my private security
lab. The incident I'm oddly proud of: six security gates committed to a repo
where they had never once executed, five of which could not have worked as
configured. I filed it as an incident instead of quietly fixing it, because a
config that only looks configured is worse than no config.

---

#### Live

**[Veridian](https://veridian.today)**: a multi-agent AI console built with
React 19, Express 5, PostgreSQL/Drizzle and Clerk for identity, with per-agent
responses streamed over SSE. It has a public API with API-key auth and an MCP
endpoint. I wrote its threat model and did the security pass on it:
- consolidated two divergent paid-access checks after finding one ignored the
  user ID entirely;
- moved API-key comparison to constant time;
- made the usage quota reserve before the model call, so aborting mid-request
  cannot bypass the daily cap.

---

#### Lab work (private, happy to walk through)

- **IDS lab**: Suricata on a Jetson Orin Nano. One signature fired live on
  two deliberate requests, a negative control stayed quiet, and a separate
  packet capture confirmed the payload. The evidence is hashed and passes a
  redaction gate before it is committed.
  [Write-up](https://github.com/Jon-Hauk/engineering-records/blob/main/labs/LAB-2026-09-30-ids-suricata.md).
  Next: a Wazuh SIEM ingesting it.
- **M365 / Entra posture lab**: five audits said nothing was open. The first
  live run against a real tenant found four defects in one night, every one
  invisible to the test fixtures. Afterwards I found a standing admin write
  grant on my own tenant and revoked it, and I didn't pre-grant the next
  audit's access either.
- **Zero-trust tailnet policy as code**: default-deny across four nodes, with
  an access-test block in CI and a job that diffs the live policy against the
  repo. At first apply, the permitted sources went from an entire /11 range to
  four explicit hosts, TCP only, two ports, verified against the compiled
  packet filter rather than the console's success message. The best find
  wasn't the policy: a VM deleted two weeks earlier still held an authorized
  node key and a live address.
- **genai**: an image/video SDK over local GPU and cloud backends. Python,
  uv-locked, 44 tests, and a confirmation gate on anything that spends money.
- **ESP32-S3 firmware**: a USB HID keyboard that boots locked, arms only on a
  deliberate hold, and re-locks whenever a USB host appears.

---

#### Find me

[LinkedIn](https://www.linkedin.com/in/jhauk780/) ·
[Credly](https://www.credly.com/users/jon-nicholas-hauk/badges)
