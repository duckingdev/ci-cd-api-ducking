# 🚀 CI-API-DUCKING · Reusable Deployment Workflows

This repository provides **reusable GitHub Actions workflows** for deploying the API-DUCKING project to different environments.

---

## 📌 **Available Workflows**

| Workflow File            | Purpose                          |
| ------------------------ | -------------------------------- |
| `.github/workflows/deploy-staging.yml` | Deploy to **Staging** environment |
| `.github/workflows/deploy-production.yml` | Deploy to **Production** environment |

---

## ✅ **How to Use**

To reuse these workflows in another repository:

```yaml
jobs:
  deploy-staging:
    if: github.ref == 'refs/heads/staging'
    uses: duckingdev/ci-api-ducking/.github/workflows/deploy-staging.yml@main
    with:
      ref: ${{ github.sha }}
    secrets:
      SSH_PRIVATE_KEY_STAGING: ${{ secrets.SSH_PRIVATE_KEY_STAGING }}
      REMOTE_USER_API_DUCKING_STAGING: ${{ secrets.REMOTE_USER_API_DUCKING_STAGING }}
      REMOTE_HOST_STAGING: ${{ secrets.REMOTE_HOST_STAGING }}
      REMOTE_PATH_API_DUCKING_STAGING: ${{ secrets.REMOTE_PATH_API_DUCKING_STAGING }}
