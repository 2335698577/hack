# Loop: the plan on one page

A summary of the [3-person handbook](../sources/loop-handbook-3-people.md). The handbook has every step in detail; this page is for finding your place quickly. H-times count from 12:00 Saturday.

## What happens at a table (about 15 minutes per exchange)

1. **Scan** the QR code on your table. You get an anonymous alias (for example "Purple Otter") and 3 time credits.
2. **Ask:** tick the skills you need and can offer, describe the problem in one sentence (no names), set a price of 1 to 3 credits. You get a two-character code, for example A7, to write on a sticky note.
3. **Match:** someone with the right skills sees your request, sorted by best match, and taps Accept. Your credits go into escrow.
4. **Robot:** it drives to your table, you drop the note in the rooftop mailbox, it drives to the helper's table, they take the note.
5. **Help:** the helper writes back on the note, or both tap Reveal to see each other's table and help in person.
6. **Done:** escrowed credits go to the helper. The big screen gets a new line in the help network.

## Who owns what

| Member | Owns | Files |
|---|---|---|
| A (robot and design) | Robot, relay micro:bit, dispatch page, styles, big screen, venue set-up, pitch story | `dispatch.html`, `js/dispatch.js`, `screen.html`, `css/style.css`, MakeCode `loop-car` and `loop-relay` |
| B (rules and data) | Ledger rules, matching, statistics, economic model | `js/match.js`, `js/skills.js`, `js/stats.js` |
| C (code lead) | Firebase, ledger code, anonymous login, phone app, repo, deployment, security, code help | `index.html`, `js/firebase.js`, `js/ledger.js`, `js/phone.js` |

Everyone edits only their own files. C merges, reviews and is the only one who runs `firebase deploy`. All files live under `public/` in the Firebase Hosting project.

## Data model (Firestore)

Agree in hour 1, then don't rename fields without telling everyone.

```js
// users/{hashedId}  (only a pseudonym, never a real name)
{ alias: "Purple Otter", table: 3, balance: 3, held: 0, rating: 4.8, skills: ["UI design", "Python"] }

// requests/{id}
{ from: "hashedId", need: ["React"], offer: ["UI design"], price: 1,
  status: "open",          // open / matched / delivering / done
  helper: null, cycleId: null, code: "A7",
  revealByAsker: false, revealByHelper: false }

// transactions/{id}
{ from: "hashedId", to: "hashedId", amount: 1, status: "held" }   // held / released / refunded

// tasks/{id}  (a delivery job for a robot)
{ stops: [3, 5], requestId: "...", status: "queued", createdAt: ... }   // queued / running / done
```

Anything that changes a balance runs inside a Firestore transaction. The [architecture draft](../architecture.md) proposes a few extra fields on `tasks` and two new collections for the robot fleet.

## Robot commands (handbook version)

The dispatch page sends text over USB to the relay micro:bit, which forwards it by radio (group 7) to the robot.

| Command | Meaning |
|---|---|
| `GO:3` | Go to station 3 |
| `AT:3` | Robot reports: arrived at station 3 |
| `HOME` | Return to the start (station 0) |

## Timeline in clock times

| Clock | H | Phase | Goal |
|---|---|---|---|
| Sat 12:00 to 13:00 | H0 to H1 | Opening set-up | Tape the track, recruit 4 to 6 tables, C launches an empty site |
| Sat 13:00 to 17:00 | H1 to H5 | Foundations, in parallel | A: robot goes to any station on command. B: matching code on test data. C: login and a correct ledger |
| Sat 17:00 | H5 | Integration check | All three show their part working (10 minutes) |
| Sat 17:00 to 20:00 | H5 to H8 | Connect everything | One full exchange on two phones |
| **Sat 20:00** | **H8** | **Make-or-break test** | Ask, accept, robot drives two stops, Done, balances 2 and 4. Twice in a row |
| Sat 20:00 to Sun 02:30 | H8 to H14:30 | Live, sleep in shifts | Real users, robot running, log every problem. Two people always awake |
| Sun 00:00 to 07:00 | H12 to H19 | Upgrades | Big screen, exchange cycles, reveal, reputation, and either the item-trading prototype and economic simulation or the Neptune North fleet layer (see [decisions.md](decisions.md)) |
| Sun 07:00 to 09:00 | H19 to H21 | Freeze | Bug fixes only, collect the data, rehearse 3 times, record the backup video |
| Sun 09:00 to 11:00 | H21 to H23 | Devpost | Write it up, submit early |
| Sun 11:00 to 12:00 | H23 to H24 | Before the demo | Test run, phones on, backup video open |

Sync rule: every 2 hours, 5 minutes together to check progress.

Shift rota from the handbook: A sleeps 20:30 to 22:30, B sleeps 22:30 to 00:30, C sleeps 00:30 to 02:30.

## Cut order when time runs short

From the handbook, cut from the top: item-trading prototype → economic simulation → reveal tables → reputation and reporting → exchange cycles. **Never cut** the big screen or the real-data statistics.

If we commit to Neptune North, the architecture draft suggests the fleet layer takes the slot of the item-trading prototype and economic simulation.

## Pitch (under 3 minutes)

Opening story (A, 20 s) → live demo with a judge (A, 50 s) → real data from the day (B, 30 s) → rules and model (B, 40 s) → vision (A, 30 s) → close (A, 10 s). Full script and likely judge questions are in section 7 of the handbook.

## Risks we already have fallbacks for

Floor tape not allowed (use a big sheet of cardboard on a table), unreliable line-following (manual buttons on the dispatch page), venue Wi-Fi blocking phones (mobile data and a phone hotspot), demo failure (backup video). Full table in section 8 of the handbook.
