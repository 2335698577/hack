# Challenges at DurHack 2026

Everything announced at the opening ceremony, with how well Loop fits. Sources: [opening-ceremony.txt](../sources/opening-ceremony.txt) and [neptune-north-challenge.pdf](../sources/neptune-north-challenge.pdf).

## What we're going for

| Challenge | Status | Why |
|---|---|---|
| DurHack main theme: Composition | **Target** | Every project is judged on it. Loop needs a clear Composition angle in the pitch (see below) |
| Neptune North: Actors work better together | **Target** | Loop already has robots, phones and a database working together. To score well, the robots need to make their own decisions and keep going when communication drops. See [../architecture.md](../architecture.md) |
| "Connect things that usually aren't" (sponsor on the second floor of the TLC) | Worth ticking | Loop connects people at different tables who would never normally talk. Costs nothing extra |
| Everything else | Not targeting | See the fit notes below |

## DurHack main theme: Composition

> "We want to see creativity! Explore art, music and tech! We want to see idea mixing and trying new combinations!"

- **Judged on:** creativity and innovation; technical competence and execution; research and learning; polish and completion.
- **Prizes:** 1st overall, 2nd overall, Spirit of the Dino award.
- **How Loop fits:** Loop mixes a physical robot, a web app and a small economy, which is already a composition of unlikely parts. The draft architecture suggests one more step: each station plays a musical note when a robot arrives, so the day's deliveries play out as a tune and the big screen draws them like a score. "An orchestra with no conductor" ties the theme to the Neptune North story. This is a proposal, not decided.

## Neptune North: Actors work better together

Neptune North is a tech consultancy in Newcastle working on data, AI and software for finance and defence clients.

**The brief:** design an approach to a problem where several systems work together in a distributed way, even when communication is interrupted. When links fail, each actor has to keep operating without instructions from a central hub. Their examples: search-and-rescue drone swarms, warehouse robots that share picking jobs and avoid collisions without a central scheduler, teams of AI agents that split up a problem and merge results on reconnect, sensor networks that agree on what they see.

**Judged on:**

1. **Working towards a common goal:** multiple actors work together to solve a problem.
2. **Independent decision-making:** each actor makes its own decisions to support the group.
3. **Resilience when communications fail:** actors still make some progress when they can't communicate.
4. **Something you're excited about:** a problem that's interesting to you, solved in a way that's interesting to you.

**Prizes:** 1st place £1,000 in vouchers of your choice for the team; 2nd and 3rd place a mechanical keyboard. (The opening ceremony slide said "runner up: mechanical keyboards for the team". The PDF lists a 3rd place as well.)

**How Loop fits:** the handbook design is a straight line through a central hub (phone → Firebase → one dispatch laptop → one robot). That's exactly what this challenge asks us to avoid, so as written it would score low on criteria 2 and 3. The warehouse-robots example is close to what Loop does already. The draft architecture shows how to move the "which robot takes which job" decision into the robots themselves.

## Sponsor: "Improve the world by connecting things that usually aren't"

A sponsor offering software, cyber security, data and AI, managed services and advisory (their name is only in the slide logo). Prize: Raspberry Pi Pico and a Raspberry Pi Pico Inventor's Kit. They're on the **second floor of the TLC**. Worth a chat to confirm Loop counts.

## Other challenges (not targeting)

| Challenge | Brief | Fit with Loop |
|---|---|---|
| **RS:** build an intelligent system that can sense, analyse and respond to the real world | Capture data, analyse sensor inputs, make a decision, trigger an action. Mandatory hardware: **Arduino UNO Q, camera, USB hubs**, with optional sensors and nodes from the Product Loan Library. Prizes for 1st, 2nd and 3rd | Poor unless we switch hardware. Our robots run on micro:bits, not the UNO Q |
| **Accenture:** find a frustrating process people accept as "just the way things work" and redesign it with AI and LLMs | Judged on problem and user pain, innovation, effective use of AI and LLMs, impact and value, prototype and technical execution, responsible AI and feasibility | Partial. Being too embarrassed to ask for help is that kind of process, but Loop has no AI in it. An LLM that tags requests with skills and strips names would be the hook. Not planned |
| **SGX FX:** protect traders' assets in a market storm | Stay safe, early warning, predict what's next, spot opportunities. Historical pricing data provided | None |
| **Marshall Wace:** New Worlds | Open a door to the unexplored: new data, ideas or something novel. Looking for creativity, technical complexity, good presentation | Weak |
| **P&G** | 1: insights from complex receipt data. 2: product performance through novel sensor approaches in baby and feminine care | None |
| **QRT: Tagged** | Invent a physical language that encodes three words into an object, and a decoder that reads it back. No QR codes or plain text. Prizes per challenge: AirPods Pro, poker sets, £100 keyboard voucher | None |
| **QRT: Spray n' Tag CTF** | 15 Capture the Flag challenges on Hack The Box | Separate activity, not a project track |

Details for QRT challenges and mini-challenges are on their Discord channel.
