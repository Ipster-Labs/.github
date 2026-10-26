<div align="center">
  <img src="./ipster_logo.png" alt="Ipster logo" width="360" />
  <h1>Ipster Labs</h1>
  <p><strong>AI agents that handle customer contact across every channel — phone first, plus WhatsApp, SMS, and email — connected to your own systems.</strong></p>
</div>

---

## About Ipster
Ipster builds AI agents that act as a real employee for Dutch SMEs: answering and making calls, chatting on WhatsApp, following up by SMS or email — looking up the customer in the client's own CRM or ticketing system, booking or rescheduling appointments, quoting jobs, and handing off to the right human when a case genuinely needs one. Telephony is where it started and remains the core, but the same agent logic and integrations now run across channels. Data is hosted in the Netherlands. See https://ipster.nl/ for more.

Each client gets its own agent wired into their own systems: CRM, ticketing, scheduling, payments — whatever they already run on.

This organization page describes the engineering behind that: the platform that builds and runs the agents, and the client-specific work layered on top.

---

## The agent platform

| Repo | Does |
|---|---|
| **[app.ipster.ai](https://github.com/Ipster-Labs/app.ipster.ai)** | The in-house platform for building, configuring, and running the agents — React/TypeScript on Vercel + Railway, LiveKit Cloud for realtime voice, Supabase for data. The product clients log into. |
| **[Supabase-Sync](https://github.com/Ipster-Labs/Supabase-Sync)** | Source of truth for the Edge Functions each agent calls during a conversation: inbound webhooks (pull up the caller/contact), mid-conversation tools (look up orders, book appointments, create tickets), post-interaction logging, per-client routing. |
| **[ipster-website](https://github.com/Ipster-Labs/ipster-website)** | The public site at ipster.nl. |
| **[ipster-skills](https://github.com/Ipster-Labs/ipster-skills)** | Organisation-wide Claude.ai skills — source of truth for the AI tooling the team builds all of the above with. |
| **[klant-data](https://github.com/Ipster-Labs/klant-data)** | Knowledge bank per client: wikis, raw sources, flow diagrams — what each agent is supposed to do and why. |

Client- and integration-specific repos sit on top of this, wiring individual clients' CRMs, ticketing systems, and telephony into their agent: **[storageshare-agent](https://github.com/Ipster-Labs/storageshare-agent)**, **[agent-call-logs](https://github.com/Ipster-Labs/agent-call-logs)**, **[profile-gaston-mcp](https://github.com/Ipster-Labs/profile-gaston-mcp)**.

GitHub is the source of truth for deploys.

---

## Also here — internal R&D

A few projects support the platform without being the product themselves: **[Ipster-Analyzer](https://github.com/Ipster-Labs/Ipster-Analyzer)** turns recorded calls into searchable, analyzed data (running on our own DGX Spark hardware); **[tas-ipster-dashboard](https://github.com/Ipster-Labs/tas-ipster-dashboard)** turns a client's protocol documents into version-controlled prompts served per phone number. For the full technical picture of these, see [`overdrachtdocument`](https://github.com/Ipster-Labs/overdrachtdocument) (snapshot as of 28 August 2026).

---

## Links
- Website: https://ipster.nl/
- Platform: https://app.ipster.ai/

---

<table>
<tr>
<td>

## Contact
support@ipster.nl
(c) Ipster B.V. — internal engineering organization

</td>
<td align="right" width="200">
  <img src="./Subject.png" alt="Subject" width="160">
</td>
</tr>
</table>
