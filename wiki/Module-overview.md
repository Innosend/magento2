# Module overview

← [Home](home)

---

| Package | Magento module name | Version | Purpose |
|---------|---------------------|---------|---------|
| `innosend/magento2-integration` | `Innosend_Integration` | 1.1.0 | Shared API client (Bearer token auth), config model, healthcheck |
| `innosend/magento2-pickup-points` | `Innosend_PickupPoints` | 1.1.0 | Pickup point selection in checkout, carrier list, map, order/quote storage |
| `innosend/magento2-order-connector` | `Innosend_OrderConnector` | 1.0.3 | Order and status synchronization with Innosend |
| `innosend/magento2-checkout-hyva` | `Innosend_CheckoutHyva` | 1.0.1 | Hyvä Checkout–compatible pickup point selector (optional) |

---

## Authentication model (v1.1.0)

All modules share a single **Bearer token** (`Authorization: Bearer {API_TOKEN}`) configured in:

```
Stores → Configuration → Innosend → API Configuration → API Token
```

No separate API Key or API Secret is required.

---

## Module dependency chain

```
Innosend_Integration          ← required by all other modules
    └── Innosend_PickupPoints ← required by Innosend_CheckoutHyva
    └── Innosend_OrderConnector
    └── Innosend_CheckoutHyva (optional, Hyvä only)
```

---

[Installation](Installation) · [Optional: Hyvä Checkout](Optional-Hyva-Checkout)
