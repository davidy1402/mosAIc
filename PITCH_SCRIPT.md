# ClearBox — 4-Minute Pitch Script (6 July, MBTMY L4 Summit)

**Format:** 4 min pitch + 4 min Q&A. Max 2 presenters on stage.
**Roles:** Speaker A = storyteller (problem, business). Speaker B = demo driver (laptop, narration during demo).
**Target runtime: 3:40** — leaves 20s buffer for walking up and screen setup.

Rubric this script is built against: Innovation 20% · AI Utilization 20% · Impact 20% · UX 15% · Technical 15% · Presentation 10%.

---

## Before you're called

- Demo open at `index.html` (Mercedes me overlay showing), reset state.
- Backup video on the laptop desktop AND a phone.
- Speaker B controls the laptop the entire time. Speaker A never touches it.

---

## 0:00 – 0:35 · The problem (Speaker A)

> Every year Malaysia records over half a million road accidents.
> When one happens, three things go wrong at once.
> The evidence is weak — flat dashcam clips with blind spots that anyone can delete or dispute — so claims drag on for months and insurance fraud thrives.
> The rescue is blind — when eCall dispatches an ambulance today, responders know *where* the car is, but nothing about *who* is inside: are they conscious, are they asthmatic, is their heart failing?
> And the road forgets — the same corner keeps collecting the same crashes, and no one warns the next driver.

*(Numbers note: verify the current MIROS/data.gov.my figure the night before and say the real number. If unsure, say "over half a million reported accidents a year" — do not invent precision.)*

## 0:35 – 1:00 · The idea (Speaker A)

> Mercedes already solved the *call* — Emergency Call comes free for three years with every new car, and it works.
> ClearBox is the next tier of that same service. Using only hardware already in the car — the cabin camera, the microphone, the crash sensors, the exterior cameras and Car2X — we turn every Mercedes into three things:
> **a witness that sees** — a tamper-proof 3D reconstruction of the crash,
> **a medic that knows** — live occupant vitals sent to 999,
> **and a memory that warns** — a collective map of dangerous roads.
> Zero new hardware. One software update. Let me show you.

## 1:00 – 2:30 · Live demo (Speaker B drives and narrates; Speaker A steps back)

**[CLICK: "Start Drive" on the Mercedes me overlay]**
> It starts in the Mercedes me account the customer already has — their car, their eCall subscription, and an opt-in medical profile: our driver has acute asthma. That profile is encrypted and only ever released to 999 on an SOS.

**[Road Memory tab is now live — let the car drive 5 seconds]**
> While driving, the collective road memory is quietly watching. These heat zones are built from what other Mercedes actually experienced. As we approach one, the car warns us — before anything happens.

**[CLICK: "Simulate Crash Event" in the header]**
> Impact.
> *(pause — let the sequence run, speak over it)*
> Step one: the exterior cameras and Car2X data from surrounding vehicles reconstruct the crash as a 3D scene — you'll see it in a moment.
> Step two: the cabin camera reads each occupant contactlessly — heart rate, breathing, consciousness. Our asthmatic driver is flagged critical priority, and that diagnosis — not just a location — is dispatched to 999, so the ambulance arrives with the right equipment.
> Step three: the incident joins the road memory, warning every Mercedes behind us.
> And across the top — the trust chain: evidence signed by the vehicle's hardware identity, locked behind driver-plus-police consent, and a Mercedes Insurance claim drafted with zero paperwork.

**[CLICK: Crash Reconstruction tab — drag the 3D splat scene, rotate it once]**
> This is the witness. A Gaussian-splat reconstruction you can rotate — no blind spots, no he-said-she-said, cryptographically signed at the moment of impact.

**[CLICK: "Evidence Packet" — show the PDF for 2 seconds, close]**
> And this is what the insurer and the police receive.

## 2:30 – 3:10 · Technical honesty (Speaker A)

