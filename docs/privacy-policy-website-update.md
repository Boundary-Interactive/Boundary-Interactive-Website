# Fly Exterminator — Privacy Policy Website Update Brief

**Audience:** Agent or editor updating the Boundary Interactive website  
**Target page:** https://boundaryinteractive.com/privacy-policy/  
**Game:** Fly Exterminator (Meta Quest 3 mixed-reality game)  
**Publisher:** Boundary Interactive LLC  
**Contact:** fly.exterminator@boundaryinteractive.com  
**Purpose:** Align the existing Termly-based privacy policy with what the game actually collects today and what is planned for the next release. Keep the same URL (required for Meta Quest dashboard).

> **Note:** This document is a product/engineering brief, not legal advice. After edits, have counsel review before shipping online features.

---

## Summary

The current policy is a good **shell** (Fly Exterminator is named, Quest MR is mentioned, contact/deletion paths exist). It is **not accurate** for online play, leaderboards, or analytics. The California “Categories of Personal Information” table incorrectly marks almost everything as **“Collected: NO”** while the game uses Unity Gaming Services (UGS) and Meta platform sign-in.

**Goal:** Add a Fly Exterminator–specific section, fix the collection table, name third-party processors, and remove or narrow generic sections that do not apply. Do **not** replace the entire policy unless counsel requests it.

---

## Checklist (in order)

- [ ] **1.** Bump **“Last updated”** date to the day changes go live.
- [ ] **2.** Insert new section **“Fly Exterminator — Data We Collect and Your Choices”** (draft below) after the intro / summary, before or within “Information We Collect.”
- [ ] **3.** Add **“Third-Party Service Providers”** subsection naming **Unity Technologies** and **Meta Platforms Technologies** (draft below).
- [ ] **4.** Fix the **California CPRA categories table** — change relevant rows from **NO** to **YES** with qualifiers (draft below).
- [ ] **5.** **Remove or narrow** irrelevant generic sections (list below).
- [ ] **6.** Add a short **“Future updates”** note for optional crash reporting (draft below).
- [ ] **7.** Verify contact email `fly.exterminator@boundaryinteractive.com` and deletion/DSAR instructions remain prominent.
- [ ] **8.** Confirm the page stays **public HTTPS** with no login wall (Meta requirement).

---

## Step 2 — Insert this new section

**Suggested heading:** `Fly Exterminator — Data We Collect and Your Choices`

**Placement:** Near the top of the policy, after the summary and before generic “Information We Collect” boilerplate.

```markdown
### Fly Exterminator — Data We Collect and Your Choices

Fly Exterminator is a mixed-reality game for Meta Quest headsets. Depending on how you play, we may process different types of information.

#### Offline play

If you choose **Offline play** (or play without enabling online features):

- Game progress, unlocks, settings, and lifetime statistics are stored **locally on your headset** (for example, in JSON files under the app’s persistent data path and in Unity PlayerPrefs).
- We do **not** initialize Unity Gaming Services, submit scores to leaderboards, or send gameplay analytics.
- Mixed-reality features (passthrough, room setup, hand tracking) are handled by **Meta’s platform and device software** on your headset. We do not receive your raw room mesh or camera video on our servers.

#### Online play

If you choose **Online play**:

- The game signs you in through **Meta (Oculus) platform authentication**, which is linked to **Unity Gaming Services (UGS) Authentication**.
- We receive and use a **platform user identifier** and **display name** (for example, your Meta/Oculus name, which Unity may append with a numeric suffix for uniqueness) to identify your account and show your name on leaderboards.
- When you complete a qualifying run, we submit your **score** and compact **run metadata** (game mode, flies caught, play time, room area estimates, difficulty options, and similar gameplay statistics) to **Unity Gaming Services Leaderboards**. Leaderboard entries may be **visible to other players**.
- Online features require an internet connection. You can switch to Offline play in Settings to stop future cloud uploads (existing cloud leaderboard entries are not automatically deleted).

#### Analytics (online only, optional)

If you are in **Online play**, we may ask whether you allow **gameplay analytics** via **Unity Gaming Services Analytics**. Analytics is **off unless you opt in** (first launch prompt and Settings toggle).

If you allow analytics, we send event data to Unity, such as:

- **run_completed** — mode, score, play time, kills, difficulty/loadout options, room area estimates, whether a score was submitted to leaderboards
- **run_abandoned** — mode and exit reason
- **tutorial_funnel** — tutorial step and completion/abandon counts
- **leaderboard_submit** — submit success/failure, rank, and percentile when applicable
- **visit_ended** — session length and visit counts
- **player_profile** — aggregated lifetime stats (games completed, favorite mode, visit habits, etc.), sent periodically or after certain milestones

Analytics events may include your **UGS player ID** and **platform key** (for example, `meta`). They do **not** include your email address unless you separately provide it to us.

If you deny analytics or turn it off in Settings, we stop sending new analytics events. Leaderboards and authentication may still work if Online play is enabled.

#### Local preferences

Regardless of mode, the app may store on-device preferences such as audio levels, tutorial progress flags, analytics consent choice, and online/offline mode selection.

#### Data deletion

To request deletion of data we control (including leaderboard or analytics data associated with your account, where applicable), contact **fly.exterminator@boundaryinteractive.com**. Some data may also be managed through Meta or Unity account/platform tools as described in their privacy policies.
```

