# Notes for AI coding assistants

You're helping a three-person team build **Loop** at DurHack 2026 (12:00 Saturday 14 November to 12:00 Sunday 15 November, UK time). Two of the three are beginner programmers, so write code they can read.

## Read first

1. [docs/brain/README.md](docs/brain/README.md): what Loop is, the challenges, the timeline.
2. [docs/brain/plan.md](docs/brain/plan.md): roles, file ownership, the Firestore data model, robot commands.
3. [docs/architecture.md](docs/architecture.md): the draft architecture and the robot radio protocol.
4. [docs/brain/decisions.md](docs/brain/decisions.md): what's decided and what's still open. Don't build on an open decision without saying so.

## Stack

- Plain HTML and JavaScript ES modules, loaded with `<script type="module">`. No frameworks, no bundler, no build step, no backend server.
- Firebase JavaScript SDK v12 from the gstatic CDN: anonymous Authentication, Firestore, Hosting. Web pages live under `public/`.
- Robot and relay: BBC micro:bit V2 on a 4tronix Bit:Bot XL, programmed in MakeCode (blocks or MakeCode JavaScript) with the BitBot extension. Radio group 7.
- The dispatch page talks to the relay micro:bit with the Web Serial API at 115200 baud. It only works in Chrome or Edge, on `localhost` or `https`.

## Team rules

- Each person edits only their own files (see the ownership table in [plan.md](docs/brain/plan.md)). If a change needs someone else's file, say so instead of editing it.
- Don't rename Firestore collections or fields without the team agreeing. The data model is in [plan.md](docs/brain/plan.md).
- Anything that changes a balance (`balance`, `held`) must run inside a Firestore transaction.
- Never store real names. Users are a SHA-256 hash of the anonymous uid plus a random alias.
- All UI text in English.
- Only Member C runs `firebase deploy`.
- Keep comments short and beginner-friendly. Say which file the code goes in and how to test it.
- Radio messages must be 19 characters or fewer (micro:bit limit).

## Event rules

- All project code must be written after 12:00 on Saturday 14 November 2026.
- The README must say what was pre-existing (Bit:Bot chassis, micro:bit, open-source libraries).
- The Firebase web config is not a secret and can be committed. Service account keys and anything in `.env` must never be committed.
