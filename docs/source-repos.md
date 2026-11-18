# Source repos

Checked 2026-11-17.

## 1. chrislgarry/Apollo-11 — the original code, not an emulator

https://github.com/chrislgarry/Apollo-11

- Transcribed original Apollo 11 AGC source code, public domain, digitized from MIT Museum scans by the Virtual AGC project and the MIT Museum.
- Contains only two programs:
  - **Comanche055** — Command Module, Colossus 2A, Apr 1, 1969.
  - **Luminary099** — Lunar Module, Luminary 1A, Jul 14, 1969.
- You *read* this one. Its README points to Virtual AGC to compile it.
- Role in this project: the artifact / textbook — "how the code works."

## 2. virtualagc/virtualagc — the emulator + everything else

https://github.com/virtualagc/virtualagc

- The Virtual AGC project: source transcriptions for many missions (not just Apollo 11), plus the tools to run them.
  - **yaAGC** — CPU emulator. Given the same software and the same inputs as a real AGC, it responds the same way.
  - **yaYUL** — assembler; turns source into executable rope memory.
  - **yaDSKY / yaDSKY2** — simulated Display/Keyboard units.
  - Simulated peripherals, the LM Abort Guidance System (AGS), and other material (LVDC, Gemini OBC — minimal).
- Also provides a Docker deployment (noVNC in a browser) as an easier run path.
- Specs as stated in its README: 2,048 words of RAM (~3,840 bytes), 36,864 words of ROM (~69,120 bytes), maximum about 85,000 instructions per second, 70.1 lbs, 28V DC.
- Role in this project: "how you make it fly again on a modern computer" — and the feasibility question in roadmap.md is whether this emulator, or a smaller faithful simulator, belongs inside the eventual app.
