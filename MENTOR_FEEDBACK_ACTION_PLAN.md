# ClearBox — Mentor Feedback Action Plan (Pitch: 6 July, 4 min + 4 min Q&A)

This maps every point from the Mercedes mentoring session to a concrete fix,
prioritized for the 3 days left before pitch day.

---

## 1. Anchor ClearBox in the existing Mercedes ecosystem (mentor point: "Mercedes me app… existing product from Mercedes ecosystem that we can elevate")

The mentors' strongest hint: don't pitch a standalone product — pitch an
**upgrade to what Mercedes already sells**. The products to name-drop and build on:

| Existing Mercedes product | What it does today | How ClearBox elevates it |
|---|---|---|
| **Mercedes-Benz Emergency Call (eCall)** | Impact detected → call driver → if no answer, send location + SOS to rescue team. Subscription-based, free 3 years with a new car. | Adds *what's happening inside the car*: live occupant vitals, consciousness state, pre-saved medical history → dispatched to 999 so responders prep the right equipment. |
| **Mercedes me app / profile** | Login, driver profile, vehicle model, connected services | ClearBox medical profile (asthma, heart condition, blood type) lives in the Mercedes me profile the driver already has. Incident reports and 3D reconstructions appear in the app. |
| **MBUX + interior camera** | Attention/drowsiness monitoring — camera already looks at the driver's eyes | Same camera, new software: contactless rPPG pulse + consciousness detection. **Zero new hardware.** |
| **Car2X communication** | Cars share hazard data (e.g. Intelligent Damper Control uses data from vehicles ahead — it's on page 6 of the Vibathon guide!) | Collective Road Memory is literally Car2X extended to accident heatmaps. Quote the S-Class 2026/27 example back to them. |
| **Accident Recovery / insurance services** | Manual claims after a crash | Auto-generated, cryptographically signed incident report → zero-paperwork claim. |

**Pitch line to use:** *"Everything ClearBox needs is already in the car and
already in Mercedes me. We're not adding hardware — we're adding intelligence
to the eCall your customers already pay for after year 3."*

This also nails the **Digital Extras & Upsell** challenge track: ClearBox is a
natural premium tier of the existing eCall subscription (same "free 3 years,
then subscribe" model the mentors described).

---

## 2. Fix the feasibility story (mentor point: "seat and steering wheel don't have any sensors… but we do have a camera looking at your eyes")

This is a factual correction from Mercedes staff — **current Mercedes cars do
NOT have steering-wheel heart-rate electrodes or seat pressure vitals sensors.**
Our registration form and the vital-signs demo both claim them. If a judge asks
"which S-Class has a heart-rate steering wheel?" and we can't answer, we lose
the Technical Feasibility points (15%).

**Restructure the sensing story into two honest tiers:**

- **Tier 1 — Available today (software only, our MVP):**
  - Cabin camera → rPPG contactless pulse, blink/eye state, consciousness detection
  - Microphone → vocal stress / responsiveness check
  - Existing crash sensors → impact trigger (same trigger eCall uses today)
  - Multi-angle exterior cameras → 3D crash reconstruction
- **Tier 2 — Roadmap (partnership / future hardware):**
  - Wearables via Mercedes me pairing (Apple Watch / WHOOP health data opt-in) —
    the mentors explicitly suggested wearables, Google Glass, and smart fabric
    (China market). Show one slide: "Vitals accuracy improves as the ecosystem
    grows — camera today, wearables tomorrow, smart-fabric seats later."
  - Steering wheel electrodes / seat sensors as OEM hardware roadmap items

**Demo change (vital-signs.html):** add a "Sensor Sources" toggle or badge that
distinguishes `ONBOARD (today)` vs `ROADMAP` sources, and make the default demo
run entirely on camera+mic+crash-sensor inputs. Keep steering wheel/seat as
greyed-out "future fusion" nodes. This turns the mentors' criticism into a
credibility feature.

---

## 3. Add research & business facts (mentor point: "some fact, research, doing business pitch… what you have, what you don't have")

Add exactly one data slide + one business slide. Verify numbers before pitch:

- **Problem facts (Malaysia):** MIROS / data.gov.my road accident statistics —
  accidents per year, fatalities, and the "golden hour" survival statistic
  (survival chance drops sharply when treatment is delayed past 60 minutes).
  The Vibathon guide (p.20) itself points to data.gov.my accident datasets — use
  them and say so.
- **Insurance fraud:** cite a Malaysian/ASEAN motor insurance fraud figure
  (general insurance industry estimates ~10% of claims involve fraud — verify
  with PIAM/ISM source).
- **Business model ("what you have / what you don't have"):**
  - Have: cameras, mics, crash sensors, Car2X, MBUX, Mercedes me accounts,
    eCall infrastructure, an existing subscription billing relationship.
  - Don't have (and don't need for MVP): wearables, new sensors, new hardware.
  - Revenue: ClearBox as eCall premium tier (subscription upsell), insurance
    partnership revenue (fraud reduction shares), data-driven road-safety
    services to authorities (anonymized heatmap licensing).

---

## 4. One connected demo storyline instead of three separate demos

Mentors asked about the Mercedes me app and login/profile. Tie the three demo
pages into one narrative flow so the demo tells the eCall-elevation story:

1. **Profile** (new, small): mock Mercedes me login → driver profile shows car
   model + opt-in medical profile (asthma). ~1 screen, reuse existing styling.
2. **Drive**: road-memory.html — approaching a flagged high-risk zone, quiet warning.
3. **Impact**: vital-signs.html — impact trigger → escalation timeline that
   mirrors the real eCall flow (impact → attempt driver contact → no response →
   dispatch), but enriched with per-occupant vitals and medical history sent to 999.
4. **Aftermath**: crash-reconstruction.html — 3D scene, signed record,
   auto-submitted insurance report.

Add "next step" navigation between the pages in that order so one presenter can
click through the whole story without touching the URL bar.

---

## 5. De-risk the live demo (mentor point: "if confident, do not have a video backup" → i.e. HAVE one unless fully confident)

- **Remove hard CDN dependencies.** All four pages load Google Fonts,
  Font Awesome, jsPDF, and Leaflet/leaflet.heat + OSM tiles from the internet.
  If venue Wi-Fi fails, the demo visually degrades and the heatmap page breaks
  entirely. Vendor these files locally (fonts, FA css/woff2, leaflet js/css,
  jsPDF) and pre-cache map tiles for the demo area or ship a static map image
  fallback.
- **Record a backup video** of the full 4-step storyline (screen recording with
  the exact narration timing). Have it on a USB stick AND a phone.
- **Test on the actual laptop + projector resolution** (pages are designed for
  a fixed hyperscreen viewport; check 1080p projector scaling).

---

## 6. Pitch structure — 4 minutes, max 2 presenters, guide the Q&A

Format from the guide: Problem & Solution → Demonstration → Technical Overview
→ Impact & Future, then 4-min Q&A. Rubric: Innovation 20 / AI Utilization 20 /
Impact 20 / UX 15 / Technical 15 / Presentation 10.

Suggested 4:00 split (2 presenters):

| Time | Speaker | Content | Rubric hit |
|---|---|---|---|
| 0:00–0:40 | A | Problem with facts (accidents, golden hour, fraud) + "today's eCall dispatches blindly" | Impact |
| 0:40–1:10 | A | ClearBox in one sentence: *"We turn the eCall you already have into a witness that sees, a medic that knows, and a memory that warns."* | Innovation |
| 1:10–2:40 | B | Live demo storyline (profile → warning → impact → vitals dispatch → 3D reconstruction → auto claim) | UX, Demo, AI |
| 2:40–3:20 | A | Technical: existing hardware only (camera rPPG, Car2X, Gaussian Splatting, signed ledger); Tier-2 roadmap (wearables/smart fabric) | Technical, AI |
| 3:20–4:00 | B | Business: eCall premium tier, insurance partnership, road-safety data; close on Mercedes safety legacy | Impact |

**Guide the judges' questions** — deliberately leave hooks:
- Mention "multi-signature evidence ledger" briefly → invites a privacy/security
  question you have a strong answer for (driver + police keys, GDPR-style consent,
  anonymized heatmap).
- Mention "Gaussian Splatting from multi-angle cameras" briefly → invites a
  "how does the 3D reconstruction actually work" question — prepare a 30-second
  answer with one visual ready in the demo.
- Prepare answers for the questions you DON'T want cold: "Which sensors exist
  today?" (answered by Tier 1/Tier 2 slide), "Why would Mercedes build this?"
  (eCall upsell), "What about false positives?" (escalation mirrors eCall's
  call-driver-first flow — a human check before dispatch).

---

## Priority order for the next 3 days

1. **Today:** Fix feasibility claims in vital-signs demo (Tier 1/Tier 2 sensors);
   write the pitch script with the eCall-elevation framing.
2. **Tomorrow:** Chain the 4 demo pages into one storyline + add the Mercedes me
   profile screen; vendor CDN assets locally; add the facts/business slides.
3. **Day before pitch:** Full timed rehearsals (target 3:40, twice); record the
   backup video; test offline; assign the two presenters and Q&A owners for each
   topic (tech / business / privacy / medical).
