# Support

← [Home](home)

---

## Contact

| Channel | Details |
|---------|---------|
| Support email | support@innosend.eu |
| Developer | henk@falconmedia.nl |
| Innosend Dashboard | https://dashboard.innosend.eu |

---

## Documentation

Each module ships its own `docs/` directory with an EN and NL version:

| Module | User Guide | Technical Guide |
|--------|-----------|-----------------|
| `magento2-integration` | `vendor/innosend/magento2-integration/docs/en/USER_GUIDE.md` | `…/TECHNICAL_GUIDE.md` |
| `magento2-pickup-points` | `vendor/innosend/magento2-pickup-points/docs/en/USER_GUIDE.md` | `…/TECHNICAL_GUIDE.md` |
| `magento2-checkout-hyva` | `vendor/innosend/magento2-checkout-hyva/docs/en/USER_GUIDE.md` | `…/TECHNICAL_GUIDE.md` |

---

## Before contacting support

1. Run **Test API Token Connection** in the admin config — confirm it succeeds.
2. Check `var/log/system.log` and `var/log/exception.log` for error messages.
3. Include Magento version, PHP version, module versions, and exact error text in your ticket.

```bash
# Get module versions
composer show innosend/magento2-integration innosend/magento2-pickup-points innosend/magento2-order-connector
```

---

[Troubleshooting](Troubleshooting) · [Module overview](Module-overview)
