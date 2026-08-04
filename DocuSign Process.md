---
tags:
  - docusign
  - workflow
---

## 🧭 Block 1 — **Correct DocuSign Process (Multi-Signer / Envelope)**

**Purpose:** Fast, deterministic path to a completed, legally clean document.

```
1) Start in the right workflow
   → Click "Send" (NOT "Sign")

2) Define all actors upfront
   → Add every signer (name + email)
   → Set routing:
       - Same order number → parallel (recommended)
       - Different numbers → sequential

3) Assign fields correctly
   For each signer:
       → Select their name (dropdown)
       → Place ONLY their signature + date fields
   Rule:
       Placement ≠ ownership
       Ownership is determined by selected recipient

4) Sanity check before sending
   → Every signer has at least one required field
   → Each field is assigned to the correct person
   → Colors/names match expected ownership

5) Send (create envelope)

6) Execution phase
   Each signer:
       → Opens email
       → Clicks "Review Document"
       → Signs
       → Clicks "Finish" (NOT "Finish Later")

7) Completion
   → Status = Completed
   → Download:
       - Final PDF
       - Certificate of Completion
```

---

## ⚠️ Block 2 — **Entropy Pattern: Mixing Workflows**

**Trigger mistake:**  
Starting with the **single-signer mental model (“Sign”)** while actually using the **multi-signer system (“Send” / envelopes)**.

---

### What breaks (and why)

```
1) Hidden state mismatch
   → System expects:
       - multiple recipients
       - explicit field ownership
   → User assumes:
       - “I just sign and send it along”

Result:
   Invisible configuration errors accumulate
```

---

### Failure modes you experienced

```
A) Missing recipient
   → Only one signer defined
   → No way to assign fields to others

B) Field misassignment (core bug)
   → Signature placed in correct location
   → BUT assigned to wrong person
   → System reports: “missing required fields”

C) Color confusion
   → Colors represent recipient ownership
   → Not obvious → duplicates / misassignments

D) Accidental sequencing
   → Routing order defaults to 1 → 2 → 3
   → Creates hidden dependency:
       signer 2 cannot act until signer 1 finishes

E) “Finish Later” trap
   → Looks like progress
   → Actually: nothing submitted
   → Routing stalls silently

F) Re-auth / session friction
   → Repeated login interrupts flow
   → Increases cognitive load → more errors
```

---

### Why entropy explodes

```
Each mistake is small and local.
But they interact:

wrong workflow
  → wrong mental model
    → wrong recipient setup
      → wrong field ownership
        → validation errors
          → retries
            → session resets
              → loss of state awareness

Result:
   Nonlinear time cost (5 min → 47 min)
```

---

### Recovery principle

```
When confused:
   Reset to first principles

1) Who are the signers?
2) Is routing parallel or sequential?
3) For each field:
     Who owns it?

If any answer is unclear → stop and fix upstream
```

---

## 🧩 One-line memory hook

> **“Select name → place field → verify ownership → send.”**

---

This captures both:

- the **deterministic path** (Block 1)
    
- and the **failure topology** (Block 2)
    

If you want, we can convert this into a reusable **DocuSign template pattern** so you never rebuild this from scratch again.