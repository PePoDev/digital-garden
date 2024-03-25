---
{"dg-publish":true,"permalink":"/knowledge/technical/kubernetes/cks/","noteIcon":""}
---

## Courses
- [CKS – Challenges | KodeKloud](https://kodekloud.com/courses/cks-challenges/)
- [Certified Kubernetes Security Specialist (CKS) | KodeKloud](https://kodekloud.com/courses/certified-kubernetes-security-specialist-cks/)
- [Killer Shell (CKS) - 100% Practice tests with explanation - YouTube](https://www.youtube.com/playlist?list=PLpbwBK0ptssx38770vYNwZEuCeGNw54CH)
## Fundamentals
### Architecture
![CKS-2023-12-03.png](/img/user/Attachments/CKS-2023-12-03.png)
### PKI
![CKS-2023-12-03-1.png](/img/user/Attachments/CKS-2023-12-03-1.png)
### Kernel Vs User Space
![CKS-2023-12-16.png](/img/user/Attachments/CKS-2023-12-16.png)
### Linux Kernel Isolation
- Namespaces - Restrict what processes can see
	- PID
	- User
	- Filesystem
	- Network
- cgroups - restrict the resource usage of processes
	- RAM
	- Disk
	- CPU
## Cluster Setup
### CIS Benchmarks
- The Center for Internet Security (CIS) provides a standardized set of security benchmarks to identify and refine effective security measures for a specific set of tools and technologies
- Example of COS Rules
	- Avoid the use of "root" account
	- Ensure CloudTrail log file validation is enabled 
	- Ensure VPC flow logging is enabled in all VPCs
### Kube-bench
Tool for scan the Kubernetes cluster based on the CIS Benchmark

![CKS-2024-01-15.png](/img/user/Attachments/CKS-2024-01-15.png)
### Encryption Provider Config
The kube-apiserver process accepts an argument `--encryption-provider-config` that controls how API data is encrypted in ETCD
```yaml
apiVersion: apiserver.config.k8s.io/v1
kind: EncryptionConfiguration
resources:
  - resources:
      - secrets
      - configmaps
      - pandas.awesome.bears.example
    providers:
      - aescbc:
          keys:
            - name: key1
              # See the following text for more details about the secret value
              secret: <BASE 64 ENCODED SECRET>
      - identity: {} # this fallback allows reading unencrypted secrets;
                     # for example, during initial migration
```
### Access Control
![CKS-2024-01-15-1.png](/img/user/Attachments/CKS-2024-01-15-1.png)
#### Authentication
There are multiple ways in which we can authenticate. Some of these include:

| Authentication Modes | Description |
| ---- | ---- |
| X509 Client Certificates | Valid client certificates signed by trusted CA |
| Static Token File | Sets of bearer token mentioned in a file |
#### Authorization
| Authorization Modes | Description |
| ---- | ---- |
| AlwaysDeny | Blocks all requests (Used in test) |
| AlwaysAllow | Allows all requests; use if you don't need authorization |
| RBAC | Allows you to create and store policies using the Kubernetes API |
| Node | A special-purpose authorization mode that grants permissions to kubelets |
#### OpenID Connect
There are various additional configurations needed for the API server as part of the integration
- `--oidc-issuer-url` - The URL of the OpenID issuer
- `--oidc-username-claim` - The OpenID claim to use as the user name
- `--oidc-client-id` - Client ID for the OpenID Connect client
![CKS-2024-01-15-2.png](/img/user/Attachments/CKS-2024-01-15-2.png)
#### RBAC Authorization
##### Default Cluster Role and Cluster Role Binding

| Default ClusterRole | Default ClusterRoleBinding | Description |
| ---- | ---- | ---- |
| cluster-admin | system:masters group | Allows super-user access to perform any action on any resource |
| admin | None | Allows admin access, intended to be granted within a namespace using a RoleBinding |
| edit | None | Allows read/write access to most objects in a namespace |
| view | None | Allows read-only access to see most objects in a namespace |
### Auditing

#### Policy
| Audit Levels | Description |
| ---- | ---- |
| None | don't log events that match this rule |
| Metadata | Log request metadata (requesting user, timestamp, resource, verb, etc.) but not request or response body |
| Request | Log event metadata and request body but not response body |
| RequestResponse | Log event metada, request and response bodies |

#### Important Flags
| Audit Configuration | Description |
| ---- | ---- |
| --audit-policy-file | Path to the file that defines the audit policy configuration |
| --audit-log-path | Specifies the log file paththat log backend uses to write audit events |
| --audit-log-maxage | Maximum number of days to retain old audit log files |
| --audit-log-maxbackup | Maximum number of audit log files to retain |
| --audit-log-maxsize | Maximum size in MB of the audit log file before it gets rotated |
### Kubelet Security
| Important Configuration | Description |
| ---- | ---- |
| --anonymous-auth | Requests that are not rejected by other configured authentication methods are treated as anonymous requests |
| --authorization-mode | AlwaysAllow, Webhook |
| --client-ca-file | start the kubelet with the --client-ca-file flag, providing a CA bundle to verify client certificates |
| --read-only-port | Associated with ReadOnlyAPI |
#### Node Authorizer
| Operations | Endpoints |
| ---- | ---- |
| Read | services, endpoints, nodes, pods, secrets, and others |
| Write | nodes and node status, pods and pos status, events |
| Auth-Related | R/W to SCR for TLS Bootstrapping |
### Network Policies

### Default Deny
### 
## Sheet Cheat
- k create pod nginx --image nginx --dry-run=client -o yaml
- k delete pod nginx --grace-period=0 --force
- k config get-contexts -o name
- k config current-context
- cat ~/.kube/config | grep -i current-context | sed 's/current-context: //'

```yaml
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: nginx
  name: nginx
  namespace: default
spec:
  nodeName: master
  containers:
  - image: nginx:latest
    name: nginx
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```
