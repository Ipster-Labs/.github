<div align="center">
  <img src="./ipster_logo.png" alt="Ipster logo" width="360" />
  <h1>Ipster Labs</h1>
  <p><strong>Building the Ipster AI voice & automation stack — Edge Functions, MCP tools, integrations.</strong></p>
</div>

---

## About Ipster
Ipster bouwt een **slim, AI‑gedreven callcenter** dat integreert met je website, CRM, database en agenda. Zo worden klantvragen automatisch beantwoord of — waar nodig — **doorgezet naar een medewerker**. Resultaat: **snellere afhandeling** en minder wachttijd; data blijft in **Nederland**.  citeturn0search0

- “Jouw slimme callcenter, gedreven door AI.”  citeturn0search9
- In cases wordt ~**30–42%** reductie in statusvragen/telefoontjes genoemd.  citeturn0search13turn0search1

> Deze organisatiepagina beschrijft de **engineering codebase(s)** achter Ipster: functionele services, integraties en developer workflows.

---

## What lives here
- **Edge Functions (Supabase)** — voice/ops endpoints, webhooks, adapters
- **MCP repos** — model/context tools used by agents & internal apps
- **Integrations** — Shopify/CRM/telephony connectors, utility libs  citeturn0search10turn0search8
- **Infra & tooling** — CI/CD, observability, shared devcontainers

> Production code is kept modular and documented; GitHub is the **source of truth** for deploys.

---

## Repo conventions
**Mono‑style structure per repo**
```
supabase/
  functions/
    <group>/<name>/index.ts   # nested locally for clarity
```

**Flattened function names**
- Deploy pipeline flattens folders: `bedrijf1/functie1 → bedrijf1_functie1`
- Guarantees unique names in Supabase’s flat namespace

**Secrets**
- Supabase CLI uses a **Personal Access Token (`sbp_…`)**, stored as a repo secret.  
- Example secret name: `SUPABASE_ACCESS_TOKEN_ACCOUNT_BRUNO`

**Branches**
- `main` → protected; deploys changed functions only
- Feature branches → PR with checks

---

## CI/CD (high level)
- On push to `main`, CI:
  1. Detects changed folders under `supabase/functions/**`
  2. Flattens folder path to function name
  3. Deploys only those functions to project **`hhdxfkkanoqxqqzhrbkm`**
- Migrations/DB schema can live alongside functions (GitOps‑style)

---

## Getting started (internal)
1. Join the org and request access to required repos
2. Clone a repo and open **Codespaces** / local devcontainer
3. Add a function under `supabase/functions/<group>/<name>/index.ts`
4. Commit & open PR → merge to `main` → CI deploys that function

---

## Links
- **Website:** https://ipster.nl/  citeturn0search0
- **Dashboard:** https://dashboard.ipster.nl/  citeturn0search3
- **Changelog / features:** https://ipster.nl/changelog  citeturn0search16

---

## Contact
- engineering@ipster.nl • support@ipster.nl
- (c) Ipster B.V. — internal engineering organization
