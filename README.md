# GitHub Actions Workflows

This repo contains three CI/CD workflows for my GitHub Actions assignment.

---

## ✅ 1. Multi-Platform Testing
**File:** `.github/workflows/multi-platform.yml`

Runs tests on:
- Ubuntu
- Windows
- macOS

Each job prints OS info and writes a file to verify execution.

---

## ✅ 2. Environment Variables & Secrets Workflow
**File:** `.github/workflows/env-and-secrets.yml`

Features:
- Manual trigger (`workflow_dispatch`)
- Workflow-level variables:  
  - `AWS_REGION = us-east-1`
  - `ENVIRONMENT = production`
- Job-level variable:  
  - `DEPLOYMENT_NAME = MyAppDeployment`
- Prints masked GitHub Secrets  
- Demonstrates variable scope

### ⚠️ Issue I Faced
I initially merged all workflows into one `.yml` file by mistake, which caused:
> Unexpected value error

I fixed it by separating each workflow into its own file.

---

## ✅ 3. Dependent Jobs Workflow
**File:** `.github/workflows/dependent-jobs.yml`

Uses `needs:` to enforce order:
1. Build
2. Test
3. Deploy

---

## 🎯 How to Run
- Multi-platform & dependent jobs run on push to `main`
- Env & Secrets workflow runs manually from **Actions → Run workflow**

---


