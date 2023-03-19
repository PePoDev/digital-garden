---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/storage/","dgPassFrontmatter":true}
---


![Attachments/Pasted image 20230319173437.png](/img/user/Attachments/Pasted%20image%2020230319173437.png)

![Attachments/Pasted image 20230319173542.png](/img/user/Attachments/Pasted%20image%2020230319173542.png)
## Cloud Storage
Cloud Storage is a collection of buckets to store objects.
### FEATURES
- Scalable to exabytes
- Time to the first byte in milliseconds
- Very high availability across all storage classes
- Single API across storage classes
- Customer-supplied encryption key (CSEK)
- Object Versioning
- Object Lifecycle Management
- Directory synchronization
- Object change notification
- ACLs
### Notes
- The default class is applied to new objects
- The regional bucket can never be changed to multi-region/dual-region
- The multi-regional bucket can never be changed to regional
- Objects can be moved from bucket to bucket
- Object Lifecycle Management can manage the classes of objects
### Storage Class
![Attachments/Pasted image 20230319174904.png](/img/user/Attachments/Pasted%20image%2020230319174904.png)
### ACLs
- ACL is a mechanism used to define who has access to your buckets and objects, as well as the level of access to have
- The maximum number of ACL entries you can create for a bucket or object is 100
- Each ACL consists of one or more entries, and these entries consist of two pieces of information
- A scope that defines who can perform the specified actions
- The permission defines what actions can be performed
- The `allUsers` identifier listed under the slide represents anyone who is on the Internet, with or without a Google account
- The `allAuthenticatedUsers` identifier, in contrast, represents anyone who is authenticated with a Google account
![Attachments/Pasted image 20230319182213.png](/img/user/Attachments/Pasted%20image%2020230319182213.png)
### Signed URLs
- Create a URL that grants read or write access to a specific cloud storage resource, and specifies when this access expires.
- That URL is signed using a private key associated with their service account. 
- When the request is received, Cloud Storage can verify that the axis granting URL was issued on behalf of a trusted security principle.
- "Valet Key" access to buckets and objects via ticket
	- The ticket is a cryptographically signed URL
	- Time-limited
	- Operations specified in the ticket: HTTP GET, PUT, DELETE (not POST)
	- Any user with a URL can invoke permitted operations
- Example:
	- `gsutil signurl -d 10m path/to/privatekey.p12 gs://bucket/object`
### Storage Transfer Service
Managed service to transfer data
### Transfer Appliance
AWS Snowball-like
## Filestore

## Cloud SQL
Cloud SQL offers fully managed relational databases, including MySQL, PostgreSQL, and SQL Server as a service. It’s designed to hand off mundane, but necessary and often time-consuming, tasks to Google—like applying patches and updates managing backups, and configuring replications.
## Cloud Spanner
Cloud Spanner is a fully managed relational database service that scales horizontally, is strongly consistent, and speaks SQL.
Battle-tested by Google’s mission-critical applications and services, Spanner is the service that powers Google’s $80 billion business. Cloud Spanner is especially suited for applications that require: A SQL relational database management system with joins and secondary indexes Built-in high availability Strong global consistency And high numbers of input and output operations per second. We’re talking tens of thousands of reads and writes per second or more.
## Cloud Firestore
Firestore is a flexible, horizontally scalable, NoSQL cloud database for mobile, web, and server development. With Firestore, data is stored in documents and then organized into collections. Documents can contain complex nested objects in addition to sub-collections. Firestore’s NoSQL queries can then be used to retrieve individual, specific documents or to retrieve all the documents in a collection that match your query parameters. Queries can include multiple, chained filters and combine filtering and sorting options. They're also indexed by default, so query performance is proportional to the size of the result set, not the dataset.
## Cloud Big table
Cloud Bigtable is Google's NoSQL big data database service. The same database powers many core Google services, including Search, Analytics, Maps, and Gmail. Bigtable is designed to handle massive workloads at consistently low latency and high throughput, so it's a great choice for both operational and analytical applications, including the Internet of Things, user analytics, and financial data analysis. When deciding which storage option is best, customers often choose Bigtable if: They’re working with more than 1TB of semi-structured or structured data.