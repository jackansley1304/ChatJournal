# Chat Journal

A private, encrypted journal that lives entirely in your browser. No servers, no accounts, no tracking. Just you and your thoughts.

![License](https://img.shields.io/badge/license-MIT-blue)
![Size](https://img.shields.io/badge/size-~45KB-green)
![Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)

---

### Features

- **End-to-end encrypted** — AES-256-GCM with PBKDF2 key derivation (600,000 iterations)
- **Auto-Lock** — a new toggle to lock after 1Min, 5Mins, 10Mins, 15Mins, 30Mins of inactivity
- **Zero network requests** — `fetch` and `XMLHttpRequest` are explicitly blocked in code
- **Two-voice journaling** — Toggle between "Me" and "Inner Self" perspectives
- **Ideas tab** — Quick-capture space for fleeting thoughts
- **Full-text search** — Search across all entries and ideas
- **Encrypted backup/restore** — Export and import your journal as encrypted JSON files
- **PWA support** — Install as a standalone app on your phone or desktop
- **Dark mode** — System-respecting theme toggle
- **No dependencies** — Single HTML file, no build step, no frameworks
- **Multi Chat lists** - Multi chat lists for processing different things

---

## How to Use

1. Download `index.html`
2. Open it in any modern browser
3. Set a password
4. Start writing

or

You can head to the URL using your browser and start using it. 

That's it. No installation, no server, no configuration.

To install as a phone app: open the file in your browser, tap "Add to Home Screen." 

---
The Psychology Behind Two-Voice Journaling: 

- Internal Family Systems (IFS): Your mind has multiple "parts" — writing as them (not about them) facilitates self-dialogue.
- Narrative Therapy: Externalizing a thought by giving it a separate voice helps you step outside it.
- Expressive Writing (Pennebaker): Translating chaotic emotions into structured language improves psychological and physical outcomes.
- Chat Format: Conversational bubbles feel lower-pressure than a blank page and create natural turn-taking.

Honest Limitations:

- Rumination: The inner voice can reinforce self-criticism instead of processing. 
- False resolution: Writing it down can feel like "dealing with it".
- Echo chamber: Both voices are yours — blind spots stay blind.
- Not therapy: Cannot replace professional support, Complements therapy, doesn't substitute it.
 
## Privacy Model

The privacy design is intentionally aggressive:

| Layer | Implementation |
|---|---|
| Encryption | AES-256-GCM via Web Crypto API |
| Key derivation | PBKDF2 with SHA-256, 600K iterations, random 256-bit salt |
| Storage | IndexedDB (local only, no cookies) |
| Network | `fetch()` and `XMLHttpRequest` are overridden and blocked |
| Telemetry | None. Zero analytics, zero tracking, zero external requests |
| Backup format | Encrypted JSON — the exported file is ciphertext, not plaintext |

Your unencrypted journal text exists only in memory while the app is open. On disk, it's always encrypted.

---

## Contributing

Contributions are welcome. Some things that would make this better:

- [x] Minimum password length enforcement
- [x] Rate limiting on password attempts
- [x] Multi Chat list 
- [x] PBKDF2 iteration count increase (OWASP recommends 600,000 for SHA-256)
- [x] Auto-Lock feature
- [ ] Storage usage indicator visible outside settings
- [ ] Accessibility audit (screen reader support, keyboard navigation)
- [ ] Optional prompt/question system to guide reflection
- [ ] Import/export in plaintext (for users who want to move their data elsewhere)
- [ ] Option to automatic switching from me to inner self after a message

If you're working on a PR, please keep the single-file architecture. The simplicity is a feature, not a limitation.

---


## Resources

If you're interested in the therapeutic ideas behind this tool:

- Pennebaker, J.W. — *Opening Up by Writing It Down* (expressive writing research)
- Schwartz, R.C. — *No Bad Parts* (Internal Family Systems)
- White, M. & Epston, D. — *Narrative Means to Therapeutic Ends* (narrative therapy and externalization)
- Nolen-Hoeksema, S. — Research on rumination vs. processing (understanding the risk side)

If you or someone you know is struggling, please reach out to a mental health professional or contact a crisis helpline in your region.
