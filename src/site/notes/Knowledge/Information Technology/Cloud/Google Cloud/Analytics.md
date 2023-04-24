---
{"dg-publish":true,"permalink":"/knowledge/information-technology/cloud/google-cloud/analytics/","dgPassFrontmatter":true}
---

## BigQuery
- Serverless, Highly scalable, Cost-effective cloud data warehouse
- Fully managed
- Petabyte scale
- SQL interface
- Very fast
- Import
	- Batch Import (free)
		- Import from Cloud Storage
		- Import after processing by Cloud Dataflow and Cloud Dataproc
	- Streaming Import
		- From Cloud pub/sub, Streaming inserts
		- Import after processing by Cloud Dataflow and Cloud Dataproc
		- Use `insertId` to de-duplication
	- Federated Queries (Query external data)
	- BigQuery Data Transfer Service
- Features
	- BigQuery ML
	- BigQuery BI Engine
	- BigQuery GIS
	- BigQuery Omni
- Storage API
	- Spark
	- Tensorflow
	- Dataflow
	- Pandas
	- Scikit-learn
- BigQuery Transfer Service
- Configurable Table Expiration
- Partitioning
	- Improves performance and reduces costs
	- Partition based on ingestion time or a column
	- All you to expire parts of table data easily
- Clustering
	- Colocate related data and eliminate scans of unnecessary data
	- Avoid creating too many small partitions (less than 1 GB) in those cases, prefer Clustering
## Cloud Dataflow
- Execute a wide variety of data processing patterns
- Serverless, fully managed data processing
- Batch and stream processing with autoscale
- Open source programming using Beam
- Intelligently scale to millions of QPS
- Can use to export the Bigtable data to Cloud Storage
- Often used for ETL
![Analytics-2023-04-24.png](/img/user/Attachments/Analytics-2023-04-24.png)
## Dataproc
- Managed Spark and Hadoop service
- Visually explore, clean, and prepare data for analysis and machine learning
- Serverless, works at any scale
- Suggests ideal data transformation
- Focus on data analysis
- Integrated Partner service operated by Trifacta
- Cloud Storage Connector (instead of HDFS attached storage)
![Analytics-2023-04-24-1.png](/img/user/Attachments/Analytics-2023-04-24-1.png)
## Cloud Datalab
- Web-based tool to explore, analyze and visualize data based on Jupyter notebook
- Support for popular data-science toolkits (pandas, numpy, and scikit-learn)
## Cloud Data Studio
- Dashboard and Visualization
- Live charts and graphs based on data in Cloud SQL, BigQuery etc
## Cloud Data Catalog
- Data discovery and metadata management
- Unified view of all datasets
- Tag sensitive data using Cloud Data Loss Prevention (DLP)
## Cloud Composer
- Managed Apache Airflow Service
- Pipeline orchestration for complex dependencies
- Executes workflows defined in directed acyclic graphs (DAGs)
- Workflow is a collection of tasks with dependencies
- DAGs scripted in Python and stored in Cloud Storage
## Cloud Data Fusion
- Code-free (Drag and Drop) ETL/TLT development tool
- Managed service based on open-source CDAP data analytics platform
- Deploy as an instance
- Edition
	- Developer
	- Basic
	- Enterprise
## Dataprep
- Apache Spark, Apache Hadoop clusters
- Low cost (per second, preemptible)
- Super fast to start, scale, and shutdown
- Integrated with GCP
- Managed service
- Simple and familiar
![Analytics-2023-04-24-2.png](/img/user/Attachments/Analytics-2023-04-24-2.png)
