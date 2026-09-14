# DeepOS — Architettura

```text
Utente (telefono / PWA / Telegram)
        │
        ▼
   UI (divine_nexus / taurosweb)
        │
        ▼
   Evaluator (Problem Agent)
   - analizza la richiesta
   - separa fatti / ipotesi / obiettivi
   - riformula o segnala lacune
   - decide: PROCEED / INTEGRATE / REFRAME
        │
        ▼
   Core (Cognitive OS)
   - memoria personale (FTS5)
   - planner multi-step (regole + LLM)
   - policy + PathGuard
   - tools (read-only + scritture supervisionate)
   - provider LLM (Ollama / Groq / OpenAI)
   - privilegi a livelli
   - audit ledger
        │
        ▼
   Mobile Sentinel (sul device)
   - collectors (telemetria, permessi, rete, UI)
   - correlator temporale
   - risk engine + Trust Core
   - action gate (propone, non esegue)
   - audit ledger (hash chain)
        │
        ▼
   Esecutore controllato + Audit
```

## Flusso tipico

1. L'utente chiede qualcosa all'UI.
2. L'Evaluator analizza: è il problema giusto? Manca qualcosa?
3. Se sì, il Core pianifica e la policy decide ogni step.
4. Il Sentinel osserva il device e segnala anomalie al Core.
5. L'esecutore agisce solo se approvato; l'audit registra tutto.

## Separazione dei ruoli

| Componente | Decide | Esegue | Osserva | Audit |
|------------|--------|--------|---------|-------|
| Evaluator | riformula | no | no | sì |
| Core | policy | sì (controllato) | no | sì |
| Sentinel | risk | no (propone) | sì | sì |
| UI | presentazione | no | no | no |
