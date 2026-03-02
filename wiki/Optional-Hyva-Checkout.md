# Optional: Hyvä Checkout

← [Home](home)

---

If your store uses **Hyvä Checkout**, install the dedicated Alpine.js pickup point component:

```bash
composer require innosend/magento2-checkout-hyva
php bin/magento module:enable Innosend_CheckoutHyva
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento cache:flush
```

No additional configuration is needed — this module reads from the same **API Token** and **Pickup Points** settings already configured in the Integration and Pickup Points modules.

---

## What this module provides

- Alpine.js pickup point selector embedded in Hyvä checkout
- List + interactive map view (OpenStreetMap or Google Maps)
- Distance per pickup point
- Opening hours display
- CSP-compatible (no `eval`, no inline event handlers)

---

## Requirements

- `innosend/magento2-pickup-points` ≥ 1.1.0 (included in `innosend/magento2` 1.1.0)
- Hyvä Checkout theme

---

[Installation](Installation) · [Module overview](Module-overview)
