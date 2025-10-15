<div align="center">
  <img src="./ipster_logo.png" alt="Ipster logo" width="360" />
  <h1>Ipster Labs</h1>
  <p><strong>Building the Ipster AI voice and automation stack: Edge Functions, MCP tools, integrations.</strong></p>
</div>

---

## About Ipster
Ipster builds an AI-driven call center that integrates with your website, CRM, database, and calendar. Routine questions are handled automatically and complex cases are routed to a human. Data is hosted in the Netherlands. See https://ipster.nl/ for more details.

This organization page describes the engineering codebases behind Ipster: services, integrations, and developer workflows.

---

## What lives here
- Edge Functions (Supabase): voice/ops endpoints, webhooks, adapters
- MCP repositories: model and context tools used by agents and internal apps
- Integrations: Shopify/CRM/telephony connectors, utility libraries
- Infra and tooling: CI/CD, observability, shared devcontainers

GitHub is the source of truth for deploys.

---

## Repository conventions
**Folder layout per repo**

```
supabase/
  functions/
    <group>/<name>/index.ts   # nested locally for clarity
```

**Flattened function names**
- The deploy pipeline flattens folders: `bedrijf1/functie1` -> `bedrijf1_functie1`
- Ensures unique names in Supabase's flat namespace

**Secrets**
- The Supabase CLI uses a Personal Access Token that starts with `sbp_...` and is stored as a repository secret.
- Example secret name: `SUPABASE_ACCESS_TOKEN_ACCOUNT_BRUNO`

**Branches**
- `main` is protected and deploys changed functions only
- Feature branches go through PRs with checks

---

## CI/CD overview
On push to `main`, CI:
1. Detects changed folders under `supabase/functions/**`
2. Flattens the folder path to a function name
3. Deploys only those functions to project `hhdxfkkanoqxqqzhrbkm`

Database schema migrations can live alongside functions (GitOps style) if needed.

---

## Getting started (internal)
1. Join the org and request access to the needed repositories
2. Clone a repo and open Codespaces or a local devcontainer
3. Add a function under `supabase/functions/<group>/<name>/index.ts`
4. Commit and open a PR; after merge to `main` the CI deploys that function

---

## Links
- Website: https://ipster.nl/
- Dashboard: https://dashboard.ipster.nl/
- Changelog: https://ipster.nl/changelog

---

## Contact
engineering@ipster.nl • support@ipster.nl  
(c) Ipster B.V. — internal engineering organization
