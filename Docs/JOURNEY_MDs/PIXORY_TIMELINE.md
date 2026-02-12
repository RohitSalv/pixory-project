# Pixory – Master Project Timeline (Date-Wise)

**Theme:** *The Idea Was Clear, the Path Was Not*  
**Status:** v1 Defined, Phase 1 Completed  
**Timezone:** IST  

This document is the **single, canonical timeline** of the Pixory project, reconstructed from all chats, logs, reports, failures, and decisions.

Dates reflect when work or decisions **surfaced and solidified**, not imaginary “perfect sprint days”.

No duplicates.  
No rewriting history.  
No narrative polishing.

---

## 📅 December 19, 2025 — Ideation Begins

| Phase    | Focus           | Details                                                           | Outcome                     |
|----------|-----------------|-------------------------------------------------------------------|-----------------------------|
| Ideation | Core Idea       | Proposed “personal image cloud storage with AI analysis & search” | Idea existed, shape did not |
| Naming   | Identity        | Asked for project name, tagline, repo naming                      | Project named **Pixory**    |
| Learning | Scope Awareness | Idea already felt too big                                         | Names gave the idea edges   |

At this stage:
- No defined v1
- No architecture
- No user boundary
- Only potential

**Lesson Learned:**  
Naming is the first constraint, not branding fluff.

---

## 📅 December 22, 2025 — Early Backend Experiments

| Phase   | Focus             | What Happened                | Problems                             | Outcome                                 |
|---------|-------------------|------------------------------|--------------------------------------|-----------------------------------------|
| Backend | Spring Boot setup | Initial image upload backend | Hibernate config & dialect issues    | Learned environment setup matters early |
| Storage | Cloudinary        | Integrated Cloudinary        | URL confusion, localhost assumptions | Understood cloud ≠ local filesystem     |

Key realizations:
- Local disk storage was fragile
- Environment-specific paths were unsafe
- Backend decisions leak into frontend fast

**Lesson Learned:**  
Local storage works for demos, not systems.

---

## 📅 December 25, 2025 — Idea Drift

| Phase     | Focus            | Issue                                      | Outcome                               |
|-----------|------------------|--------------------------------------------|---------------------------------------|
| Expansion | Feature Thinking | “AI image cloud” ballooned into everything | Realized not everything belongs in v1 |

Symptoms:
- Every feature felt “essential”
- No stopping rule
- Growing mental complexity

**Lesson Learned:**  
Ambition without constraints is a liability.

---

## 📅 December 27, 2025 — Git Reality Check

| Phase       | Focus       | What Broke             | Outcome                                      |
|-------------|-------------|------------------------|----------------------------------------------|
| Maintenance | Git Hygiene | Sensitive keys exposed | Learned rebase vs history rewrite discipline |

Impact:
- Repository trust risk
- Forced understanding of Git internals
- Early exposure to production hygiene

**Lesson Learned:**  
Source control mistakes scale faster than code mistakes.

---

## 📅 December 28, 2025 — Frontend Foundations

| Phase | Focus           | What Happened                  | Friction                      | Outcome                            |
|-------|-----------------|--------------------------------|-------------------------------|------------------------------------|
| UI    | Angular Gallery | Built image card & grid layout | CSS confusion, layout stretch | UI clarity affects backend clarity |

Issues surfaced:
- Uneven cards
- Layout rigidity
- UI decisions feeding back into API design

**Lesson Learned:**  
UI is not decoration. It defines system clarity.

---

## 📅 December 29, 2025 — Validation & UX Cleanup

| Phase      | Focus        | What Happened                            | Outcome                             |
|------------|--------------|------------------------------------------|-------------------------------------|
| Validation | Resume Value | Questioned if Pixory is portfolio-worthy | Confirmed originality via execution |
| UX         | Upload Flow  | Preview + progress bar added             | Removed progress bar for calmer UX  |
| UI         | Interaction  | Hover actions (download/delete/view)     | Cleaner interaction logic           |

