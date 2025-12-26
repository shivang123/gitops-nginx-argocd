# GitOps NGINX Project – Mistakes & Fixes

This file lists mistakes I made during the project and how I fixed them.

## 1. TLS Certificate Issue
**Problem:**  
fatal: unable to access 'https://git-server/
...': server certificate verification failed


**Cause:**  
Gitea was using a **self-signed TLS certificate**. Git and Argo CD could not trust it.

**Fix:**  
- On Ubuntu:
```bash
sudo cp gitea-ca.crt /usr/local/share/ca-certificates/
sudo update-ca-certificates

```
**Branch Mismatch**

Problem: Tried pushing main while local branch was master

error: src refspec main does not match any

**Fix**

git branch -M main
git push -u origin main
