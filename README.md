# Innosend for Magento 2

## Installation

### Fresh install

```bash
composer require innosend/magento2
php bin/magento module:enable Innosend_Integration Innosend_PickupPoints Innosend_OrderConnector
php bin/magento setup:upgrade
php bin/magento setup:di:compile
php bin/magento cache:flush
```

### Update from 1.0.x

```bash
composer update innosend/magento2
php bin/magento setup:upgrade      # runs MigrateConfigPaths data patch automatically
php bin/magento setup:di:compile
php bin/magento cache:flush
```

### Deploy static content (production)

```bash
php bin/magento setup:static-content:deploy -f
```

---

## Requirements

| Requirement | Version |
|-------------|---------|
| Magento 2 | 2.4.x (framework 102.x – 103.x) |
| PHP | 8.1, 8.2, or 8.3 |
| Composer | 2.x |
| cURL | Any version bundled with PHP |

---

## Configuration

### 1. API configuration (required)

1. Go to **Stores → Configuration → Innosend → API Configuration**
2. Set **Enable API connection** to **Yes**
3. Choose **Mode**: `Test` or `Production`
4. Enter the **API Token** from [dashboard.innosend.eu](https://dashboard.innosend.eu) → **Settings → API Keys**
5. Click **Save Config**
6. Click **Test API Token Connection** to verify

### 2. Order synchronization

1. Go to **Stores → Configuration → Innosend → Order Synchronization**
2. Enable order sync and configure sync options (sync on order place, retries, status sync interval)
3. Save config — verify Magento cron is running

### 3. Pickup points

1. Go to **Stores → Configuration → Innosend → Pickup Points**
2. Enable pickup points, select carriers, and configure map options
3. Save config

---

## Post-install checklist

- [ ] `setup:upgrade` completed (data patch ran on 1.0.x → 1.1.0 update)
- [ ] `setup:di:compile` completed without errors
- [ ] **API Token** entered and **Test API Token Connection** succeeds
- [ ] Pickup Points enabled and visible in checkout (if used)
- [ ] Order Synchronization enabled and cron running (if used)
- [ ] `php bin/magento cache:flush` run after config changes

---

## Troubleshooting

| Issue | Action |
|-------|--------|
| Packages not found after `composer require` | Verify private Packagist repo is configured (see Preparations) |
| Token test fails (401) | Token invalid or expired — generate new one in the Innosend Dashboard |
| Token test fails (404) | Wrong endpoint URL or Mode — check both fields |
| Old API Key/Secret fields still visible | Config cache not flushed — run `php bin/magento cache:flush` |
| DI compilation errors after update | Run `php bin/magento setup:di:compile` |
| Pickup points not in checkout | Verify API Token is valid; check `var/log/system.log` |
| Orders not syncing | Verify order sync is enabled and Magento cron is running |

---

## Module overview

| Package | Magento module | Version | Purpose |
|---------|---------------|---------|---------|
| `innosend/magento2-integration` | `Innosend_Integration` | 1.1.0 | API client, Bearer token auth, config, healthcheck |
| `innosend/magento2-pickup-points` | `Innosend_PickupPoints` | 1.1.0 | Pickup points in checkout |
| `innosend/magento2-order-connector` | `Innosend_OrderConnector` | 1.0.3 | Order and status sync |

---

## Support

- Docs: see `vendor/innosend/{module}/docs/en/` for each module
- Email: support@innosend.eu
- Developer: henk@falconmedia.nl
- Dashboard: https://dashboard.innosend.eu
