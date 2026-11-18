# Design principles

Decided in conversation on 2026-11-17. These are the filter any future game shape is judged against.

## 1. Kernel: assembly-puzzle games

Shenzhen I/O and TIS-100 (Zachtronics) are the reference kernel:

```
give the player a tiny machine + a manual
→ a small job in assembly
→ run it, watch registers / outputs
→ pass the test, then do it in fewer lines / cycles
```

David's take on them: pretty cool, but a little boring and not flashy. The loop is right; the feel is too dry.

## 2. No abstract number-shuffling

Confirmed distinction ("Correct" — David, 2026-11-17):

Keep the assembly-puzzle core, but do **not** leave it as abstract puzzles — numbers moved around to make other numbers match, as in TIS-100.

Every AGC puzzle should be attached to a real mission effect you can see: a DSKY display changing, the spacecraft changing course, a warning light, an alarm, an engine firing.

## 3. Show the abstractness becoming real

At the same time, do **not** hide the abstract layer behind a mission wrapper. David wants to understand the abstractness itself and its connection to real life.

The chain to make visible, end to end:

```
0s and 1s woven in core rope
  → an instruction runs
    → a number changes in a register
      → that number means altitude / velocity / time
        → the DSKY displays it, or an engine fires, or the ship turns
```

That hardware–software synthesis — software on one end, the physical world on the other, with every step traceable between them — is the core fascination of the project.

## 4. Learning first, for David first

- Primary audience at this stage: David himself, learning.
- Two learning stances, possibly combined:
  - **Under-the-hood / functional** — how the computer itself works.
  - **Astronaut's-eye** — using the AGC the way the crew used it (DSKY, verbs/nouns, programs).
- Wider audience is a possible bonus, not the driver.
- This is a non-money idea.

## 5. Exploration before building

Exploration and decision are separate steps. Learn the machine and test shapes on paper before committing to a build plan, a level design, or a project structure.
