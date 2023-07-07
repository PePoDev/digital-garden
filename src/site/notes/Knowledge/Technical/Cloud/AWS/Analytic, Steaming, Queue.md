---
{"dg-publish":true,"permalink":"/knowledge/technical/cloud/aws/analytic-steaming-queue/","dgPassFrontmatter":true}
---

## Kinesis
- 
## SQS
- Standard Queue (Oldest, over 10 years old)
	- Unlimited throughput, unlimited number of messages in the queue
	- Default retention of messages 4 days, max 14 days
	- Low latency (<10 ms on publish and receive)
	- Limitation of 256KB per message sent
	- Can have duplicate messages (at least once delivery, occasionally)
	- Can have out-of-order messages (best-effort ordering)
- Producer
	- Produced to SQS using the SDK (SendMessage API)
- Consumer
	- Poll SQS for messages (receive up to 10 messages at a time)
	- Delete the messages using the DeleteMessageAPI
- Security
	- In-flight encryption using HTTPS API
	- At-rest encryption using KMS keys
	- Client-side encryption
	- Access Controls by IAM policies
	- SQS Access Policies (similar to S3 bucket policies)
		- Useful for cross-account access
		- Useful for allowing other services to write to an SQS queue
## SNS
- 
## Amazon MQ
- 
