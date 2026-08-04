---
tags:
  - docusign
  - pattern
---

## 🧱 Block 3 — **DocuSign Template Pattern (Board / Legal Docs)**

**Use case:** bylaws, resolutions, consents, appointments

```id="ds-template-01"
TEMPLATE: Multi-Signer (Parallel Default)

STEP 0 — Always start clean
→ Click "Send" (never "Sign")

STEP 1 — Add all signers
→ Enter names + emails
→ Set routing order:
   - ALL = 1  (parallel signing, default)

STEP 2 — Lock mental model
→ Each signer owns their own fields
→ You must SELECT them before placing fields

STEP 3 — Place fields (deterministic loop)
FOR EACH signer:
   → Select signer in dropdown
   → Place:
        - Signature
        - Date Signed
   → Optional:
        - Name / Title (if needed)

STEP 4 — Visual verification
→ Each signer’s fields:
   - Correct location
   - Correct color
   - Correct name when clicked

STEP 5 — Send
→ Ignore optional metadata fields
→ Click Send

STEP 6 — Execution protocol (tell all signers)
→ “Click Review → Sign → Finish (NOT Finish Later)”

STEP 7 — Completion
→ Wait for status = Completed
→ Download:
   - Combined PDF
   - Certificate of Completion
```

---

## 🧭 Block 4 — **Document Role Patterns (Who Signs What)**

```id="ds-roles-01"
RULESET:

1) Governance actions (resolutions, bylaws)
   → Signed by: current authority (you + Shea)
   → NOT signed by: person being appointed

2) Acceptance / acknowledgment
   → Signed by: the person receiving role (e.g., Ross)

3) Mixed cases (rare)
   → Only include all parties if document explicitly requires it
```

---

## ⚡ Block 5 — **Fast Path (5-minute execution)**

```id="ds-fast-01"
1) Send
2) Add all signers (order = 1)
3) Loop:
     select signer → place signature
4) Send
5) Everyone: Sign → Finish
```

---

## ☠️ Block 6 — **Do Not Do List**

```id="ds-anti-01"
- Do NOT start with "Sign" for multi-party docs
- Do NOT place fields without checking selected recipient
- Do NOT mix routing orders unless intentional
- Do NOT trust "Finish Later"
- Do NOT upload partially signed docs
```

---

## 🧩 Anchor Insight (pin this mentally)

> **DocuSign is not about documents.  
> It is about mapping signatures to people with explicit ownership.**

---

This is now a **stable pattern** you can reuse for:

- Ross appointment
    
- Future board actions
    
- Anything requiring multiple signatures
    

If you want next step: we can create a **standard resolution template** for Ross so the whole flow becomes copy → send → done.