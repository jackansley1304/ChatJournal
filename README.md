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

## The Psychology Behind Two-Voice Journaling

The "Me / Inner Self" toggle isn't a gimmick — it's been in several evidence-based therapeutic approaches.

### Externalizing Internal Dialogue

Traditional journaling asks you to write *about* your thoughts. This app asks you to write *as* different parts of yourself. That distinction matters.

**Internal Family Systems (IFS)** therapy is built around the idea that the mind contains multiple "parts" — a protective part, a vulnerable part, a critical part — and that healing comes from facilitating dialogue between them. The two-voice interface provides a lightweight structure for this kind of self-dialogue.

**Narrative therapy** uses a technique called externalization, where you separate yourself from the problem by giving it a voice or identity. Writing from "Inner Self" creates that separation naturally — you're no longer trapped inside the thought, you're in conversation with it.

### Expressive Writing Research

James Pennebaker's research on expressive writing (spanning from the 1980s to present) has consistently shown that writing about emotional experiences improves both psychological and physical health outcomes. The key mechanism appears to be **cognitive processing** — the act of translating chaotic internal experience into structured language.

The chat format encourages shorter, more frequent entries compared to traditional journaling, which can lower the barrier to consistent practice.

### The Chat Format Itself

There's a reason people process emotions through texting. Chat interfaces feel conversational and low-pressure compared to a blank page. The bubble format creates natural turn-taking, which can help you move from venting to reflection without the structure feeling imposed.

---

## Risks and Honest Limitations

This tool can help, but it can also hurt if misused. 

### Psychological Risks

- **Rumination vs. processing.** There is a well-documented distinction in psychology between productive emotional processing and unproductive rumination (repetitively going over the same distressing thoughts without resolution). This tool can enable either. If you find yourself using the "Inner Self" voice to reinforce self-criticism or spiral into the same painful loop repeatedly, you're ruminating, not processing. The "Inner Self" works best when it's **compassionate rather than critical**.

- **Not a substitute for professional support.** Two-voice journaling can complement therapy, but it cannot replace it. If you're dealing with trauma, severe anxiety, depression, or suicidal thoughts, please reach out to a mental health professional. A journal cannot ask you the question you're avoiding.

- **False sense of resolution.** Writing something down can create a feeling of having "dealt with it" when the underlying issue remains unaddressed. Be honest with yourself about whether you're processing or performing.

- **Echo chamber of one.** Unlike therapy, there's no external perspective here. Both voices are yours. This means your blind spots remain blind spots. Use this alongside other forms of support — friends, professionals, community — not instead of them.

### Security Limitations

- **Password strength is on you.** The app doesn't enforce a minimum password length. A weak password makes the encryption meaningless. Use a strong one.

- **Browser storage isn't bulletproof.** IndexedDB data can be cleared by the browser (storage pressure, clearing site data, OS cleanup). The encrypted backup feature exists for this reason — **use it regularly**.

- **Local-only means no sync.** Your journal lives on the device where you created it. If you lose the device without a backup, the data is gone.

- **Not audited.** The encryption implementation uses the Web Crypto API (which is solid), but this codebase has not been professionally audited. Don't use it for anything where a security breach would be catastrophic.

---

## Privacy Model

The privacy design is intentionally aggressive:

| Layer | Implementation |
|---|---|
| Encryption | AES-256-GCM via Web Crypto API |
| Key derivation | PBKDF2 with SHA-256, 100K iterations, random 256-bit salt |
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