---

## Step 3 — Third-party service providers

Add or expand **“When and With Whom We Share Your Personal Information”** (or equivalent) with:

```markdown
### Service providers for Fly Exterminator

We use the following third parties to operate online features. They process data on our behalf according to their terms and privacy policies:

| Provider | Purpose | Typical data |
|----------|---------|--------------|
| **Unity Technologies** (Unity Gaming Services) | Account authentication, leaderboards, optional gameplay analytics | UGS player ID, platform-linked account info, scores, leaderboard display name, gameplay event parameters described above |
| **Meta Platforms Technologies** (Meta Quest / Horizon OS) | Platform sign-in, entitlement verification, mixed-reality and device features | Oculus/Meta user ID, display name, device/platform signals required for VR and MR |

We do not sell your personal information. We do not use Fly Exterminator data for third-party advertising.
```

**Links to include (optional but recommended):**

- Unity Privacy Policy: https://unity.com/legal/privacy-policy  
- Meta Privacy Policy: https://www.meta.com/legal/privacy-policy/  
- Unity Gaming Services terms: https://unity.com/legal/terms-of-service  

---

## Step 4 — Fix California CPRA categories table

The current table marks **Identifiers (A)**, **Internet activity (F)**, and related categories as **Collected: NO**. That is **incorrect for Online play and optional analytics**.

Update the table so it reflects **conditional collection** (only when the user enables Online play / analytics). Suggested corrections:

| Category | Collected? | Examples for Fly Exterminator |
|----------|------------|------------------------------|
| **A. Identifiers** | **YES** (Online play) / **NO** (Offline only) | UGS player ID; Meta/Oculus user ID used for sign-in; leaderboard display name |
| **B. Customer records (CA)** | **NO** | We do not collect mailing address, payment card, etc. in the game |
| **C. Protected classifications** | **NO** | Not collected |
| **D. Commercial information** | **NO** | No in-app purchases in current version |
| **E. Biometric information** | **NO** | Hand/body tracking is processed on-device for gameplay; we do not collect biometric templates on our servers |
| **F. Internet or network activity** | **YES** (Online + analytics opt-in) / **NO** (Offline) | Gameplay analytics events, leaderboard API calls, authentication sessions |
| **G. Geolocation data** | **NO** (precise GPS) | We do not collect GPS location. Room size/area used for gameplay is derived locally from MR setup, not GPS. |
| **H. Audio, visual, etc.** | **NO** (on our servers) | Passthrough/camera data stays on device / Meta stack; not uploaded to Boundary Interactive |
| **I. Professional / employment** | **NO** | Not collected |
| **J. Education** | **NO** | Not collected |
| **K. Inferences** | **LIMITED** | Aggregated gameplay statistics in analytics (e.g., favorite mode); not used for advertising profiles |

Add a footnote: *“Collection depends on your choices (Offline vs Online play; analytics opt-in).”*

Also update the **“Do we collect information from third parties?”** answer: change from a blanket **NO** to explain that **Meta provides account identifiers and display names** when you use Online play and Meta sign-in.

---

## Step 5 — Remove or narrow irrelevant sections

These Termly boilerplate sections **do not apply** to Fly Exterminator and confuse store reviewers. **Delete** or replace with “Not applicable to Fly Exterminator”:

