# Stripe Operations — Phronesis Project

## Purpose

This document records the operational knowledge needed to manage the Phronesis Stripe account. It is intended to prevent rediscovering configuration decisions months or years later.

---

# Current Status (RC0)

**Reality votes YES.**

The complete support workflow has been tested successfully.

```
Visitor
    ↓
Phronesis website
    ↓
Stripe Payment Link
    ↓
Stripe Checkout
    ↓
Payment Authorization
    ↓
Stripe Balance
```

A live $1 test contribution completed successfully.

---

# Website Integration

Website:

```
phronesisproject.org
```

Repository:

```
GitHub
mcorning/Phronesis-Online
```

Support page:

```
support.html
```

Stripe component:

- Payment Link
    
- Buy Button embed
    
- Customer chooses amount
    

No backend required.

No server-side code required.

No secret key required.

---

# Stripe Dashboard

Organization

```
Phronesis Project
```

Payment mechanism

```
Payment Link
Support the Phronesis Project
```

Supporters choose their own contribution amount.

---

# Buy Button

The website uses the generated Stripe Buy Button.

To regenerate:

```
Payment Links
    ↓
Support the Phronesis Project
    ↓
Buy button
    ↓
Copy Code
```

Paste the generated code directly into:

```
support.html
```

Never edit the generated Stripe code.

---

# API Keys

Publishable key

Safe for browser use.

Included automatically in the generated Buy Button.

Secret key

Never place on GitHub Pages.

Never embed in HTML.

Never expose publicly.

---

# Payments

Verify payments at

```
Payments
```

Check

- Gross amount
    
- Stripe fee
    
- Net amount
    
- Status
    

---

# Customers

Supporters appear under

```
Customers
```

Guest customers are created when no Stripe account exists.

---

# Balance

Current historical balance

```
$467.65
```

Current test payment

```
$1.00 gross
$0.67 net
```

Incoming funds settle daily.

---

# Payouts

Bank

```
Mid Oregon Credit Union
```

Current policy

```
Manual payouts
```

No automatic transfers occur.

Funds remain in Stripe until explicitly transferred.

---

# Historical Note

A historical transaction exists:

```
Dec 12, 2025

EVO Two SE Upgrade
$484.42
```

No corresponding record was found in the SSC Stripe account.

Evidence suggests this commercial transaction was processed through the Phronesis Stripe account.

Current balance appears consistent with:

```
Gross sale
− Stripe fees
= $467.65
```

This should be reconciled before transferring historical funds.

---

# Lessons Learned

## GitHub Pages

The website is published from

```
mcorning/Phronesis-Online
```

A nested Git repository accidentally became tracked as a submodule.

Symptoms included:

- GitHub Pages build failures
    
- Missing Sync button
    
- Strange VS Code Source Control behavior
    

Removing the accidental submodule restored normal deployment.

---

## Stripe

The simplest architecture won.

No custom checkout.

No API programming.

No backend.

Stripe Payment Links plus Buy Button provide everything required.

---

# Operational Checklist

When updating Support:

1. Edit `support.html`
    
2. Keep generated Stripe code unchanged
    
3. Commit
    
4. Push
    
5. Verify GitHub Pages build
    
6. Hard refresh website
    
7. Test payment if appropriate
    

---

# Future Improvements

- Improve Support page copy.
    
- Center and style the Stripe card.
    
- Remove obsolete placeholder donation widgets.
    
- Replace remaining "Donate" language with "Support" where appropriate.
    
- Reconcile the historical $484.42 SSC transaction.
    
- Decide whether manual payouts remain appropriate as support volume grows.
    

---
## Open Questions

- Investigate the December 12, 2025 Stripe payment for "EVO Two SE Upgrade for two amps" ($484.42). The transaction appears in the Phronesis Stripe account but not in the SSC Stripe account. Trace the event beginning with Pirate Ship, then SSC order records, to determine why it was processed through the Phronesis account and whether the retained balance should ultimately be reconciled with SSC.