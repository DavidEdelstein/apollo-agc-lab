# Learning map

The terrain to learn, at a high level. This is the content of the overview first given in chat on 2026-11-17 — kept here so it lives in the repo, not only in conversation.

## The machine in one picture

```
  IMU + radar + optics
   (feels motion / sees stars)
            ↓
        ┌─────────┐
        │   AGC   │  the box — no screen, no keyboard
        │  CPU +  │
        │  memory │
        └────┬────┘
             ↕
        ┌─────────┐
        │  DSKY   │  the astronauts' face to it
        └─────────┘
     VERB + NOUN + PROGRAM
```

## 1. The box

- About 70 lbs, about 85,000 instructions per second.
- One of the first computers built from integrated circuits.
- Multitasking, with priority-based scheduling and automatic restarts (see §4).

## 2. Memory

- **RAM:** 2,048 words — about 3,840 bytes — erasable magnetic core memory.
- **ROM:** 36,864 words — about 69,120 bytes — of **core rope**: wires woven by hand through or around tiny magnetic cores to encode 1s and 0s.
- Once woven, the program could not change in flight. The code had to be right before launch.

## 3. The DSKY (Display/Keyboard)

- 19 keys, a few 7-segment displays (registers R1, R2, R3), and warning lights. No menus, no screen in the modern sense.
- The Command Module had two DSKYs; the Lunar Module had one.
- You talk to it in two numbers:
  - **VERB** = what to do — e.g. 16 = monitor, 37 = change program.
  - **NOUN** = what to do it to — e.g. 36 = time, 62 = velocity / altitude data.
- Example: `V16 N36 ENTR` = "show me the time, and keep updating it."
- **PROGRAMS** are the big jobs: e.g. P11 (launch monitoring), P63 (lunar landing).

## 4. The code

- Two layers:
  - Raw AGC assembly, for speed and direct hardware control.
  - An interpreted language on top, for the heavy guidance mathematics — effectively a virtual machine inside the tiny machine, trading speed for compact, higher-precision math.
- An **Executive** ran jobs by priority, plus a Waitlist for timed tasks.
- Restart protection is the famous payoff: during Apollo 11's landing, the **1201 / 1202 alarms** signalled Executive overload. By design, the computer shed low-priority work, restarted in seconds, and kept flying the important jobs. Not a crash — load-shedding working as designed (Margaret Hamilton's team).

## 5. Inputs that connect it to the real world

- **IMU** (Inertial Measurement Unit): gyroscopes and accelerometers — feels motion and rotation, so the AGC can integrate its way to position and orientation.
- Radar, optics, engine and thruster interfaces, and astronaut input via the DSKY.

This is where the abstract chain in [principles.md](principles.md) §3 lands: sensor numbers in, guidance numbers computed, physical action out.

## Proposed learning order (not yet decided)

1. Start at the DSKY, astronaut's-eye: run one real verb/noun and watch what happens.
2. Peel back one layer: what job did the Executive start, what registers changed, what did those numbers mean?
3. Then go under-the-hood: memory, core rope, and a small real assembly routine, traced end to end.

The alternative order — memory / core rope first, DSKY second — was also offered. David has not picked an order yet; he moved first to the game-format question (see principles.md).
