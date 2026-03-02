# Preparations (do this first)

← [Home](home)

---

**The Innosend developer must complete these steps before installing or updating the module.** They configure access to the private Packagist repository where the Innosend packages are hosted.

---

## 1. Add the private Packagist repository

From the Magento 2 root directory:

```bash
composer config repositories.private-packagist composer https://repo.packagist.com/falconmedia/innosend/
```

This is required to resolve and install the `innosend/magento2` packages.

---

## 2. Authentication: developer (local / updating)

For **read/write access** on your developer machine (e.g. `composer require`, `composer update`), use a **global** Composer auth config. Innosend provides you with a Packagist username and read/write token.

Run once on your development machine (replace the placeholders with the credentials from Innosend):

```bash
composer config --global --auth http-basic.repo.packagist.com YOUR_PACKAGIST_USERNAME YOUR_PACKAGIST_READ_WRITE_TOKEN
```

This stores credentials in your global `auth.json` (e.g. `~/.composer/auth.json`), so you can update the module and run `composer update`.

---

## 3. Authentication: deployment (server / read-only)

For **deploying to the client server** (e.g. CI/CD or production), use a **read-only** token. This must be stored in the project’s `auth.json` so that `composer install` can run without write access.

Run from the Magento 2 root directory (Innosend provides the read-only token):

```bash
composer config --auth http-basic.repo.packagist.com token YOUR_PACKAGIST_READ_ONLY_TOKEN
```

This creates or updates `auth.json` in the project root.

> **Note:** The read-only token may only be used for installing dependencies (e.g. `composer install`). It cannot be used for `composer update` or publishing packages. Use it only on deployment targets, not on developer machines that need to run `composer update`.

---

## Summary

| Environment      | Where to configure | Purpose                    |
|------------------|--------------------|----------------------------|
| Developer machine| `composer config --global --auth ...` | Read/write; `composer update` |
| Deployment/server| Project `auth.json` via `composer config --auth ...` | Read-only; `composer install` |

After completing these steps, continue with [Installation](Installation).

---

Next: [Installation](Installation)