> Everything you just saw runs on sensors that are in Mercedes showrooms today. The vitals come from remote photoplethysmography on the existing cabin camera — reading pulse from skin colour micro-changes — plus vocal stress from the microphone. Published rPPG studies reach clinical-grade heart-rate accuracy in-cabin; we're not inventing the sensing, we're fusing it.
> On our roadmap, accuracy grows with the ecosystem: opt-in wearables paired through Mercedes me, and smart-fabric seats as they reach production. The MVP needs none of them.

## 3:10 – 3:40 · Business & close (Speaker A)

> The business model already exists: eCall is free for three years, then becomes a subscription. ClearBox is its premium tier — and it pays for itself twice: subscription revenue for Mercedes, and claims that settle in days instead of months for insurers, with fraud checked against signed sensor data.
> Mercedes invented the crumple zone to protect people *during* a crash.
> ClearBox protects them *after* it — their life, their truth, and every driver who passes that road next.
> We're mosAIc. Thank you.

---

## Q&A strategy (4 minutes)

Split ownership BEFORE the day — never two people answering one question:
- **Speaker A:** business, privacy/legal, Mercedes fit
- **Speaker B:** sensors, AI, architecture

The script deliberately baits three questions you want. Prepared answers:

**"How real is the camera vitals claim?"** (baited by "published rPPG studies")
> rPPG is peer-reviewed and already used in automotive research; in-cabin heart-rate error of a few BPM is published. Motion and lighting are the hard parts — that's exactly why we fuse it with the microphone and, on the roadmap, wearables. And for triage we don't need clinical precision — we need "conscious or not, breathing or not, deteriorating or not."

**"How does the 3D reconstruction actually work?"** (baited by "Gaussian splat")
> Multi-angle footage from the car's own cameras, plus Car2X frames from nearby Mercedes, are fused into a Gaussian-splatting scene — the same technique used for photorealistic 3D capture today. What you saw is a simulated PoC of that pipeline; the reconstruction runs in the cloud after upload, only the capture happens in the car.

**"What about privacy?"** (baited by "driver-plus-police consent")
> Three protections: health monitoring is opt-in through Mercedes me; all evidence is encrypted on-vehicle and needs BOTH driver and police keys to unlock — Mercedes itself cannot view it; and the road memory shares only anonymized coordinates, never identities. This maps to PDPA requirements in Malaysia.

Answers you must have cold (don't bait, just be ready):

- **"Which sensors exist in today's cars?"** → Cabin camera (ATTENTION ASSIST already watches the driver's eyes), microphone, crash/airbag sensors, exterior cameras, Car2X. NOT in cars today: steering-wheel electrodes, seat vitals sensors — they're on our roadmap slide, not our MVP.
- **"False positives — will it call 999 for a pothole?"** → Same escalation as today's eCall: impact triggers a voice check first; dispatch only when the occupant doesn't respond or vitals confirm distress. The AI adds information to that flow, it doesn't remove the human check.
- **"Why would Mercedes build this rather than a startup?"** → Because the moat IS Mercedes: the sensors, the eCall infrastructure, the Car2X fleet density, the insurance arm, and the customer's existing subscription relationship. A startup has none of those.
- **"What did you actually build?"** → A working MBUX-style cockpit: live driving simulation with collective road-memory heatmap, contactless vitals monitoring with per-occupant triage, the SOS escalation flow, a rotatable 3D crash scene, and an auto-generated signed evidence packet — all running locally, no internet needed. *(Confident, specific, no apologies.)*

## Rehearsal checklist

- [ ] Run it twice, timed. Cut lines, not speed — if over 3:50, drop the road-memory narration line first.
- [ ] Speaker B rehearses the click sequence until it needs no thought: Start Drive → wait 5s → Simulate Crash → wait for sequence → Reconstruction tab → rotate 3D → Evidence Packet.
- [ ] Record the backup video from THIS build (it runs offline — record it exactly as you'd present it, with cursor movements).
- [ ] Test on the venue projector resolution if possible; otherwise test at 1920×1080 external display.
- [ ] Decide who says the first Q&A sentence if judges go silent: Speaker A invites — "Happy to go deeper on the reconstruction or the business case."
