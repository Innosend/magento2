# GitLab Wiki – innosend/magento2

These Markdown files are the source for the **GitLab wiki** of the project `innosend/magento2`.

## How to publish to GitLab Wiki

### Option A – Manual (page by page)

1. In your GitLab project, open **Wiki** in the left sidebar.
2. **Home page**: Edit the start page and paste the contents of `home.md`.
3. **Other pages**: For each file below, click **New page**, set the title as shown, and paste the file content.

| Wiki page title | Source file |
|-----------------|-------------|
| home | `home.md` |
| Preparations | `Preparations.md` |
| Requirements | `Requirements.md` |
| Installation | `Installation.md` |
| Configuration | `Configuration.md` |
| Optional-Hyva-Checkout | `Optional-Hyva-Checkout.md` |
| Post-install-checklist | `Post-install-checklist.md` |
| Troubleshooting | `Troubleshooting.md` |
| Module-overview | `Module-overview.md` |
| Support | `Support.md` |

Links between pages use the wiki page title as the link target (e.g. `[Installation](Installation)`). If you use different page titles, update the links in each file accordingly.

### Option B – Git push (if wiki repository is enabled)

```bash
# Clone the wiki repo (URL from GitLab → Wiki → Clone repository)
git clone https://gitlab.com/innosend/magento2.wiki.git /tmp/innosend-wiki

# Copy all .md files
cp wiki/*.md /tmp/innosend-wiki/

# Push
cd /tmp/innosend-wiki
git add .
git commit -m "docs: update wiki for v1.1.0"
git push
```

## Current version: 1.1.0
