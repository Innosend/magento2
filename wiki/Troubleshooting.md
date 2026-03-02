# Troubleshooting

← [Home](home)

---

## API / token issues

| Symptom | Action |
|---------|--------|
| **Test API Token Connection** fails with 401 | Token is invalid or expired — generate a new one in the [Innosend Dashboard](https://dashboard.innosend.eu) → **Settings → API Keys** |
| **Test API Token Connection** fails with 404 | Wrong endpoint URL or **Mode** (Test vs. Production) — check both fields |
| API Token field shows `*****` but test still fails | Token may be corrupted in DB — clear the field, re-enter the token, save and test again |
| Old API Key/Secret fields still visible after update | Config cache not flushed — run `php bin/magento cache:flush` |

## Installation / upgrade issues

| Symptom | Action |
|---------|--------|
| Packages not found after `composer require` | Verify the private Packagist repo is configured (see [Preparations](Preparations)) |
| `setup:upgrade` fails on `MigrateConfigPaths` | Check `var/log/exception.log`; confirm DB user has write access to `core_config_data` |
| DI compilation errors after 1.1.0 upgrade | Run `php bin/magento setup:di:compile` — new interfaces require regeneration |
| Module not found error | Run `php bin/magento module:enable Innosend_Integration Innosend_PickupPoints Innosend_OrderConnector` |

## Pickup points

| Symptom | Action |
|---------|--------|
| Pickup points not shown in checkout | Confirm API Token is valid; check browser console and `var/log/system.log` |
| Carrier dropdown empty in admin | Token invalid — carrier list cannot be fetched; fix token and flush config cache |
| Map not loading | Enable **Show Map** in Pickup Points config; for Google Maps verify API Key and Map ID |

## Order sync

| Symptom | Action |
|---------|--------|
| Orders not syncing | Confirm **Order Synchronization** is enabled; check that Magento cron is running and `var/log` for errors |
| Status not updating | Check sync interval setting; verify cron schedule |

## General

```bash
# Check module status
php bin/magento module:status | grep Innosend

# View recent errors
tail -n 50 var/log/system.log
tail -n 50 var/log/exception.log

# Flush everything
php bin/magento cache:flush && php bin/magento setup:di:compile
```

---

[Configuration](Configuration) · [Post-install checklist](Post-install-checklist) · [Support](Support)
