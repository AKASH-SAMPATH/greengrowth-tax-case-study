# GreenGrowth Tax — Case Study Prototype
** Akash Sampath · akashsampath16@gmail.com**

One working product covering **all ten challenges**, rather than ten disconnected demos — because the case study's hardest tensions (traceability, trust, status, roles, scale) only show up when the pieces have to coexist on the same screens. It's a preparer's workspace and a client's portal for a single return, sharing one codebase, one status model, and one visual language.

## Run it
Open `index.html` in any browser. Single file, vanilla JS, no build step, no dependencies, no backend. Hosted via Netlify Drop / Vercel.

## Where each challenge lives
**01 Traceability — the spine of the product.** Click any number: the source document appears with the extracted box highlighted, plus the full chain from source through transformation to return field. Every value is a claim with evidence attached; a CPA is never asked to take the software's word for anything.

**10 Trustworthy AI — proven, not described.** The trust model has teeth: switch to the client role, upload the clean 1099-DIV (simulated), switch back — line 3b now shows a **re-extraction diff** ($1,893.40 @71% → $1,898.40 @99%, with a plain-English reason: the fold had hidden the final digits). The value never changes silently; a human accepts or declines, and either decision lands in the field's audit trail. Confidence scores appear only when they change what you should do, explained in scan-quality terms, never model internals.

**08 Affordances.** Five states, five consistent treatments everywhere: amber dot = AI/unverified · green check = human-verified (locked against silent updates) · gray lock = calculated (uneditable but never opaque — it still shows its math) · red dot = blocked · purple ⇄ = new extraction awaiting a decision. The same chips appear on fields, documents, queue rows, and requests, so the vocabulary is learned once.

**05 Roles + 02 Collaboration.** A role switcher (labeled as a prototype affordance, per the brief) flips between preparer and client. Internal notes aren't hidden by CSS — the client role's render path never receives them, and the client view carries a prototype annotation saying exactly that. Threads can only exist attached to a field, document, or request; there is no inbox for context to die in. Internal vs. client-visible is chosen per message via a structural toggle, not a checkbox you forget.

**03 First-run.** The client's home screen *is* the onboarding: a welcome line stating how many things need them, the shared pipeline, an owner strip saying whose move it is, and a numbered task list starting with "Do it now →". Next action understood in well under ten seconds; nothing forces a tour.

**06 Status.** One six-step pipeline both roles read identically — same steps, same labels (that's the point of a shared mental model). What differs by audience is the *detail around it*: the preparer sees verification counts and reviewer names; the client sees "your move: 2 quick uploads."

**07 Dashboard.** "Work on this now" is a ranked queue where every row shows its rank *and its reason*. The formula — days-to-deadline ÷ (open blockers + unverified fields) — is printed on the screen, because an explainable ranking beats a clever opaque one for exactly the same reason the trace panel exists.

**09 Scale.** The "All items" tab holds 384 deterministically generated items (documents, questions, calculations, warnings, messages — seeded PRNG, so every reviewer sees the same data). Groups open on demand, long lists reveal in slices, live search flattens the hierarchy with match highlighting, and clearing it restores your place. The complexity is real; the default view is five lines.

**04 Navigation.** Three mechanisms: breadcrumbs everywhere; a **⌘K command palette** indexing fields, documents, threads, and views; and **URL hash deep-linking** (`#/preparer/return/review/3b` opens the app with that field traced), which makes browser back/forward restore your workflow for free. Cross-object jumps preserve context — a thread links to its field, a document to the lines it feeds.

Keyboard: ↑/↓ move between fields, V verifies, Esc closes, ⌘K jumps anywhere.

## What's real vs. simulated
**Real:** all interaction and state — verify/correct/reopen with attribution, the accept/decline re-extraction flow, per-field audit history, role-filtered message rendering, both upload simulations mutating shared state across roles, live search/filter over 384 items, hash routing with back/forward, the command palette, keyboard flows.
**Simulated:** documents are hand-built HTML mockups, not parsed files; confidence scores, traceability links, and the re-extraction result are fabricated; the item dataset is generated; there is no backend, auth, or model — per the brief's "quick and dirty behind the frontend" instruction. Only the Chen return is fully wired; other queue rows say so when clicked rather than dead-ending.

## Type & palette, briefly
Public Sans (the U.S. Web Design System face — the native vernacular of government forms) for UI; Spline Sans Mono with tabular figures for every number, because on a tax platform figures are data and data should align. Ledger-green/ink palette; amber is reserved exclusively for "AI touched this and a human hasn't yet," and purple exclusively for "the AI wants to change something a human already saw."
