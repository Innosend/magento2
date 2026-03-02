# Post-install checklist

← [Home](home)

---

- [ ] `composer require innosend/magento2` ran without errors
- [ ] `php bin/magento setup:upgrade` completed (data patch migrated config if updating from 1.0.x)
- [ ] `php bin/magento setup:di:compile` completed without errors
- [ ] **API Token** entered in **Stores → Configuration → Innosend → API Configuration**
- [ ] **Test API Token Connection** button returns a success message
- [ ] Pickup Points enabled and visible in the checkout (if used)
- [ ] Order Synchronization enabled and Magento cron is running (if used)
- [ ] `php bin/magento cache:flush` run after every config change

---

[Configuration](Configuration) · [Troubleshooting](Troubleshooting)
