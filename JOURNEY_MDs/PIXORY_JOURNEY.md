# Pixory – Project Journey  
**Theme:** *The Idea Was Clear, the Path Was Not*

This document captures the real development journey of Pixory — including false starts, scope mistakes, technical failures, and the decisions that shaped the final v1.

It is not a celebration.  
It is a record.

---

## Why Pixory Exists

Pixory began as a simple question:

> “What if personal images could be stored privately and still gain the benefits of AI understanding?”

The initial idea sounded exciting:  
*AI-powered image cloud with search, tagging, and analysis.*

That excitement quickly became a problem.

---

## Phase 1: Ideation Without Constraints

**Initial Concept**
- Personal image cloud
- AI-generated descriptions
- Search by content
- Albums, filters, sharing, future ideas

At this stage, Pixory had:
- No defined user
- No defined v1
- No architectural boundaries

Everything felt important.  
That was the first red flag.

**Lesson:**  
If everything feels important, nothing is being built.

---

## Phase 2: Early Backend Experiments

The backend was started using Spring Boot with the assumption that images could be stored locally.

### What Was Attempted
- Multipart file uploads
- Local filesystem storage (`D:/uploads`)
- Database metadata persistence

### What Broke
- Local paths could not be safely served to browsers
- Environment-specific storage paths
- No scalability or portability

### Correction
Cloudinary was introduced to:
- Store original images
- Serve images via CDN-backed URLs
- Remove filesystem dependency

**Lesson:**  
Local storage works for demos, not systems.

---

## Phase 3: Frontend Reality Check

An Angular-based gallery UI was created to display uploaded images.

### Problems Encountered
- Inconsistent card sizing
- Overuse of loaders and progress bars
- UI complexity without clear user value

### Decisions Made
- CSS Grid over forced Flex layouts
- Removed upload progress bar for calmer UX
- Focused on preview → result feedback

**Lesson:**  
UI is not decoration. It defines system clarity.

---

## Phase 4: AI Integration (Where Things Actually Got Hard)

AI image analysis was introduced using Google Gemini.

### Initial Issues
- Manual JSON payload construction broke requests
- AI responses exceeded database column limits
- High-resolution images caused token exhaustion (429 errors)
- Incorrect or unavailable model versions caused failures

### Corrections
- Switched to Map-based JSON serialization
- Changed database columns from VARCHAR to TEXT
- Introduced image resizing before AI analysis
- Locked model usage to `gemini-2.5-flash`

### Result
- Token usage reduced by ~70%
- Stable AI responses
- Predictable backend behavior

**Lesson:**  
AI integration is engineering, not magic.

---

## Phase 5: Scope Collapse (The Turning Point)

At this stage, Pixory had:
- Backend logic
- Frontend UI
- AI integration
- Growing feature ideas

But it still could not be described in one sentence.

That forced a hard stop.

### The Question That Changed Everything
> “What problem does Pixory solve on day one?”

### The Answer
Pixory v1 does exactly four things:

> Upload → Store → Analyze → Display

Everything else was cut.

No social features.  
No advanced search yet.  
No future promises.

**Lesson:**  
v1 is not about ambition. It is about survival.

---

## Phase 6: Architecture Discipline

The project was split into:
- Backend repository
- Frontend repository
- Meta repository for documentation

This enforced:
- Clear responsibility boundaries
- Independent evolution
- Realistic production structure

**Lesson:**  
Architecture is a decision, not a diagram.

---

## Phase 7: Documentation as a First-Class Artifact

Instead of treating documentation as an afterthought:
- READMEs were written per repository
- A root meta-repo was created
- This journey document was added

The goal was not explanation.  
The goal was **traceability**.

**Lesson:**  
If you cannot explain how a project evolved, you do not fully understand it.

---

## Current State (v1)

As of v1:
- Image upload pipeline is stable
- Cloud storage is production-safe
- AI analysis is optimized and predictable
- Frontend provides a clean, calm user flow

Pixory is **v1 complete**, not finished.

---

## What Pixory Taught Me

- Scope control is an engineering skill
- AI systems require cost and failure planning
- UI decisions affect backend complexity
- Shipping v1 matters more than perfect ideas
- Stopping is harder than building

---

## What Comes After v1 (Intentionally Deferred)

- Semantic search over AI metadata
- Drag-and-drop uploads
- Upload progress tracking via interceptors
- Advanced filtering and categorization

These are planned, not promised.

---

## Final Note

Pixory is not impressive because of its features.

It is valuable because it demonstrates:
- End-to-end system thinking
- Failure-driven iteration
- Architectural restraint
- The discipline to ship and stop

That is the real project.

*The idea was clear.  
The path was not.*
