# *WILDCARD × Supabase — Possibility Engine

An evidence-aware experiment ledger for recombining problems, capabilities, resources, constraints, signals, and audiences into falsifiable hypotheses.

## Deployment status (October 31, 2026)
- Supabase project: [*WILDCARD × Supabase](https://supabase.com/dashboard/project/bmtplzmjvinhoimktttw).
- Migration `wildcard_possibility_engine_v1` applied successfully.
- Three empty tables: `public.wildcard_atoms`, `public.wildcard_hypotheses`, and `public.wildcard_tests`.
- Row-level security enabled for all tables, and three policies restrict access to `auth.uid() = user_id`.
- Security advisors returned zero findings at deployment time.
- Function `public.wildcard_candidate_pairs(integer)` generates previously untested candidate pairings using invoker permissions.
- No Vercel deployment or authentication UI yet. Earlier standalone prototype is a local demo, not connected to Supabase.

## Operating model
1. Capture sourced observations as **atoms** (including kind, tags and optional source URL).
2. Propose cross-domain **hypotheses** with testable predictions.
3. Record **tests** and evidence, distinguishing supported, refuted and inconclusive outcomes.
4. Learn from evidence rather than treating unverified ideas as discoveries.

## Security and deployment precautions
Use only the Supabase publishable key in client code, never a service-role or secret key. Require user login, test cross-user isolation, and verify read/write before publishing. Review Vercel integration permissions and pricing before connecting it. No paid AI calls are necessary for the core experiment.

## Next steps
- Commit a SQL migration snapshot, an authenticated frontend, and integration tests.
- Connect GitHub to Vercel once signed in; configure the Supabase project URL and publishable key.
- Run a real end-to-end write/read test and then log the first evidence-backed experiment.

**Scope:** Standalone, near-$0 experiment. Do not merge it with LEVERAGE//SEEKER until outcomes justify it.
