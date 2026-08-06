
# Audit Note — December 2025 Stripe Reconciliation

**Date of Investigation:** 2026-08-04  
**Investigators:** Michael Corning and ChatGPT (Watson)

## Purpose

While validating the new Phronesis Project Support page and Stripe integration, we discovered an unexpected historical Stripe balance of **$467.65**. This note documents the investigation and conclusions.

---

# Trigger

During live testing of the new Phronesis Project Support page:

- Website successfully accepted a $1.00 test contribution.
    
- Stripe recorded the payment correctly.
    
- Existing Stripe balance unexpectedly showed **$467.65**.
    

Initial concern:

> Why does the Phronesis Stripe account contain several hundred dollars before any meaningful nonprofit fundraising?

---

# Investigation

## Stripe

Observed:

- Historical balance: **$467.65**
    
- Manual payouts enabled.
    
- No payout history.
    
- Mid Oregon Credit Union configured as settlement account.
    

Historical customer:

```text
Unnamed customer
$484.42
Description:
EVO Two SE Upgrade for two amps
Date:
2025-12-12
```

---

## SSC Stripe

No matching transaction found.

This confirmed the payment had **not** been processed through the SSC Stripe account.

---

## Help Desk

Searching for:

- Evo Two
    
- Evo 2
    
- Upgrade
    

revealed the relevant support case.

Important findings:

Jason instructed:

> Customer pays round-trip shipping for Evo 2 → Evo Two-SE upgrade.

Support thread records:

```
Shipping USA → Taiwan

$241.21 × 2

≈ $482.42
```

The Stripe payment of **$484.42** differs by only **$2.00**, consistent with a small adjustment, insurance, or invoice correction.

---

## Pirate Ship

Two labels were found matching the transaction.

12 Dec 2025

Label 1

```
$184.21
```

Label 2

```
$180.49
```

Total outbound labels:

```
≈ $364.70
```

Labels correspond to shipment of two amplifiers to NuPrime Taiwan for upgrade.

---

# Reconstruction

Evidence supports the following sequence:

```text
Customer requests Evo Two-SE upgrade
            │
            ▼
Jason creates custom payment
            │
            ▼
Payment processed through
Phronesis Stripe account
            │
            ▼
Customer pays ≈ $484
            │
            ▼
Pirate Ship labels purchased
            │
            ▼
Units shipped to Taiwan
            │
            ▼
Upgrade completed
            │
            ▼
Units returned to customer
```

---

# Why the money remained in Stripe

Stripe configuration shows:

```
Manual payouts
```

No payout history exists.

Therefore:

- payment remained in Stripe,
    
- fees were deducted,
    
- remaining balance stayed in account.
    

Current balance:

```
$467.65
```

matches:

```
Customer payment
minus Stripe fees
```

---

# Current Workflow Comparison

This transaction represents a historical workflow variant.

December 2025:

```text
Help Desk
      ↓
Custom payment
      ↓
Stripe
      ↓
Pirate Ship
      ↓
Factory upgrade
```

Current workflow:

```text
WooCommerce
      ↓
SSC Stripe
      ↓
Order
      ↓
Shipping
```

Current process is substantially cleaner and avoids this corner case.

---

# Accounting Assessment

Evidence strongly suggests:

- funds originated from legitimate SSC business,
    
- transaction was associated with Evo Two-SE upgrade program,
    
- payment remained in Phronesis Stripe because manual payouts were never executed,
    
- no evidence of missing or misappropriated funds,
    
- no evidence of duplicate payment.
    

---

# Recommendation

Transfer the historical Stripe balance to the SSC USB operating account after current test payment settles.

Document transfer as reconciliation of historical SSC shipping funds processed through the Phronesis Stripe account.

Given:

- age of transaction,
    
- one-off workflow,
    
- current workflow replacement,
    
- cost of reopening 2025 accounting,
    

no further reconstruction of 2025 books is recommended unless required by future audit.

---

# Lessons Learned

This investigation was initiated by a $1.00 live test of the new Phronesis Support page.

The operational test unexpectedly exposed an unresolved historical accounting artifact.

The investigation validated:

- GitHub Pages deployment
    
- Stripe integration
    
- Support workflow
    
- Manual payout configuration
    
- Historical transaction provenance
    
- Current SSC workflow improvements
    

---

