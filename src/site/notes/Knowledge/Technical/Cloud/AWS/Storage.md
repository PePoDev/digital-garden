---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/storage/","dgPassFrontmatter":true}
---

## EBS
- Elastic Block Store is a network drive
- Can mount only one instance at a time
- Bound to a specific AZ
- Type
	- gp2 / gp3 (SSD): general purpose, 1GiB - 16 TiB
	- io1 / io2 (SSD): highest-performance, 4GiB - 16 TiB
		- Support multi-attach in the same AZ up to 16 instances at a time
	- st1 (HDD): low cost, 125GiB - 16 TiB
	- sc1 (HDD): lowest cost, 125GiB - 16 TiB
- Only gp2/gp3 and io1/io2 can be used as boot volumes
- Data at rest is encrypted inside the volume
- All the data in flight moves between the instance and the volume is encrypted
- All snapshots are encrypted
- Encryption has a minimal impact on latency
- EBS encryption leverages keys from KMS (AES-256)
### Snapshot
- Make a backup at a point in time
- Not necessary to detach the volume to do a snapshot, but recommended
- Can copy snapshots across AZ or Region
### Snapshot Archive
- Move a snapshot to an "archive tier" that is 75% cheaper
- 24 to 72 hours for restoring the archive
### Recycle Bin
- Setup rules to retain deleted snapshots so you can recover them after an accidental deletion
- Specific retention (from 1 day to 1 year)
### Fast Snapshot Restore (FSR)
- Force full initialization of snapshot to have no latency on the first use (\$\$\$)
## Instance Store
- High-performance hardware disk
- Better I/O performance
- Ephemeral, Lose when stopping the instance
- Good for the buffer, cache, scratch data / temporary content
- Backup and Replication are your responsibility
## EFS
- Managed NFS that can mount on many EC2
- Work with EC2 instances in multi-AZ
- Highly available, scalable, expensive (3x gp2), pay per use
- Use NFSv4.1 protocol
- Use a security group to control access
- Compatible with Linux-based AMI
- Modes
	- Performance Mode
		- General Purpose (default)
		- Max I/O: higher latency, throughput, highly parallel
	- Throughput Mode
		- Bursting: 1 TB = 50 MiB/s + burst of up to 100 MiB/s
		- Provisioned: set your throughput regardless of storage size
		- Elastic: automatically scales throughput up or down based on your workload
			- Up to 3 GiB/s for reads and 1 GiB/s for writes
- Storage Tiers
	- Standard: frequently accessed files
	- Infrequent access (IA): cost to retrieve files, lower price to store
- Availability and durability
	- Standard: Multi-AZ
	- One zone: One AZ, Backup enabled by default, compatible with IA, 90% cost saving
- Lifecycle Policy: move files between storage tier
- File system policy: Control the access permission in EFS
## RDS
- Stands for Relational Database Service
## Aurora

## ElasticCache
