---
title: Software Design Policy
tags: [canonical, policy, Syntopix]
created: 2025-05-09
---

**Syntopix Holarchy: Software Design Policy (`Policies.md`)**

---

### 🧭 Guiding Principle
All Syntopix software must be designed for **clarity, shareability, and emergence**. Code should be readable and improvable by others, with minimal onboarding.

---

### ✅ Core Policies

#### 1. **Readable Over Clever**
Favor readable constructs over elegant one-liners. If another developer can't trace your logic at a glance, it's too clever.

#### 2. **Export Discipline**
- Use `default export` for fully encapsulated services (e.g., `SocketService`)
- Use `named exports` for utility libraries
- Explicitly alias imports where ambiguity might arise

#### 3. **Function-Style Event Handling**
Inside components, handle side-effects like `moveTopic()` or `saveTopiq()` using a `respond()`-style internal method:
```js
function respond(result) {
  if (result.success) doThis();
  else handleThat();
}
```
This makes callbacks readable, testable, and unit-replaceable.

#### 4. **Graph Mindset**
Design with holons in mind. Components and logic should expect nesting, self-reference, and emergence—favor graphs over trees where appropriate.

#### 5. **Entropy-Aware UX**
User interfaces must lower cognitive load, not raise it. Use layout, spacing, and tooltips to reduce user entropy.

#### 6. **Persistent State Awareness**
Always ask: What should persist? What’s emergent? Favor local cache, Redis, or IndexedDB only when necessary—avoid premature optimization.

#### 7. **Data Should Travel Well**
Topiqs, Spaces, and metadata must be serializable and REST/GraphQL/JSON-ready. Future ports (mobile, offline, etc.) depend on this.

---

### 🔄 Refactor Rules

1. If you see entropy increasing, pause and ask: *Can this be simplified or split?*
2. If a holon is becoming too dense, consider emergent subdivision (i.e., break into smaller holons).
3. If a new principle emerges repeatedly, **promote** it to this file.

---

### 🔐 Versioning
This document governs all current and future Syntopix Holarchy codebases. Updates require agreement between primary maintainers (Michael and AI).