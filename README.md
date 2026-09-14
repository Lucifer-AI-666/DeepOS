# DeepOS

**Sistema operativo cognitivo personale — local-first, policy-driven, audit completo.**

> Il modello propone. La policy decide. L'esecutore agisce. L'audit registra.

DeepOS unisce in un unico monorepo i componenti dell'ecosistema TAUROS:

| Cartella | Componente | Ruolo |
|----------|-------------|-------|
| `core/` | TAUROS Cognitive OS v0.4.1 | Cervello: memoria, planner, policy, esecutore, audit, privilegi |
| `mobile/` | tauros-mobile-sentinel | Sensore di sicurezza sul telefono: osservazione, correlazione, risk engine, audit ledger |
| `evaluator/` | TaurosAgenteDelProblema | Pre-filtro: analizza e riformula la richiesta prima del planner |
| `ui/` | divine_nexus + taurosweb | Interfaccia mobile: chat, identità, automazioni, shell |

## Filosofia

Il telefono non è un'app isolata: è un **dispositivo dipendente** dal sistema cognitivo. Il cervello vive nel core, il sensore osserva il device, l'evaluator evita soluzioni al problema sbagliato, l'UI parla con l'utente.

## Struttura prevista

```text
DeepOS/
├── README.md
├── VISION.md
├── ARCHITECTURE.md
├── core/          # Cognitive OS (Python, FastAPI, PWA)
├── mobile/        # Mobile Sentinel (Python + Kotlin roadmap)
├── evaluator/     # Problem Agent (docs + bridge)
├── ui/            # App mobile (Expo / TypeScript)
│   ├── divine_nexus/
│   └── taurosweb/
├── docs/          # Filosofia, roadmap, benchmark
└── scripts/       # Install, start, migrate
```

## Stato attuale

- Struttura monorepo creata.
- I componenti esistenti restano nei repo originali; qui vivono come riferimento e punto di unione.
- Prossimo passo: portare il codice di `core/` e `mobile/` dentro le rispettive cartelle.

## Licenza

MIT per il core e l'evaluator. Apache-2.0 per il mobile sentinel. Vedi i singoli componenti.
