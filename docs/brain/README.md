# Team brain

Everything the team (and any AI assistant we use) needs to know about DurHack 2026 and Loop, in one place. Read this page first. Each file below is short.

Last updated: Saturday 14 November 2026, about 14:30.

## The 60-second version

- **What we're building:** Loop. You scan a QR code at your table, ask for help anonymously, and a small robot carries your paper note to someone who can help. Helpers earn time credits. Pitch line: *Ask without shame, help without cash.*
- **Challenges we're going for:** the DurHack main theme (**Composition**: art, music and tech) and the **Neptune North** challenge (several actors working together that keep going when communication drops). See [challenges.md](challenges.md).
- **Clock:** hacking started at 12:00 on Saturday 14 November and runs for 24 hours. The make-or-break test is at **20:00 Saturday**: ask, accept, robot drives two stops, credits arrive. See [plan.md](plan.md) for the full timeline in clock times.
- **Stack:** plain HTML and JavaScript, Firebase (anonymous login + Firestore + Hosting), no backend server. Robot is a 4tronix Bit:Bot XL with a BBC micro:bit, programmed in MakeCode. The dispatch laptop talks to the robot through a second micro:bit over Web Serial and radio.
- **The big open question:** how far we take the Neptune North angle. The draft architecture proposes letting the robots decide which jobs to take, so the system keeps working when the laptop or Wi-Fi drops. See [../architecture.md](../architecture.md) and [decisions.md](decisions.md).

## Files

| File | What's in it |
|---|---|
| [event.md](event.md) | DurHack logistics: times, rooms, food, workshops, hardware library, safety, judging |
| [challenges.md](challenges.md) | Every challenge announced at the opening ceremony, with criteria, prizes and how well Loop fits |
| [plan.md](plan.md) | One-page summary of our handbook: roles, files, data model, timeline in clock times, cut order |
| [decisions.md](decisions.md) | Decisions made and decisions still open, with who needs to make them |
| [../architecture.md](../architecture.md) | Draft system architecture, including the Neptune North fleet layer |
| [../progress.md](../progress.md) | Progress notes from team members |

## Source documents

These are the originals. The pages above summarise them; go to the source when something matters.

| Source | Notes |
|---|---|
| [Loop handbook, 3 people (Markdown)](../sources/loop-handbook-3-people.md) | Text version of `Loop_DurHack_2026_Plan_and_Handbook_EN_3people.docx`, so it's searchable and AI tools can read it |
| `Loop_DurHack_2026_Plan_and_Handbook_EN_3people.docx` (repo root) | The current handbook. Supersedes the 2-person version next to it |
| [opening-ceremony.txt](../sources/opening-ceremony.txt) | Text of the opening ceremony slides: schedule, sponsors, challenges, theme |
| [neptune-north-challenge.pdf](../sources/neptune-north-challenge.pdf) | Neptune North challenge slides |

## How to keep this useful

- When a decision gets made, add it to [decisions.md](decisions.md) with the time.
- When something changes the plan (hardware we couldn't get, a feature we cut), update [plan.md](plan.md) and note it in [../progress.md](../progress.md).
- Keep pages short. Link to the source instead of copying it.
