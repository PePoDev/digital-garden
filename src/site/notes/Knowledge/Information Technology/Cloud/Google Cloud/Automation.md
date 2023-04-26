---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/automation/","dgPassFrontmatter":true}
---

## CI/CD pipelines
![Automation-2023-04-24.png](/img/user/Attachments/Automation-2023-04-24.png)
### Spectrum
![Automation-2023-04-24-1.png](/img/user/Attachments/Automation-2023-04-24-1.png)
### Google Cloud Services
![Automation-2023-04-24-2.png](/img/user/Attachments/Automation-2023-04-24-2.png)
## Cloud Source Repository
- managed Git repository
- Control access by using IAM
- Work with Google services
-  allows Google Cloud diagnostics tools, like Debugger and Error Reporting
## Cloud build
- Google-hosted Docker build service
- Use CLI to submit a build `gcloud builds submit --tag <tag> .`
## Build triggers
- Watch a repository and trigger whenever code is pushed
- Support Maven, custom builds, and Docker
## Container Registry
- Cloud-hosted Docker repository
- Tag image with `gcr.io/<project-id>/image-name`
- Vulnerability scanning (must be explicitly enabled)