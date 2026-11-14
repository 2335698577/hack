# Decisions

Newest at the top within each section. When you decide something, move it from Open to Made and add the time.

## Open

| # | Question | Options | Recommendation | Who decides |
|---|---|---|---|---|
| 1 | Do we enter Neptune North, and how? | A: robots pick their own jobs over radio. B: one laptop per robot, each picks jobs in Firestore. C: keep the handbook design, skip Neptune North | **A**, built on top of the handbook so the 20:00 test isn't at risk. See [../architecture.md](../architecture.md#three-ways-to-build-it) | Whole team, today before 17:00 |
| 2 | Can we get a third micro:bit? | Hardware library (top floor TLC), another team, or skip the second robot | Ask the hardware library now. Two robots plus the gateway need three micro:bits; we planned for two | A |
| 3 | Who writes the robot "brain" (task book, claims, radio protocol)? | A in blocks, or C in MakeCode JavaScript | C writes it in MakeCode JavaScript; A keeps the line-following and stop-counting | A and C |
| 4 | What do idle robots do? | Keep doing slow laps, or park | Slow laps. On a single loop a parked robot blocks the other one. See [../architecture.md](../architecture.md#the-one-track-problem) | A |
| 5 | Composition angle for the pitch | "Orchestra with no conductor" (stations play notes, big screen draws a score), or another idea | Try the orchestra idea: it is one "play tone" block per arrival and links the theme to Neptune North | Whole team |
| 6 | Who taps Done? | Both confirm (Part 1 of the handbook), or only the asker (the phone flow) | Asker's Done releases credits; helper can Report; C cancels orders open over 2 hours (handbook recommendation) | Whole team, before B's ledger table and C's code diverge |
| 7 | Did the organisers allow floor tape and a robot among the tables? | Floor track, or the cardboard table-top fallback | Check the reply to the T-1 email | A |

## Made

| When | Decision | Why |
|---|---|---|
| Before the event | We're building **Loop**: anonymous help requests, delivered as paper notes by a robot, paid in time credits | Handbook Part 1 |
| Before the event | Build the skill-and-time exchange for real. Item trading is a prototype only | 24 hours is not enough for all three layers |
| Before the event | Stack: Firebase (anonymous auth, Firestore, Hosting) with plain HTML and JavaScript, no backend server. Robot: Bit:Bot XL + micro:bit in MakeCode | Simple enough for everyone to read and change |
| Before the event | Roles: A robot and design, B rules and data, C code lead. Everyone edits only their own files; only C deploys | Handbook section 4 |
| Before the event | Make-or-break test at H8 (20:00 Saturday) | Everything after that is a bonus |
| Sat 14 Nov | Target the main theme (Composition) and the Neptune North challenge | Team decision at the event |
