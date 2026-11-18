# Roadmap

Stages in order. Only Stage 1 is done; the rest are proposed, not committed.

## Stage 1 — Spec (done 2026-11-17)

- Dedicated public repo created by David: https://github.com/DavidEdelstein/apollo-agc-lab
- This spec pushed by Muse: README + principles, learning map, source repos, and this roadmap.

## Stage 2 — Learn together

Walk the machine before designing anything:

- Run one real verb/noun on a simulated DSKY (VirtualAGC) and trace what happens inside.
- Trace one small real assembly routine end to end: bits → instruction → register → meaning → physical effect.

## Stage 3 — Feasibility

Open question: can VirtualAGC / yaAGC realistically run inside a web app we would build, or does the app need a simplified AGC simulator that is faithful to the real instruction set and DSKY behaviour, but smaller?

No answer is assumed in this spec.

## Stage 4 — Sketch game shapes

Only after Stages 2–3: sketch 2–3 concrete level / game shapes at postcard size, judged against principles.md, for David to react to.

## Not decided yet

- Learning order: DSKY-first vs under-the-hood-first.
- Any level design, puzzle list, or scoring system.
- Whether the app runs the real emulator or a simplified faithful simulator.
- Any project / board structure. Nothing here is a build commitment yet.
