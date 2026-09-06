<p align="center"><img src="assets/cover.png" alt="Speak Grandma — complex things can be simple" width="720"></p>

# speak-grandma 👵

**Explain any technical system the way you'd tell your grandma** — one everyday
metaphor, behaviors instead of implementation, an ASCII diagram drawn *inside*
the metaphor, and a one-line moral at the end.

Not "dumbed down": **pre-assembled**. A good metaphor hands the reader a mental
model that already works — the daemon is *the secretary*, the classifier is
*the office manager*, the watchdog is *the guardian who revives everyone in 30
seconds*. Rules become character traits ("he'd rather ask too much than do too
much"). Numbers that govern behavior stay ("6 tokens", "expires after 30
days") — numbers aren't jargon, they're house rules.

## Install

```bash
npx skills add f-liva/speak-grandma@nonna
```

Then just ask: `/nonna how does git rebase work?` — or say *"explain it like
I'd tell my grandma"*.

> *nonna* is Italian for grandma. The skill answers in the language you ask in.

## What you get

- **One load-bearing metaphor** from everyday life (an office, a kitchen, a
  workshop) — tested against the system's weirdest behaviors before use, never
  mixed with a second world.
- **Human actors in bold** — every component becomes a person or object of
  that world, named once, then called the same name forever.
- **Behaviors, never implementation** — "if it comes back with the same
  problem, the bell rings at your house", not "if the fingerprint matches, the
  guard returns C".
- **Rules as consequences, with real anecdotes** when available.
- **An ASCII diagram in the same metaphor** — box-and-arrow summary of the
  story, not an architecture diagram in disguise. Phone-friendly.
- **A one-line moral in italics.** If it can't be written, the explanation
  isn't ripe yet.

## Sample output (git rebase, abridged)

> **On the family kitchen table there's the recipe notebook.** Guarding it is
> **the notary** (Git): he stamps every page, and computes each stamp from the
> page's content *and the stamp of the page before*. […]
>
> **The re-copying (the "rebase")**: the notary detaches your recipes and
> copies them at the end, after your aunt's pages. But your pages now come
> after *different* pages — the stamp must change. Same recipe, word for word:
> to the notary, they are **new pages**. The originals go into **a drawer**
> (about a month, then gone). The big danger: if you had already handed
> **photocopies to the cousins**, at the next family dinner there will be two
> versions of the same story — and a real fight.
>
> **Golden rule: only re-copy what no cousin has a photocopy of yet.**
>
> *Re-copying makes a nicer story to read — but re-copied pages are new
> pages: rewrite only what is still yours alone.*

## Why it works

A technical explanation makes the reader build the mental model themselves.
A good metaphor **delivers it pre-assembled**: every new rule snaps onto a
world the reader has known forever. Understanding arrives before the sentence
ends.

## License

MIT