| Section | Action |
|---------|--------|
| Social media logins (Facebook, X/Twitter, etc.) | **Remove** — game does not offer social login |
| Google API Limited Use disclosure | **Remove** — no Google API user data |
| Broad “GPS geolocation” collection claims | **Narrow** — clarify we do not collect GPS; MR room sizing is local |
| “We do not collect information from third parties” (if absolute) | **Revise** — Meta provides platform account data for Online play |
| Generic “payment / purchase” examples | **Remove or mark N/A** unless IAP is added later |

**Keep** (but ensure consistency):

- GDPR / UK / Swiss rights sections  
- US state privacy rights (CCPA/CPRA, etc.)  
- Data retention, security, children’s privacy (game is not directed at under-13)  
- Contact and DSAR / deletion via email  

---

## Step 6 — Future features (optional short paragraph)

Add near the end or in a “Changes to this policy” section:

```markdown
We may update Fly Exterminator with additional online or diagnostic features (for example, optional crash or performance reporting through Unity). If we enable new data collection, we will update this privacy policy and, where required, ask for your consent before collecting additional information.
```

**Current status (do not claim as active unless enabled):**

- Unity **Engine Diagnostics** / crash reporting: **not enabled** in the current build (`m_EnableCloudDiagnosticsReporting: 0`).
- Unity **Friends**, **Cloud Save**, **Ads**: **not used**.

---

## Technical reference (for accuracy — do not paste verbatim into policy)

Use this only to verify the public-facing text is correct.

### Unity Gaming Services packages in use

- Authentication (Meta/Oculus sign-in on Quest; anonymous in editor)
- Leaderboards
- Analytics (consent-gated)
- Core

### Leaderboard data submitted

- Numeric **score**
- **Display name** (from Meta, sanitized; Unity may add `#1234` suffix)
- **Metadata JSON**: game mode, raw score, time taken, room total/effective area, fly settings, mode-specific stats, optional device type/model strings

### Analytics events (only if user opts in)

`run_completed`, `run_abandoned`, `tutorial_funnel`, `leaderboard_submit`, `visit_ended`, `player_profile` — see engineering `RunAnalyticsEventBuilder.cs` for full parameter list.

### Local-only files (Offline and Online)

- `LifetimeStats.json`, `StageUnlockStatus.json` under app persistent data path
- PlayerPrefs: audio settings, analytics consent, tutorial flags, etc.

### Planned UX (include in policy now)

| Mode | Leaderboards | Analytics | UGS init |
|------|-------------|-----------|----------|
| **Offline** | Off | Off | No |
| **Online** | On | Opt-in toggle | Yes + Meta auth |

First launch: choose Offline vs Online; if Online, separate analytics Allow / Not now prompt.

---

## Meta Quest dashboard alignment

After the website is updated:

1. **Privacy Policy URL** in Meta Developer Dashboard → App → Privacy → set to `https://boundaryinteractive.com/privacy-policy/`
2. **Data Use Checkup** answers must match the updated policy (identifiers, online services, analytics).
3. In-game **Settings or Credits** should link to the same URL (separate game task).

Meta **VRC.Quest.Privacy.4** expects a working deletion/contact path — keep `fly.exterminator@boundaryinteractive.com` visible.

---

## What NOT to change

- **Canonical URL** — keep `https://boundaryinteractive.com/privacy-policy/` (no new path unless counsel advises).
- **Entity name** — Boundary Interactive LLC.
- **Game name** — Fly Exterminator.
- **General GDPR/CCPA rights language** — keep unless counsel consolidates.

---

## Suggested “Last updated” line

```markdown
Last updated: [MONTH DAY, YEAR]
```

Use the actual publication date when edits go live.

---

## Post-edit verification

- [ ] Page loads over HTTPS without authentication  
- [ ] Fly Exterminator section is visible without scrolling past unrelated social-login text  
- [ ] CPRA table no longer claims zero identifier collection for all users  
- [ ] Unity and Meta are named as processors  
- [ ] Offline vs Online vs Analytics choices are described clearly  
- [ ] Contact email works and is linked (`mailto:fly.exterminator@boundaryinteractive.com`)  
- [ ] Lawyer review scheduled before online leaderboards ship to production  

---

## Related game repo tasks (not for website agent)

These are tracked in the Fly Exterminator OpenXR Unity project, not on the website:

1. Implement Offline / Online play mode gating for UGS, leaderboards, and analytics  
2. Add in-app Privacy Policy link in Settings / Credits  
3. Align first-launch consent flow with policy text  

---

*Document generated for Boundary Interactive — Fly Exterminator OpenXR project. Source: product privacy review, April 2026 policy baseline.*
