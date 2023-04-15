---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/automation/","dgPassFrontmatter":true}
---

## CI/CD pipelines
![Pasted image 20230415162209.png](/img/user/Attachments/Pasted%20image%2020230415162209.png)
### Spectrum
![Pasted image 20230415162333.png](/img/user/Attachments/Pasted%20image%2020230415162333.png)
### Google Cloud Services
![Pasted image 20230412133723.png](/img/user/Attachments/Pasted%20image%2020230412133723.png)
## Cloud Source Repository
- managed Git repository
- Control access by using IAM
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