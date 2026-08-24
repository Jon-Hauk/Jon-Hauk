### Jon Hauk

Infrastructure automation and security, mostly Windows. Edmonton, AB.

**Security+ · Network+ · A+ · CCSK v5** - all four earned in under three months,
while working full time.

I build tools I need, then run them against my own machines until they stop
lying to me. Background is industrial operations, so I think in terms of blast
radius, rollback, and whether a control actually ran.

**How I work:** most of the code in these projects was drafted with AI coding
tools. I choose the architecture, review what lands, write and run the tests,
and own the result when it breaks. I'd rather be assessed on how well I use the
tools than have it come up later - and I'll work to whatever policy a team has,
including unassisted where that's the requirement.

---

#### Open source

**[fieldkit](https://github.com/Jon-Hauk/fieldkit)** - read-only Windows diagnostics for client engagements.

42 checks across system inventory, network fault isolation, and a security
baseline. Windows PowerShell 5.1, no dependencies. Nothing is installed on the
target machine and nothing on it is modified - the report is the only thing
written. Three-state exit contract for RMM integration, and a check that could
not read its input reports `UNKN` instead of being quietly counted as a pass.

---

#### Live

**[Veridian](https://veridian.today)** - multi-agent AI console. React 19, Express 5,
PostgreSQL/Drizzle, Clerk for identity, per-agent responses streamed over SSE.
Public API with API-key auth and an MCP endpoint. I wrote its threat model and
did the security pass on it: consolidated two divergent paid-access checks after
finding one ignored the user ID entirely, moved API-key comparison to constant
time, and made the usage quota reserve before the model call so aborting
mid-request cannot bypass the daily cap.

---

#### Not public, happy to walk through

- **Zero-trust tailnet policy as code** - default-deny across four nodes, held in
  version control with an access-test block and a documented rollback. Verified
  against the compiled packet filter rather than the console success message:
  permitted sources went from an entire /11 range to four explicit hosts, TCP
  only, two ports, with UDP and ICMP dropped. The best find wasn't the policy -
  a VM deleted two weeks earlier still held an authorized node key and a live
  address.
- **genai** - image/video SDK over local GPU and cloud backends. Python, uv-locked,
  44 tests. Confirmation gate on anything that spends money.
- **ESP32-S3 firmware** - USB HID keyboard that boots locked, arms only on a
  deliberate hold, and re-locks whenever a USB host appears.
- **An incident writeup I'm oddly proud of** - six security gates committed to a
  repo that had never once executed, five of which could not have worked as
  configured. Filed it as an incident instead of quietly fixing it, because a
  config that only looks configured is worse than no config.

---

#### Find me

[LinkedIn](https://www.linkedin.com/in/jhauk780/)
