# Configuration

← [Home](home)

---

## 1. API configuration (required)

Go to **Stores → Configuration → Innosend → API Configuration**.

| Field | Value |
|-------|-------|
| **Enable API connection** | Yes |
| **Mode** | `Test` (staging) or `Production` |
| **API Token** | Bearer token from the Innosend dashboard |
| **Organization ID** | Optional — leave empty unless instructed otherwise |
| **Request Timeout** | Default 30 s — increase if pickup points are slow |

### Getting the API Token

1. Log in to the [Innosend Dashboard](https://dashboard.innosend.eu)
2. Go to **Settings → API Keys**
3. Create a new token and copy it
4. Paste it into the **API Token** field in Magento
5. Click **Save Config**
6. Click **Test API Token Connection** — a success message confirms the token is valid

> **v1.0.x users:** The API Key and API Secret fields have been removed. The API Token replaces both. Your old token (if already set) is migrated automatically on `setup:upgrade`.

---

## 2. Order synchronization

Go to **Stores → Configuration → Innosend → Order Synchronization**.

| Field | Recommendation |
|-------|----------------|
| Enable order sync | Yes |
| Sync on order place | Yes (or use cron-only for high-volume stores) |
| Status sync interval | As required (default: every 15 min via cron) |
| Retry attempts | 3 |

After saving, verify that Magento cron is running:

```bash
php bin/magento cron:run
```

---

## 3. Pickup points

Go to **Stores → Configuration → Innosend → Pickup Points**.

| Field | Notes |
|-------|-------|
| Enable Pickup Points | Yes |
| Allowed Carriers | Select carriers (e.g. DHL, PostNL) — list is fetched from the API |
| Show Map | Yes / No |
| Map Type | OpenStreetMap (default) or Google Maps |

> The API Token set in step 1 is also used to fetch the carrier list and pickup points. No separate credentials are needed here.

---

[Installation](Installation) · [Post-install checklist](Post-install-checklist)
