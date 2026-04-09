# 🕵️ Threat Actor Profiler

> Actor name → aliases · MITRE ATT&CK · tooling · campaigns · hunting pivots

Part of the [SecOps AI Suite](https://dgiry.github.io) — client-side tools for security analysts.

**Live:** [dgiry.github.io/threat-actor-profiler](https://dgiry.github.io/threat-actor-profiler)

---

## What it does

Enter a threat actor name — APT28, LockBit, Lazarus Group, Scattered Spider — and get a structured analyst-grade profile:

| Section | Content |
|---------|---------|
| **Identity** | Origin, actor type, motivation, active since |
| **Targeting** | Sectors and regions typically attacked |
| **MITRE ATT&CK** | Top techniques with tactic tags and actor-specific usage |
| **Tooling & malware** | Named tools with type and usage description |
| **Campaigns** | Known operations with year and target/impact |
| **Infrastructure** | C2 patterns, hosting preferences, domain generation |
| **Hunting pivots** | Actionable detection ideas per actor behavior |

---

## Deep links

```
?actor=APT28
?actor=LockBit&context=ransomware+observed+in+healthcare+sector
?context=45.142.212.100+Cobalt+Strike+beacon
```

All parameters are URL-encoded. `?context=` accepts IOC fragments, campaign names, or incident descriptions.

---

## Pipeline position

```
Extract → Pivot → Profile → Enrich → Explain → Detect → Respond
                    ↑ here
```

Fits between IOC Pivot (indicators) and Alert Explainer (alert context). Once you identify an IOC or suspect an actor, profile them before diving into detection.

**Bridges out:**
- 🔭 [IOC Pivot Hub](https://dgiry.github.io/ioc-pivot) — pivot on infrastructure IOCs
- 🚨 [Alert Explainer](https://dgiry.github.io/alert-explainer) — explain the alert in context of this actor
- ✍️ [SIGMA Generator](https://dgiry.github.io/sigma-generator) — generate detection rules pre-filled with techniques
- 📖 [Playbook Builder](https://dgiry.github.io/playbook-builder) — build IR playbook for this actor

---

## Privacy & API key

- 100% client-side — no backend, no telemetry
- Your OpenAI key is stored in `localStorage` under `cv_oai_key` — shared with all suite tools
- Nothing is sent anywhere except OpenAI's API when you click "Profile actor"

---

## Export

Click **📋 Copy markdown** to get the full profile as a markdown document — ready for Notion, Obsidian, or a post-mortem report.

---

## Run locally

```bash
git clone https://github.com/dgiry/threat-actor-profiler
cd threat-actor-profiler
python3 -m http.server 8080
# open http://localhost:8080
```

---

## License

MIT — see [LICENSE](LICENSE)

Part of the [SecOps AI Suite](https://dgiry.github.io) by [@dgiry](https://github.com/dgiry)
