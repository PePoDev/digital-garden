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
- The customer-supplied encryption key (CSEK)
- Object Versioning
	- Maintain a history of modifications of objects
	- List archived versions of an object, restore or delete.
- Object Lifecycle Management
	- Object inspection occurs in asynchronous batches
	- Changes can take 24 hours to apply
	- Example
		- Downgrade storage class on objects older than a year
		- Delete objects created before a specific date
		- Keep only the 3 most recent versions of an object
- Directory synchronization
- Object change notification
	- Can use with pub/sub notifications for Cloud Storage 
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
### Data Import Services
#### Transfer Appliance
AWS Snowball-like. Rack, capture, and then ship your data to Google Cloud
![Attachments/Pasted image 20230319190416.png](/img/user/Attachments/Pasted%20image%2020230319190416.png)![Attachments/Pasted image 20230319190617.png](/img/user/Attachments/Pasted%20image%2020230319190617.png)
#### Storage Transfer Service
Import online data (another bucket, an S3 bucket, or a web source)
#### Offline Media Import
Third-party provider uploads the data from physical media
## Filestore
- Fully managed network attached storage (NAS) for Compute Engine and GKE instances
- Predictable performance
- Full NFSv3 support
- Scales to 100s of TBs for high-performance workloads
## Cloud SQL
- Cloud SQL offers fully managed relational databases, including MySQL, PostgreSQL, and SQL Server as a service
- Designed to hand off mundane, but necessary and often time-consuming, tasks to Google—like applying patches and updates managing backups, and configuring replications
- Spec: 64 TB of Storage, 60000 IOPS, 624 GB of RAM
- Scale:
	- Up: Machine capacity
	- Out: Read replicas
- Choice:
	- MySQL 5.6, 5.7 (default), or 8.0
	- PostgreSQL 9.6, 10, 11, 12, 13 (default), or 14
	- Microsoft SQL Server 2017 or 2019 (standard default)

![Attachments/Pasted image 20230319201143.png](/img/user/Attachments/Pasted%20image%2020230319201143.png)
## Cloud Spanner
- Cloud Spanner is a fully managed relational database service that scales horizontally, is strongly consistent, and speaks SQL
- Battle-tested by Google’s mission-critical applications and services, Spanner is the service that powers Google’s $80 billion business
- Cloud Spanner is especially suited for applications that require: A SQL relational database management system with joins and secondary indexes Built-in high availability Strong global consistency And high numbers of input and output operations per second
- Tens of thousands of reads and writes per second or more
- Scale to petabytes
- Used for financial and inventory applications
- Uptime (Multi-regional: 99.999%, Regional: 99.99)

![Attachments/Pasted image 20230319205034.png](/img/user/Attachments/Pasted%20image%2020230319205034.png)
## Cloud Firestore
- Firestore is a flexible, horizontally scalable, NoSQL cloud database for mobile, web, and server development
- With Firestore, data is stored in documents and then organized into collections
- Documents can contain complex nested objects in addition to sub-collections
- Firestore NoSQL queries can then be used to retrieve individual, specific documents or to retrieve all the documents in a collection that match your query parameters
- Queries can include multiple, chained filters and combine filtering and sorting options
- They're also indexed by default, so query performance is proportional to the size of the result set, not the dataset
- ACID transactions
- Multi-region replication
- Live synchronization and offline support
- Datastore mode (server)
	- backward compatible with Cloud Datastore
	- No entity limits
- Native mode (mobile and web apps)
	- Collection and document data model
	- Real-time updates

![Attachments/Pasted image 20230319205822.png](/img/user/Attachments/Pasted%20image%2020230319205822.png)
## Cloud Bigtable
- Cloud Bigtable is Google's NoSQL big data database service
- The same database powers many core Google services, including Search, Analytics, Maps, and Gmail
- Bigtable is designed to handle massive workloads at consistently low latency and high throughput
- Customers often choose Bigtable if: They’re working with more than 1TB of semi-structured or structured data
- Petabyte-scale
- Consistent sub-10ms latency
- Seamless scalability for throughput
- Learns and adjusts to access patterns
- Ideal for Ad Tech, Fintech, and IOT
- Storage engine for MK applications
- Easy integration with open-source big data tools

![Attachments/Pasted image 20230319210450.png](/img/user/Attachments/Pasted%20image%2020230319210450.png)

![Attachments/Pasted image 20230319210648.png](/img/user/Attachments/Pasted%20image%2020230319210648.png)

![Attachments/Pasted image 20230319210812.png](/img/user/Attachments/Pasted%20image%2020230319210812.png)

![Attachments/Pasted image 20230319210825.png](/img/user/Attachments/Pasted%20image%2020230319210825.png)
## Memorystore
- In-memory data store service
- High availability, failover, patching, and monitoring
- Sub-millisecond latency
- Instances up to 300 GB
- Network throughput of 12 Gbps
- Easy Lift-and-Shift