Key decision:
- Remove over-engineered UX elements
- Favor calm feedback over noise

**Lesson Learned:**  
Simpler UI signals confidence.

---

## 📅 December 30, 2025 — Design & Stack Decisions

| Phase      | Focus            | Decision                            | Outcome                     |
|------------|------------------|-------------------------------------|-----------------------------|
| Design     | Homepage         | Designed full landing experience    | Clear design blueprint      |
| Tooling    | Figma            | Generated Figma frames & AI prompts | Design system thinking      |
| Tech Stack | Angular vs React | Stack anxiety surfaced              | Locked Angular for momentum |

Underlying tension:
- Visual appeal vs execution speed
- Tool switching temptation
- Fear of “wrong” long-term choice

**Lesson Learned:**  
Momentum beats theoretical perfection.

---

## 📅 December 31, 2025 — Heavy Day (Multiple Subsystems Completed)

### 🔹 Branding & Visual Identity

| Time     | Action         | Details                                 |
|----------|----------------|------------------------------------------|
| 11:32 PM | Initial Brief  | Minimal, AI-themed, blue/purple palette |
| 11:34 PM | Concept        | Eye + Pixel motifs                      |
| 11:35 PM | Refinement     | Shift to Vault / Hexagon geometry       |
| 11:36 PM | Implementation | React SVG logo component                |
| 11:37 PM | Finalization   | Production-ready logo assets            |

**Outcome:**  
Pixory Branding & Asset Design completed with meaning-driven visuals.

---

### 🔹 Angular Grid & Upload System

| Time     | Status | Action                             |
|----------|--------|----------------------------------|
| 11:00 AM | ✅     | JSON data analysis                 |
| 11:15 AM | ✅     | `@for` loop + typed interface     |
| 11:30 AM | ✅     | Grid UI styling                    |
| 11:45 AM | ✅     | Stretch fix via `align-items`     |
| 12:00 PM | 🔍    | Identified D:/ path security block |

Key realization:
- Browsers block local filesystem paths
- Backend must serve public URLs

---

### 🔹 AI Backend (GalleryV1)

| Date   | Event              | Status | Fix                            |
|--------|--------------------|--------|--------------------------------|
| Dec 28 | RestTemplate null  | ❌     | Dependency injection fixed     |
| Dec 28 | JSON payload break | ❌     | Switched to Map + ObjectMapper |
| Dec 29 | DB truncation      | ❌     | VARCHAR → TEXT                 |
| Dec 30 | Model 404          | ❌     | Switched to gemini-2.5-flash   |
| Dec 31 | 429 quota error    | ❌     | Image resize before AI         |
| Dec 31 | Final pipeline     | ✅     | Stable & optimized             |

**Lesson Learned:**  
AI integration is engineering, not magic.

---

### 🔹 Angular Landing Page Phase 1

| Milestone   | Component                | Outcome           |
|-------------|--------------------------|-------------------|
| Foundation  | Tailwind v4 + animations | Unified theme     |
| Navigation  | Glass header             | Brand continuity  |
| Hero        | Animated blobs           | Visual hook       |
| Core        | Features & Use Cases     | Product clarity   |
| Application | Upload + Gallery         | Landing → Product |

**Status:** Phase 1 complete.

---

## 📅 January 1, 2026 — Reflection & Discipline

| Phase         | Focus           | Outcome                                  |
|---------------|-----------------|------------------------------------------|
| Reflection    | Project clarity | “AI-powered image cloud” was meaningless |
| Scope Lock    | v1 definition   | Upload → Store → Analyze → Display       |
| Discipline    | Stop point      | Feature freeze                           |
| Documentation | History log     | Honest reconstruction                    |

This marked the moment Pixory became *explainable*.

---

## ✅ Surviving v1 Definition

> **“Pixory lets you upload images, securely store them, auto-analyze them with AI, and view them in a clean, searchable interface.”**

No buzzwords.  
No pretending.  
No fake disruption.

---

