# Innosend for Magento 2

Meta package that installs the full Innosend suite for Magento 2: API integration, pickup points, and order synchronization.

**Current version: 1.1.0**

---

## Wiki navigation

| Page | Description |
|------|-------------|
| **[Preparations](Preparations)** | **Do this first:** repository and Composer auth (developer + deploy) |
| [Requirements](Requirements) | PHP, Magento, Composer versions |
| [Installation](Installation) | Composer install and Magento setup commands |
| [Configuration](Configuration) | API Token, Order Sync, and Pickup Points settings |
| [Optional: Hyvä Checkout](Optional-Hyva-Checkout) | Add pickup points support for Hyvä Checkout |
| [Post-install checklist](Post-install-checklist) | Verify installation is complete |
| [Troubleshooting](Troubleshooting) | Common issues and solutions |
| [Module overview](Module-overview) | Packages, Magento module names, and versions |
| [Support](Support) | Documentation and contact |

---

## Quick start

1. **First:** complete [Preparations](Preparations) (private Packagist repo + Composer auth).
2. Then run:

```bash
composer require innosend/magento2
php bin/magento module:enable Innosend_Integration Innosend_PickupPoints Innosend_OrderConnector
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento cache:flush
```

3. Go to **Stores → Configuration → Innosend → API Configuration**, enter your **API Token**, and click **Test API Token Connection**.

---

## What's new in 1.1.0

- **Single API Token** replaces the old API Key + API Secret credentials.
- All admin config fields for API Key, API Secret, `allow_mutations`, and `enable_pickup_points` removed.
- Configuration path for the token moved from `pickup_points/api_token` → `api_token`.
- Automatic config migration runs on `setup:upgrade`.

See the [CHANGELOG](https://gitlab.com/innosend/magento2-integration/-/blob/main/CHANGELOG.md) in each module for full details.
