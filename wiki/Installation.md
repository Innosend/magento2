# Installation

← [Home](home)

---

**Prerequisite:** Complete [Preparations](Preparations) first (private Packagist repository and Composer authentication).

---

## 1. Require the meta package

From your Magento 2 root directory:

```bash
composer require innosend/magento2
```

This installs:

| Package | Version | Purpose |
|---------|---------|---------|
| `innosend/magento2-integration` | 1.1.0 | API client, Bearer token auth, config |
| `innosend/magento2-pickup-points` | 1.1.0 | Pickup points in checkout |
| `innosend/magento2-order-connector` | 1.0.3 | Order and status sync |

## 2. Enable modules and upgrade

```bash
php bin/magento module:enable Innosend_Integration Innosend_PickupPoints Innosend_OrderConnector
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento cache:flush
```

> `setup:di:compile` is required in 1.1.0 — new interfaces and a data patch are registered.

## 3. Deploy static content (production only)

```bash
php bin/magento setup:static-content:deploy -f
```

## 4. Updating from 1.0.x

```bash
composer update innosend/magento2
php bin/magento setup:upgrade      # runs MigrateConfigPaths data patch automatically
php bin/magento setup:di:compile
php bin/magento cache:flush
```

The data patch migrates your existing API Token from the old config path and removes the old API Key/Secret rows from `core_config_data`. No manual database changes are needed.

---

Next: [Configuration](Configuration)
